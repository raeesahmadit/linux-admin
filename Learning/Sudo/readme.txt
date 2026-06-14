-to change the user: su - <username>     # where '-' will start form home but remov '-' from exact location
-to logout from that user: exit
-to login root : su - 

-sudo (super user do): temporarily grant admin rights

-details of sudo in: /etc/sudoers

-wheel/sudo group: users in wheel group can act as a admin rights

-to add user in sudo group: usermod -aG sudo <username>

-to provide limited sudo access to specific commands: 
     find the path of a command by using 'which' <command-name>
              e.g: which systemctl             #it will show /usr/bin/systemctl            
            (as a root/sudo): visudo --> 
                 (below the root user) <username> ALL=<command name>
                                root ALL=(ALL)        ALL
                                nick ALL=(ALL) /usr/bin/systemctl                     #locate is command name

-which: it prints the complete path of a command

-whatis: it prints function of specific command 