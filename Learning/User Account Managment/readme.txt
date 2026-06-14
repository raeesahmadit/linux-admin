user account managment: 
           -useradd
           -userdel
           -usermod
           -groupadd
           -groupdel
 
files: 
            /etc/passwd
            /etc/group
            /etc/shadow

-simple:
    create a user:  useradd <username>
    to check user is created: id <username>
    to check all users: less /etc/passwd

-customize way:
    create a user: useradd -g <groupname> -s /bin/bash -c "description" -m -d /home/<username> <username>
       (-g add in a specific group)  (-s specific script)(-c user info) (-m make folder) (-d permisiion and where)

-delete a user:
     -userdel <username> : no folders or file will delete
     -userdel -r: remove all his data too, home dirctory too
     -userdel -f: remove user forcefully even if user is logged in

-modify a user:
    (imp)-to add a user to a new group and default group will remain same:
            usermod -G <groupname><username>
         -to change the default group:
            usermod g<groupname><username>
    
    
-others modifications:
              -m -d: /home/folder (to move/shift the content of homefolder to the newfolder)
              -passwd <usrename>: to change password of a user
              -s: shell type
              -usermod -L -U <username>: (lock/unlock user) : user could not be loggedin


-to make a new group:           -groupadd <groupname>
      check group is made or not:    -less /etc/group
-to delete a group:             -groupdel <groupname>

-/etc/shadow: password details about every user, when was last password changed max day to expire 