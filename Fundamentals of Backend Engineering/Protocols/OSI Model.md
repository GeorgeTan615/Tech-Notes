## OSI Model (Open Systems Interconnection Model)
### 7 layers each describe a specific networking component
- Layer 7 - Application - HTTP/FTP/gRPC
- Layer 6 - Presentation -  Encoding/Serialization (parse JSON object to string)
- Layer 5 - Session - Connection establishment, TLS
- Layer 4 - Transport - UDP/TCP (send segments in TCP and send datagrams in UDP)
- Layer 3 - Network - IP (send packets)
- Layer 2 - Data link - Frames, Mac Address Ethernet (send frames)
- Layer 1 - Physical - Electric signals, fiber or radio waves

## Example (Sender)
- Example sending a POST request to HTTPS webpage