UMASK: to change default file permissions

    to check: umask           0002/0022 is default
              umask -S        readable format

permissions:  
        0777 - 0022 = 0755    #first bit is for special bits, user, group, others

to change(temporary): 
        umask u+rw,g+w,o+wx
    
    permanently: changes in '.bashrc' file    # for all users changes in /etc/bashrc folder else in your own (hidden.bashrc) file
                cd ~ 
                vi .bashrc
                at end> umask o-r >save
                source .bashrc   #to apply changes after save
                