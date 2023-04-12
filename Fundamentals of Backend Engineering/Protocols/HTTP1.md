## Client/Server
- (Client) Browser, python or javascript app, or any app that
makes HTTP request
- (Server) HTTP Web Server, e.g. IIS, Apache Tomcat, NodeJS, Python Tornado

## HTTP Request Structure
- Method (GET,POST,PUT,PATCH,DELETE)
- PATH (uri endpoint)
- Protocol (HTTP/1.1, HTTP/1.2 etc)
- Headers (Content type,content length,cookies)
- Body (empty for GET request)
![HTTP Req](https://media.discordapp.net/attachments/776828668386213908/1095578463215296543/image.png?width=1694&height=915)

## HTTP Response Structure
- Protocol (HTTP vers)
- Code (Response Status code)
- Code text (description for status code)
- Headers 
- Body 
![HTTP Response](https://media.discordapp.net/attachments/776828668386213908/1095583106532130846/image.png?width=1694&height=924)

## HTTP 1.0
![HTTP1.0](https://media.discordapp.net/attachments/776828668386213908/1095588592648212500/image.png?width=1608&height=924)
- As can see, opens a new connection each time for a request
- Slow
- Buffering (transfer encoding didnt exist, no SSE)
- No multi-homed websites 

## HTTP 1.1
![HTTP1.1](https://media.discordapp.net/attachments/776828668386213908/1095588896194166855/image.png?width=1674&height=924)
![Pipelining](https://media.discordapp.net/attachments/776828668386213908/1095588923088048168/image.png?width=1629&height=924)
- Has persisted TCP connection, open one connection and get all the stuff you want
- Low latency and low CPU usage
- Streaming with chunked transfer as we can keep a connection open and keep sending stuff
- Pipelining, send the requests all at once(disabled by default as what if the image reached first before html, client expect get html first)
- Proxying and multi homed websites
