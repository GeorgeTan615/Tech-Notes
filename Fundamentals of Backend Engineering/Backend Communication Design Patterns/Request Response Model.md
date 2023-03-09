## Overall process
1) Client sends a request
2) Server parses a request
3) Server processes a request
4) Server sends a response
5) Client parses the response and consume

## Serialization
A mechanism of converting state of an object into byte stream. The byte stream us platform independant, thus can be deserialized on different platforms.

## Deserialization
A reverse process to convert the byte stream back into the actual object.

## Where is Request Response Model Used
- Web, HTTP, DNS, SSH (send 'ls' return directory)
- RPC (remote procedure call, calling a function that exists in a remote server)
- SQL and Database Protocols (parses SQL and makes up the plan, then returns the data)
- APIs (REST/SOAP/GraphQL)

## Building upload image service with Request Response
1) Send a large request with the image (simple)
2) Chunk the image and send a request for each image (resumable, know which chunks arent sent and continue there)

## Cases where Request Response doesn't work
1) Notifications 
	- For example when user logs in, server is the one that has the data and knowledge of this
	- Request Response can work if you keep on asking requests "Is the user logged is the user logged in...", but its so redundant and hard to scale right? These empty requests would also congest the network 
2) Chat applications
	- Same logic "Did the user send a message did the user send a message...", not scalable
3) Long requests
	- Responses take too long to return 
4) What if client disconnects
	- How does the user know if the request has been done when the client reconnects