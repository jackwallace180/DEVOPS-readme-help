## :link: ssh Command :link: ##

ssh is a command that can be used to go into a virtual machine. For this we will need the SSH private key (located on your machine) that is linked with the public key on your virtual machine.
The way we use the command is as follows:

 - $ ssh -i ~/.ssh/my-key.pem ubuntu@my-virtual-machineDNS

 replacing my-key.pem with your private key file and my-virtual-machineDNS with the DNS or public IP of your virtual machine.

## :mailbox: scp Command :mailbox: ##

scp stands for secure copy paste.
We can send files to our virtual machine without even being inside them, to do this we use the scp command. Similar to ssh we will need the SSH private key that is linked to the VM, as well as a destination in the virtual machine (can be made by ssh'ing inside and using $ mkdir or/and $ touch). We will also need the route on your local machine to the file you want to copy.
the command is as follows:

 - $ scp -i ~/.ssh/my-key.pem home/documents/my-file ubuntu@my-virtual-machineDNS:/home/USER/FILENAME

 Replacing my-file with the desired file and USER/FILENAME with whatever directory you made in your virtual machine.

 scp is particularly useful for moving provision files you have written. We can use dos2unix to transform our written provision file into a file that our VM will understand. Once we have used scp to move the file into our VM we can run it and it will run all the provisioning that you had written!
