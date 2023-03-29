## Network vs Host
- a.b.c.d/x (a.b.c.d are integers) x is the networks bits and remains as host
- Example 192.168.254.0/24 (so a,b,c each is 1 byte (up to 2^8 = 255), thus total 3 bytes x 8 = 24 bits for network, and d alone is for host which is 1 byte = 8 bits)
- The first 24 bits (3 bytes) are network, the rest 8 bits are for host
- This means we can have 2^24 networks and each network has 2^8 hosts
- Also called a subnet

## Subnet Mask
- 192.168.254.0/24 is also called a subnet
- and each subnet has a subnet mask, for ex  255.255.255.0
- Subnet mask is used to determine whether an IP is in the same subnet

## Default gateway 
- Most network consists of hosts and a Default Gateway 
- Host A can talk to B directly if they are in the same subnet
- Otherwise A sends to someone they might know, the gateway
- The gateway has an IP address and each host should know its gateway

## Example
- If host A,192.168.1.3 wants to talk to host B, 192.168.1.2, A applies its subnet mask to both its IP and host B's IP and check if they are in the same subnet
- so 255.255.255.0 bit operation AND 192.168.1.3, compared with bit AND operation of 255.255.255.0 with 192.168.1.2, if both results same, then router can just pass the pass according to MAC address (layer 2) (remember the IP are just all bits)
- if different subnet, the packet is sent to the default gateway (router)(its IP should be known) 
- However, ARP Poisioning could happen as some host could disguise its IP as the router's IP and be receiving off all the data