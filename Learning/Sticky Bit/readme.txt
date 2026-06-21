sticky bit or (Restricted Deletion Flag): 
              only file/directory owner can delete or rename a file/directory for secuirty purpose
              show as 't' 'T'

drwxrwxr-T 2 ibcent IT 18 Jun 2026 folder/
              
        t: when there is already executable 'x' is assigned to file/directory
        T: when there is no executable 'x' is assigned to file/directory

to set/unset:
             chmod o+t <foldername/filename>
             chmod o-t <foldername/filename>