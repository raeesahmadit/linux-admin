postfix: how to generate and send emails, using google smtp service

    -to check is installed?:    rpm -qa | grep postfix    #if nothing show mean its not installed
    -to install:                yum install postfix       #for functionality
                           yum install mailx         #for mailing

-configration files:   /etc/postfix/main.cf
     add as it is:    relayhost = [smtp.gmail.com]:587
                      myhostname= <your-hostname>

-add followings lines to main.cf end:
        #########################################################################
        #Location of sasl_passwd we saved
        smtp_sasl_password_maps = hash:/etc/postfix/sasl/sasl_passwd

        #Enable SASL authentication for postfix
        smtp_sasl_auth_enable = yes
        smtp_tls_security_level = encrypt

        #Disallow methods that allow anonymous authentication
        smtp_sasl_secutiry_options = noanonymous

-create a file under /etc/postfix/sasl/
   filename: sasl_passwd
-add the detail:
   [smtp.gmail.com]:587 <email>@gmail.com:<password>

              -to get the password: 
                 1.go to google mail > security >
                 2. 2step authentication should Enable
                 3. search 'apps password'
                 4. enter stmp app name
                 5. copy that password to <password>

-convert the sasl_passwd file into db file: 
   postmap sasl_passwd  
   #on the same place and if you have to change gmail or password make db file agian after previous step

-change permissions for password for security purpose:
   chmod 600 *        #this will only allow to user

-start postfix service:
  systemctl start postfix.service
  systemctl status postfix.service     #should active(running)

-to send mail:
         echo "test mail" | mail -s "postfix Test" email@gmail.com     # (-s) subject line in mail and reciver email
   -with attach a file: echo "test mail" | mail -s "postfix Test" -a <testfilepath> email@gmail.com      #-a to attacha file