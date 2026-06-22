system monitoring:
         to see is there any hardware problem in the server 
         
         (dmesg): linux utility displays kernel related messages retrieved from the kernel ring buffer
                 ring buffer stores info abiut hardware, device driver initialization and message from kernel modules on startup

        dmesg : show everything
        dmesg -HTx | more          (human readable)
        dmesg | head -10
        dmesg | tail -10

        dmesg -HTx | grep usb
        dmesg -HTx | grep memory
        dmesg -HTx | grep sda
        dmesg -HTx | grep ram
        dmesg -HTx | grep tty
        dmesg -HTx | grep error
        dmesg -HTx | grep warn

        dmesg -w       (live monitoring)
        dmesg -c       (to clear ring buffer)
        dmesg -l (emerg/alert/crit/err/warn/notice/info/)