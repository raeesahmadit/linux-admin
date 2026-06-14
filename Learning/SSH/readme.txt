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
