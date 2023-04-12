HTTP1.1 we need to use one connection to get a single thing, HTTP2 we can multiplex over a single connection, thus combine many requests into one connection and receive many responses in one connection, i.e., send more than one thing in one connection. HTTP2 with push is dead, where for ex u ask for index.html, server is gonna send you all the css, images, js, blabla together. Is bad because client might dont need those, maybe client already cached those

## Pros
- Multiplexing over a single connection
- Compression (headers and data)
- Server push
- Secure by default
- Protocol Negotiation

## Cons
- TCP head of line blocking
	- We send requests in order, for ex requests 10 is not related to request 1, but since its in order, if request 1 did not make it, server will not process requests 2-10, thus blocked
- Server push never picked up
- High CPU usage
	- because we have streams headers, flow control at streams level and backend has to read and parse these