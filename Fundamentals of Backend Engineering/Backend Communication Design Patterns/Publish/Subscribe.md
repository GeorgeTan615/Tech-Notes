## Where it breaks (Microservice Naive Request Response)
[Microservice Naive Request Response](https://media.discordapp.net/attachments/776828668386213908/1083301328303947816/image.png?width=1503&height=820)
- Any service that breaks in the middle will break the whole thing
- Pros
	- Elegant and simple
	- Scalable
- Cons
	- Bad for multiple receivers 
	- High coupling (one breaks everything breaks)
	- Client/server have to be running
	- Chaining,circuit breaking