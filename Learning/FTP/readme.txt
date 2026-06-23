FTP (file transfer protocol) :
          is a communication protocol used for transfer of files b/w client and server on a network
          uses TCP/IP
          also used to upload/download files from website and server


   -remote server FTP setup(reciver):
           -need root acces
           -install vsftpd service : yum install vsftpd
        config: 
            /etc/vsftpd/vsftpd.conf 

            -anonymous_enable=NO
            -uncomment
                -ascii_upload_enable=YES
                -ascii_download_enable=YES
                -write_enable=YES
            -may add
                 -use_localtime=YES

    -client server FTP setup(sender):
        -need root access
        -install ftp service : yum install ftp

perform: 
       type ftp and enter a new terminal will start with ftp>

transfer a file:
        ftp 192.168.100.110 
        user/pass
        ftp> put <path/file>
        ftp> pwd                            #to see where are we
        ftp> cd /home/ibtu/Desktop/files    #to change to send location in remote server
        ftp> mkdir videos                   #to make a new folder in remote server
        ftp> mput file1 file2 file3         #to send multiple files

download file from remote server:
        ftp> get <file>