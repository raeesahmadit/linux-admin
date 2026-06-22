Log files:
          it stores events, processes, messages and other data from apps, operating system, or device
          provide info based on actions performs by users, important for monitoring/troubleshooting

  /var/log : logs location

  log files (RHEL): 
            -boot.log : on starting boot processes 
            -dnf.log/yum.log: packages install, update uninstall
            -chron    : cron jobs all details
            -secure   : login activities about users, trying acces, password relaed
            -maillog  : mails issues
            -httpd    : web server issues
            -messages : (most used) all activites on server
  
  log files (ubuntu):
            -boot.log    : on starting boot processes
            -dpkg.log: packages install, update uninstall
            -syslog    : cron jobs all details
            -auth.log   : login activities about users, trying acces, password relaed
            -maillog  : mails issues
            -httpd    : web server issues
            -syslog : (most used) all activites on server
    
    
    cat: Displays the entire log content at once
    less: Lets you scroll through logs page-by-page
    tail -f : Monitors new log entries in real-time

-journalctl (modern way) : system logs via systemd
 This service does not use traditional files, but you can query all logs instantly with this command

   journalctl              : view all system logs
   journalctl -f           : view live logs
   journalctl -b           : view since the last boot
   journalctl -u <service> : view specific service