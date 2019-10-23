# :shell: :key: SSH Keys :key: :shell: #

## What are SSH keys? ##

SSH (Secure Shell) is used for managing networks, operating systems, and configurations. Functionally SSH keys resemble passwords, They grant access and control who can access what. SSH keys always come in pairs, and every pair is made up of a private key and a public key. Who or what possesses these keys determines the type of SSH key pair. If the private key and the public key remain with the user, this set of SSH keys is referred to as user keys. If the private and public key are on a remote system, then this key pair is referred to as host keys.

### Public Key ###

A public key is copied to the SSH server(s). Anyone with a copy of the public key can encrypt data which can then only be read by the person who holds the corresponding private key.

### Private Key ###

A private key remains (only) with the user. The possession of this key is proof of the user's identity. Only a user in possession of a private key that corresponds to the public key at the server will be able to authenticate successfully. The private keys need to be stored and handled carefully, and no copies of the private key should be distributed.

## User Keys ##

![userkey](https://jumpcloud.com/wp-content/uploads/2017/08/LAN.png)

In a user key set, the private key remains on the system (our computer) being used to access the remote system (AWS EC2 as an example) and is used to decrypt information that is exchanged in the SSH protocol. Private keys should never be shared with anyone. A public key is used to encrypt information, can be shared, and is used by the user and the remote server. On the server end, the public key is saved in a file that contains a list of authorized public keys. On the user’s side, the public SSH key is stored in an SSH key management software or in a file on their computer.  

This is typically what we use in DevOps, for example if we are creating a virtual machine and want an application (such as jenkins) to connect and communicate with our local machine. But since we are the only possessor of the private key only we can connect via the SSH which is normally desirable!#
