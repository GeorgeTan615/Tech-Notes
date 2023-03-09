## Where it breaks (Microservice Naive Request Response)
![Microservice Naive Request Response](https://media.discordapp.net/attachments/776828668386213908/1083301328303947816/image.png?width=1503&height=820)
- Any service that breaks in the middle will break the whole thing
- Pros
	- Elegant and simple
	- Scalable
- Cons
	- Bad for multiple receivers 
	- High coupling (one breaks everything breaks)
	- Client/server have to be running
	- Chaining,circuit breaking


## Pub/Sub
![Pub/Sub Model](https://media.discordapp.net/attachments/776828668386213908/1083307057945530378/image.png?width=1419&height=820)
- In context of microservices, each microservice in charge of publishing to a a certain topic or subscribe to certain topic, don't have to care about overall flow
- Upload service - > Raw Mp4 videos, Compress service then consumes everything from raw MP4 videos and does it stuff and publishes to Compressed video, same goes for others
- Pros
	- Scales with multipler receivers
	- Great for microservices
	- Loose coupling
	- Works while client is not running (after upload you're just done, very independant and loosely coupled)

- Cons
	- Message delivery issues (would not know if subscriber actually got the message, or if consumed twice, thats why kafka has this at least once guarantee thing)
	- Complexity (adding another broker, making partitions to scale better)
	- Network saturation (a lot of clients wanting to poll)
