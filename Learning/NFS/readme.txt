NFS (Network File System): a network protocol for distributed file system, 
            a client can access the files on server side like as they are accessing locally
            sync and shared files on both server and client

 -setup(centos):
       server-side config(providing access):
             -install:      yum install nfs-utils libnfsidmap
             -start:        systemctl enable rpcbind, nfs-server
                            systemctl start rpcbind, nfs-server, rpc-statd, nfs-idmap
             
             -make folder(to share):  
                           -mkdir /server/apps
             -give permission:  
                            chmod 777 /server/
                            chmod 777 /server/apps
             -modify rule to share to which client:
                            vi /etc/exports:
                                           /server/apps *(rw,sync,no_root_squash)
             -load the changes: 
                            exportfs -rv       


        
        client-side  (accessing):
             -install:      yum install nfs-utils rpcbind
             -start:        systemctl /start rpcbind
             -stop firewall: systemctl stop firewalld /iptable
             -show mount from NFS server: showmount -e <ip of server>

             -create a mount point(folder): mkdir /mnt/apps
             -mount NFS file system: mount <ip>:/server/apps /mnt/apps
             -verify: df -h

perform: 
        (open client side)                                 (open server side)
          cd /mnt/apps                                   cd /server/apps

what ever you make or delete every thing will be sync on both sides in apps folders