## Stateful VS Stateless Backend
- Stateful
	- Stores state about client in memory
	- Depends on the information being there
- Stateless
	- Client is responsible to transfer 'the state' with every request
	- May store but can safely lose i

## What makes a backend stateful
- Stateless backends can store data somewhere else(database)
- The backend remains stateless but the system is stateful
- Can you restart the backend during idle time and the client workflow will continue to work?

## Stateless vs Stateful protocols
- The protocols can be designed to store state
- TCP is stateful
	- Sequences, Connection file descriptor
- UDPgi is stateless
	- DNS send queryID in UDP to identify queries
	- QUIC sends connectionID to identify connection


## Complete Stateless System
- Stateless Systems are rare
- State is carried with every request
- A backend service that relies completely on the input
	- Check if input param is a prime number
- JWT (JSON Web Token)
	- Therefore insecure, what if someone stole, if session id stored in db we can just flip it, but for jwt if stolen means we are exposed, same goes for the refresh and access tokens for jwt
- Definitions go nowhere