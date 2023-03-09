## Request/Response isn't always ideal
- Client wants real time notifications from backend
	- User just logged in 
	- A message is received
- Push model can be ideal in such cases as server/backend is the one that has the info

## What is Push
- Client connects to server
- Server sends data to client
- Client doesnt' have to reuqest anything
- Protocol must be bidirectional
- Used by RabbitMQ

## Pros and Cons of Push
- Pros
	- Real time (sends data once an event happens or smth)

- Cons
	- Clients must be online (can push data to a server and server pushes to client once client is online, but cant directly push to a client that is offline)
	- Clients might not be able to handle (client does not know the payload, what if speed of processing the payload at client side is slower than speed of receiving the payloads, server may crash)
	- Requires a biredirectional polling
	- Polling is preferred for light clients (clients only make request when they have leisure/can handle)