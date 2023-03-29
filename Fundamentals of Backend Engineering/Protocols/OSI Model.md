## OSI Model (Open Systems Interconnection Model)
### 7 layers each describe a specific networking component
![OSI Model](https://media.geeksforgeeks.org/wp-content/uploads/computer-network-osi-model-layers.png)
- Layer 7 - Application - HTTP/FTP/gRPC
- Layer 6 - Presentation -  Encoding/Serialization (serialize JSON object to string)
- Layer 5 - Session - Connection establishment, TLS
- Layer 4 - Transport - UDP/TCP (send segments in TCP and send datagrams in UDP)
- Layer 3 - Network - IP (send packets)
- Layer 2 - Data link - Frames, Mac Address Ethernet (send frames)
- Layer 1 - Physical - Electric signals, fiber or radio waves

## Example (Sender) (Layer 7 -> Layer 1)
- Example sending a POST request to HTTPS webpage
- Layer 7 - Application 
	- POST request with JSON data to HTTPS webpage
- Layer 6 - Presentation
	- Serialize JSON data into flat byte strings
- Layer 5 - Session
	- Request to establish TCP connection/TLD
- Layer 4 - Transport
	- Sends SYN request target port to 443 (to establish connection, need send SYN, ACK packets, port 443 is also the default port for HTTPs)
- Layer 3 - Network
	- SYN is placed in IP packets and adds the source/dest IPs
- Layer 2 - Data link
	- Each packet goes into a single frame and adds the source/dest MAC address
- Layer 1 - Physical
	- Each frame becomes string of bits which converted into either a radio signal(wifi), electric signal (ethernet), or light (fiber)

## Example (Receiver) (Layer 1 -> Layer 7)
- Receiver computer receives the POST request the other way around
- Layer 1 - Physical
	- Radio, electric or light is received and converted into digital bits
- Layer 2 - Data link
	- The bits from layer 1 are assembled into frames
- Layer 3 - Network
	- The frames from layer 2 are assembled into IP packet
- Layer 4 - Transport
	- The IP packets from layer 3 are assembled into TCP segments
	- Deals with Congestion control/flow control/ retransmission in case of TCP
	- If segment is SYN we don't need to go further into more layers as we are still processing the connection request
- Layer 5 - Session
	- The connection session is established or identified
	- We only arrive at this layer when necessary (three way handshake is done)
- Layer 6 - Presentation
	- Deserialize flat byte strings back to JSON for the app to consume
- Layer 7 - Application
	- Application understands the JSON POST request and your express json or apache request receive event is triggered

## When client sends HTTP post request (segments,packets, frames)
![When client sends HTTP post requests](https://media.discordapp.net/attachments/776828668386213908/1089475184894943232/image.png?width=1599&height=924)
![How segments, packets and frames work in OSI model](https://media.discordapp.net/attachments/776828668386213908/1089474626112999484/Untitled-2023-03-24-1310.png?width=1204&height=469)

## Shortcomings of OSI model
- OSI model has too many layers which can be hard to comprehend
- Hard to argue which layer does what
- Simpler to deal with layers 5-6-7 as just one layer, application
- TCP/IP model does just that 

TCP/IP Model
- Application (layer 5,6,7)
- Transport (layer 4)
- Internet (layer 3)
- Data link (layer 2)
- Physical layer is not officially covered in the model 
