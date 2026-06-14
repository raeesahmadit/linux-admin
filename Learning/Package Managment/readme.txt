package managment: its about packages
                 -installing
                 -upgrading
                 -deleting
                 -view package info
                 -package config

package mangment tools:
  -yum/dnf/rpm for redhat-based linux like centos    #'dnf' is new version of 'yum'
  -apt for debian based like ubuntu, kali

-yum (yellow-dog updater modifier): primary package management tool for redhat
     (imp) - yum perform dependencies resolutions when installing, updating and removing software
 
 e.g: -installing/removing: sudo yum install nginix -y     # -y is already saying yes otherwise it will ask you tu install
                           sudo yum remove nginix
        
      -update/upgrade: sudo yum upgrade package
                      sudo yum update package

      -different b/w upgrade and update:
               upgrade: will delete old packages 
               update: keep old packages we can rollback

      -yum -option                : you can see what else you can do
      -yum check-update           : list will come you can update then
      -yum history                : see all history even other user can see
      -yum history undo/redo <id> : to redu or undo by using id


-rpm (redhat package manager package): install, uninstall, query individual software packages
       (imp) - cant manage dependencies like yum
             - maintain a database of installed packages, which enables powerful and fast queries

e.g:  -installing: install, upgrade or delete an .rpm package
        -rpm -i package-file   : install
        -rpm -U package-file   : upgrade
        -rpm -ivh package-file : v-verbose (addition info), h for hash to show progess
        -rpm -evh package-file : erase
(imp)   -rpm -qa :  to query all installed packages
(imp)   -rpm -qi <package-name>: more info 
(imp)   -rpm -qc <package-name>: show all files about configrations of package
        -copy .rpm file form internet and using 'wget' paste it then use uper commands to install or etc..


-dnf (dandified yum): updated version of yum, also resolve dependencies
        -sudo dnf list avaliable
        -sudo dnf list installed
        -sudo dnf update/upgrade 
        -sudo dnf install package
        -sudo dnf remove package
        -sudo dnf info package
        -sudo dnf search package

-apt: for ubuntu (much similar to yums)
       -apt install package
       -apt remove package
       -apt autoremove (to remove the dependencies of package, because it doesnt with only remove cmd)
       -apt-get upgrade: upgrade all avaliable packages you have installed
       -apt-get update: only get list of avaliable packages 
       -apt-cache search package