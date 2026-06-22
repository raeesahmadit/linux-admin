RSYNC: r sync, a utilty for efficient transfering and syncronizing files across diff systems or locations
       best in speed, flexibility, efficiency

features: -if you send a 8gb file to a remote server and again send it will not send all 8gb file it only send the changes 2nd time
          - 1st time can be slow because use syncronizing and also send detail of ownership, when made etc..

RSYNC syntax:
            rsync [options] source destination
    options:
           -a / --archive  : archiving files
           -v / --verbose  : verbose output
           -z / --compress : compression
           --progress      : to show progress bar
    -after cahnges:
           -b              : backup before deleting , this will update a new file with backup old same file after changes
           -d              : delete file before copying
           --backup-dir=/tmp/

perform: your account should be in destination
        rsync (-a,-v,-z,--progress,--backup-dir=/tmp/) <filename> <user>@<destination-ip>:<filepath-where-to-send>
 
 ex: rsync -vzab --progress --backup-dir=/home/ibtu/Desktop/archive/$(date +%Y%m%d-%H%M%S) name.txt ibcent@192.168.100.112:/home/ibcent/Desktop/ 