Firewall: is a network security system that monitor and control incoming and outgoing network traffic
          based on rules defined, used to determin and block untrusted network to access out system

types: 
        -software based: run on operating system 
        -hardware based: a dedicated application with Firewall software b/w two different networks

tools on linux:
        -iptables (old)
        -firewalld (latest)

to check the firewalld service is installed or not:  
         rpm -qa | grep firewalld 
to install: 
         sudo yum install firewalld
to stop/start/restart:
         sudo sysytemctl stop/start firewalld
         sudo sysytemctl enable/disable firewalld
         sudo sysytemctl restart firewalld

-check the ruels of firewalld (as a root ):
                            firewall-cmd --list-all         #you can change all to any specific detail like: ports,interfaces,etc
-list all services firewalld is aware of:
                            firewall-cmd --get-services
-reload config of firewalld:
                            firewall-cmd --reload

-firewall has multiple zones, to get list:
                            firewall-cmd --get-zones
                            firewall-cmd --get-active-zones                 #to see only active zones
                            firewall-cmd --zone=<name-of-zone> --list-all   #for specific zone rules


-to add/remove a service(temporary,will remove after reload):
                        firewall-cmd --add-service=<name-of-service>          #services name can be seen in list
                        firewall-cmd --remove-service=<name-of-service>
-to add/remove a service(permanently,will not remove after reload, restart firewall to apply changes):
                        firewall-cmd --add-service=<name-of-service> --permanent          #services name can be seen in list
                        firewall-cmd --remove-service=<name-of-service> --permanent


-to add/remove a port: 
                      firewall-cmd --add-port=<port-no>/type-of-protocol> --permanent
                      firewall-cmd --remove-port=<port-no>/type-of-protocol> --permanent
                                                       (80/tcp)

-to block incoming traffic from an IP:
                     firewall-cmd --add-rich-rule='rule family="ipv4" source address="192.168.0.0" reject'
-to block outgoing traffic to a IP or URL:
                     firewall-cmd --direct --add-rule ipv4 filter OUTPUT 0 -d <IP> -j DROP
         (to get a ip of any wesite:      (host -t a www.fb.com))

-to block ICMP incoming traffic: (nobuddy can ping your server)
                     firewall-cmd --add-icmp-block-inversion