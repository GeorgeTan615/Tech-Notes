## TCP
- Controls the transmission unlike UDP which just sends everything regardless
- Has a connection, thus requires handshake
- 20 bytes headers segment
- Stateful (store client and server info)

## Use cases
- Reliable communication (e.g. text messages)
- Remote shell 
- Database connections (e.g. SQL commands)
- Web communication (everything in web done through http which is built on tcp)
- Any bidirectional communication (just like WebSockets)

## TCP connection
- Connection is layer 5 (save the session)
- Connection is agreement between client and server (store who is connected, so spoofing is prevented)
- Must create connection to send data 
- Connection is identified by 4 properties (make a hash out of these 4 properties and can use a lookup to see if we have connection)
	- SourceIP-DestinationIP
	- SourcePort - DestinationPort
- Cant send data outside of connection
- Sometimes called socket or file descriptor
- Requires a 3 way handshake
- Segments are sequenced and ordered
- Segments may arrive out of order but can be easily rearranged back
- Lost segments are retransmitted

## Connection establishment (SYN -> SYN/ACK -> ACK)
![Connection Establishment](https://media.discordapp.net/attachments/776828668386213908/1094609528076648498/image.png?width=1694&height=894)

## Sending data
![Sending data](https://media.discordapp.net/attachments/776828668386213908/1094610727240749116/image.png?width=1659&height=924)
Flow Control - Can server handle the incoming load
Congestion Control - Can routers handle the load 

## Acknowledgment
![Acknowledgement](https://media.discordapp.net/attachments/776828668386213908/1094611282033905685/image.png?width=1694&height=798)
If you acknowledge sequence3, means you also acknowledge 1 and 2, everything above the number you acknowledged is acknowledged as well

## Lost data (Retransmission)
![Retransmission of lost data](https://media.discordapp.net/attachments/776828668386213908/1094612071645196408/image.png?width=1694&height=894)

## Close connection
![Close connection](https://cdn.discordapp.com/attachments/776828668386213908/1094612289409261568/image.png)
- Can't close a non existent connection, send FIN, checks if has a connection based on file descriptor, if yes, sends back ACK
- File descriptor is then destroyed once received the last ACK, but the side that initiated this closing connection does not destroy its file descriptor, and is put into a time wait state. This is to handle old/ lost segments that have just been retrasmitted and we are able to identify that they are old, and clean them up
- If we dont clean them up, it may cause corruption

## TCP Pros
- Guarantee delivery
- No one can send data without prior knowledge
- Flow control and Congestion control
- Ordered Packets no corruption
- Secure can't be easily spoofed

## TCP Cons
- Larger header overhead compared to UDP
- More bandwidth
- Stateful, consumes memory on server and client (store file descriptor etc)
- Considered high latency for certain workloads (slow start/congestions/acks)
- Does too much at a low level (hence QUIC)
	- Single connection to send multiple streams of data (HTTP requests)
	- Stream 1 has nothing to do with Stream 2
	- Both Stream 1 and Stream 2 packets must arrive
- TCP Meltdown
	- Not a good candidate for VPN

## Anatomy of TCP Segment
- Source Port
- Destination Port
- Sequence Number
- Acknowledgement number (because we can send message as we are acknowledging)
- TCP Flags
- Window Size (specify the segment size that can handle)
- Checksum
- Urgent pointer
- Optional