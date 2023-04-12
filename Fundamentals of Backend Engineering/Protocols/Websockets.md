## Websocket process
Established through a websocket handshake, which is basically a http request.
![Handshake](https://cdn.discordapp.com/attachments/776828668386213908/1095595388897079306/image.png)
![Get upgrade](https://media.discordapp.net/attachments/776828668386213908/1095595434963116112/image.png?width=1625&height=924)
![Real example](https://cdn.discordapp.com/attachments/776828668386213908/1095595502214598656/image.png)
Asks for upgrade to websocket

## Use cases
- Chatting
- Live feed
- Multiplayer gaming
- Showing client progress/logging

## Pros
- Full duplex, no need for polling
- HTTP compatible, built on top of HTTP, which is built on top of TCP
- Firewall friendly, because websocket use the default ports of 80 and 443, which are generally not blocked by firewalls.

## Cons
- Stateful, difficult to horizontally scale
- Proxying is tricky
- L7 LB is challenging

## Do you have to use Websockets?
- No
- Rule of thumb - do you absolutely need bidirectional communication?
- Long polling
- Server Sent Events
