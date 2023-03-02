## TCP (Transmission Control Protocol)
Used to establish a connection between client and serve to transfer data.
## 3-way Handshake
1) Client sends a SYN segment which informs the server that the client is likely to start communication and with what sequence number it starts segment with.
2) Server sends back a SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with.
3) Client sends back an ACK packet and the client and server now has established a reliable connection with which they will start the actual data transfer.