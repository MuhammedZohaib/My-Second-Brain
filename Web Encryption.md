
![[Screenshot from 2023-01-18 21-22-53.png]]

# Web Encryption Protocols:
We use HTTPs to encrypt the communication between the browser and the web server. The `Https` mainly consist of `Http` and a `s-secure` protocol.

`s-secure` may consist of `Secure Socket Layer (SSL)`   or `Transport Layer Security (TLS)`

# History of Encryption:
Netscape was the one of the first browser. It came up with the encryption `SSL v1` Later in 1994 it introduced `SSLv2` and `SSLv3` in 1995. In 1995 Microsoft introduced internet explorer in windows and started the browser wars. Later in 1999 Both Microsoft and Netscape came to agreement and introduced `IETF` which is an encryption organization and both of these introduced `TLS 1.0`.
To this date we are using `TLS 1.3`.

## Process:
To encrypt a message the message goes under an encryption algorithm and a encryption key then it's encrypted and moved from browser to server where it goes under the same encryption algorithm and same encryption key is used to decrypt the message.
The key need to be identical as of encryption while decryption but how do we send the key to server without others finding out the key?


## Key Exchange Protocols:

1. `RSA(Rivest Shamir Adelman) in 1977` *Not used*
2. `Diffie Hellman in 1976` *Predictable*
3. `EC-DHE in 2011` *Used*

In `TLSv1.2` all the above protocols are used but in `TLSv1.3` only `EC-DHE` is used.

### TLS Key Exchange:

We use `Diffie-Hellman` key exchange by this there are two public keys(Prime Numbers) which are sent over to server and everyone can see these two keys.
Now Client generates a private key which only client know and it uses the `Diffie-Hellman` encryption and another two public keys are generated which are exchanged between the client and the server later these exchanged public keys goes under decryption using `Diffie-Hellman` formula and a same key is generated on the both server and client side in this way we can decrypt the encrypted messages.

![[Screenshot from 2023-01-18 21-22-05.png]]

### Vulnerability in Diffie-Hellman Algorithm

![[Screenshot from 2023-01-18 21-37-43.png]]


### EC-DHE:

![[Screenshot from 2023-01-18 21-34-27 1.png]]


## Data Encryption Protocols:
1. `3DES 168bit` *Not used anymore*

2. `AES 128 or 256bit` *Used*
* `Galios Counter Mode`
* `Cypher Block Chaining` *Used*

3. `Cha-Cha 20 ` 
* `Poly1305`

In addition to encryption protocols there are sub protocols which validates the encryption that it hasn't been tempered. Theses sub protocols checks the encryption integrity.

Once we encrypt the data with some encryption protocol it goes into sub encryption protocol which generates a hash and this hash is sent along with the encrypted data and sent over to the server where the encrypted data again under goes the same sub encryption protocol and generates a hash if the hash from client and server matches it validates the integrity of the encryption that the bits of the encrypted data haven't been tempered.  

![[Screenshot from 2023-01-18 21-27-07 1.png]]

# Handshake Integrity:
Handshake integrity is similar to encryption integrity.


At start there is a three way handshake with `TCP` protocols.
The client send a `client Hello` to server and Server keeps it and send back `server Hello` along with `server certificate and server key` in return client sends `client key`.
These are the calculated public keys.

## Process:
After the handshake we take a small portion from packets at the client side and run it under encryption which generates a hash and sends it to the server where the same packets also goes under the encryption and another hash is generated.
If client hash and server hash matches it validates the integrity of three way handshake. And same goes for the server and client validates the handshake.

### Algorithms:
The algorithms used to check integrity of handshake are:
* `SHA`
* `SHA-256`
* `SHA-384`


# Certificates:

Certificates all start with a certificate authority which is nothing more than a server running which allows to generate certificates. These certificates can be created with open source program like `Open SSL` .
Certificate authority creates a root certificate with a private key they use that root certificate along with another private key to generate an intermediate certificate and which is then used to generate server certificate.
In other words we can say that certificates verifies the integrity of the server and client communication that the server is actually who it claims to be.









 