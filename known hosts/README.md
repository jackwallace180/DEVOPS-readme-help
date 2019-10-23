# :two_men_holding_hands: Known Hosts :two_women_holding_hands:

One of the first things that happens when the SSH connection is being established is that the server sends its public key to the client, and proves (thanks to public-key cryptography) to the client that it knows the associated private key. This authenticates the server: if this part of the protocol is successful, the client knows that the server is who it claims it is.

The client may check that the server is a known one, and not some rogue server trying to pass off as the right one. SSH provides only a simple mechanism to verify the server's legitimacy: it remembers servers you've already connected to, in the ~/.ssh/known_hosts file on the client machine (there's also a system-wide file /etc/ssh/known_hosts). The first time you connect to a server, you need to check by some other means that the public key presented by the server is really the public key of the server you wanted to connect to. If you have the public key of the server you're about to connect to, you can add it to ~/.ssh/known_hosts on the client manually.

By the way, known_hosts can contain any type of public key supported by the SSH implementation

### Authorized Keys ###

Authorized keys can be easily confused with known hosts. Authorized keys holds a list of authorized public keys for servers. When the client connects to a server, the server authenticates the client by checking its signed public key stored within this file.
