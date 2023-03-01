# DNS (Domain Name System)
### *DNS Recursive Solver*
The computer that responds to the DNS query from the client and tracks down the IP address for the DNS record of the domain name.
### *TLD (top level domain) Nameserver*
A server that contains information for every domain name that share the same domain extension (.com,.net). So a .com TLD nameserver contains information for every website that ends with a '.com'
### *Authoritative Nameserver*
A server that holds the DNS resource records. It is usually the final source of truth in the lookup chain.
### *DNS Lookup Chain and Process*
Client -> DNS Recursive Resolver -> TLD nameserver -> Authoritative nameserver
1) User types in domain name in browser.
2) If the IP address for this domain does not exist in the browser cache or the OS cache, the query travels into Internet and resolved by DNS Recursive Resolver.
3) DNS Recursive Resolver checks if the IP exists in cache, if not, it queries the DNS root nameserver.
4) The root nameserver then responds to the resolver the address of the TLD DNS server (.com, .net) which stores the information of its domains.
5) The resolver then makes a request to the .com TLD server(for example).
6) The TLD server responds with the IP address of the domain (example.com)'s authoritative nameserver.
7) The recursive resolver makes request to the domain's authoritative nameserver and the authoritative nameserver responds with the IP address of the domain.
8) The recursive resolver returns this IP address to the web browser, where the web browser can send HTTP request to the IP address and the server at the IP returns the web page to be rendered in the browser.