 ## UDP (User Datagram Protocol)
 - Layer 4 protocol
 - Ability to address processes in a host using ports
 - Simple protocol to send and receive data
 - Prior communication not required (double edge sword)
 - Stateless no knowledge is stored on the host
 - 8 byte header Datagram
 - primarily used to establish low-latency and loss-tolerating communications between applications on the internet

 ## Use Cases
 - Video streaming
 - VPN
 - DNS
 - WebRTC
 - Computer games (interactive games that exchange small messages and losses can be recovered)

## UDP Datagram
- UDP Header is 8 bytes only (IPv4)
- Datagram slides into an IP packet as "data"
- Port are 16 bit (0 to 65535)

 ## Anatomy of UDP
- UDP Header
	- Source Port
	- Destination Port 
	- Length
	- Checksum (check if the packet has been corrupted or not)
 - Data

## Pros
- Simple protocol (basically saying we can deal with losses, don't just try to resend packets if there are losses, but just send the packets as soon as possible)
- Header size is small so datagrams are small
- Uses less bandwidth
- Stateless, consumes less memory as no state is stored in the server/client
- Low latency - no handshake, order, retransmission or guaranteed delivery

## Cons
- No acknowledgment (never really know if the thing that has been sent has been successfully delivered)
- No guarantee delivery (therefore low latency)
- Connection-less, anyone can send data without prior knowledge (no handshakes like TCP)(imagine a DNS attack where change the source IP to a victim and the victim gets flooded with dns responses)
- No flow control (no clue if the target can handle the data)
- No congestion control 
- No ordered packets
- Security - can be easily spoofed (anyone can send the packet and the receiver must process it at a cost, can easily DoS, denial of service, the machine)





 ## Multiplexing and demultiplexing
 - IP address targets host only
 - Hosts may run many apps each with different requirements
 - Ports now identify the "app" or "process", like how you can specify which port your app or server run on, e.g. "localhost:8080"
 - Sender multiplexes all its apps into UDP
 - Receiver demultiplex UDP datagrams to each app 