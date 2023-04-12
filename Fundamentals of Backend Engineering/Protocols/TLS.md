## TLS (Transport Layer Security)
Used to establish a secure connection on top of TCP connection. An important concept is you can't encrypt something with public key and decrypt it with public key, same goes for private key. So if encrypt with public, need to decrypt with private.
There are two key exchange algorithms, RSA and Diffie Hellman.
## TLS with RSA (1.2)
![RSA](https://cdn.discordapp.com/attachments/776828668386213908/1095399788322754651/image.png)
1. Client sends client hello, server sends hello back with a certificate attached with server's public key
2. Client generates symmetric key and encrypts it using server's public key, then sends this encrypted key to server
3. Server decrypts it using its private key
4. Now both sides have the symmetric key

But RSA has risk, if discover private key, then attackers can breach.

## TLS with Diffie Hellman (1.3)
![Diffie Hellman](https://cdn.discordapp.com/attachments/776828668386213908/1095400603519303720/image.png)
^ g and n are both public keys, x is a private key on client side and y is private key on server side
![Process](https://cdn.discordapp.com/attachments/776828668386213908/1095402114018181232/image.png)
1. Client sends g^x % n to server, server then uses its private key y to get the symmetric key
2. Server then sends g^y % n to client, client then uses its private key x to get the symmetric key
3. Now both sides has the symmetric key

This works because we are merging public and private key, and we can't unmerge it, thus private key is not obtainable from attackers

Diffie Hellman is more secure, but since we are dealing with exponentiation, it can be slower than RSA

## TLS Summary
TLS 1.3 much faster than TLS 1.2, as TLS 1.2 need two round trips (discuss on encryption those), TLS 1.3 just straight sends the necessary info