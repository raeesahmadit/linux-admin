SSH(secure shell): is a network communication protocol that enable two devices to communicate and share data
       - communication is encrypted
       - default port is 22 , but we can change it too

    -to access:
              ssh <username>@<ip/hostname> 
        (imp) but your user account should be on that machine too for login
    
    - to install shh service:
              sudo apt install openssh-client openssh-server 
    - to check status of ssh:
              systemctl status ssh
    - to start ssh:
              systemctl start ssh
    - to see the version of ssh: ssh -V
    - to see the version of ubuntu: cat /etc/os-relese



Connect SSH without password: when we have to access a server frequently
            1. we generate a new ssh key pair on local machine
            2.copy public-key to remote machine
            3.login to remote server without password

    ssh-keygen: set all thing blank                 #this will make a keygen in local machine
    ssh-copy-id <username>@<ip> : it will ask one time only and then you can access without 
 

 to remove keygen on both machines: so ask password every time, delete .ssh files in home directory
           cd ~
           ls .shh
           rm ~/.shh/codefilename 
