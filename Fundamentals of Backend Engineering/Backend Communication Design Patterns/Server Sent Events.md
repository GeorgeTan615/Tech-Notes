## Limitations of request/response
- Vanilla request/response isnt ideal for notification backend
- Client wants real time notification from backend
	- A user just logs in 
	- A message is just received
- Push works but restrictive
- Server sent requests works with request/response
- Designed for HTTP

## What is Server Sent Requests
- A response has start and end, server sent requests does not have an end
- Client sends a request
- Server sends logical events as part of response
- Server never writes the end of the response
- It is still a request but unending response
- TLDR, make a request, and server keeps sending events (can be message events containing dataor wtv) just like a stream of data

## Pros and Cons
- Pros
	- Real time
	- Compatible with request/response

- Cons
	- Client must be online
	- Client might not be able to handle
	- Polling is prefered for lighter clients
	- HTTP/1.1 problem (only have 6 TCP connections per domain, and HTTP/1.1 only can send one request per connection, thus if all 6 connections are server sent events, means all connections would be forever busy)