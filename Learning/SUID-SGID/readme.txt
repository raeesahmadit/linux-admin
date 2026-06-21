SUID: (set on user level)
     a file with SUID always execute as the user who owns the file, regardless of the user executing
     where 's' is seen mean userid is set, show as 's','S'
     e.g: rw(s)r-xr-x 1 root root 33424 Jun 18 2026 /usr/bin/passwd

  set/unset SUID:
      chmod u+s <filename> : set
      chmod u-s <filename> : unset


SGID: (set on a group level)
      if set on a file, it allow the file to be executed as the group that owns the file
      if set on a directory, any file created in the directory will have their ownership set to that of directory owner
      useful for directories that are often used in collaborative efforts b/w members of a group, any member can access any new file
      if a person create a file in that group then every member can make changes in it
  
  set/unser SGID:
       chmod g+s <filename>
       chmod g-s <filename>

