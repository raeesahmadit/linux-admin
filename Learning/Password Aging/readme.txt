password aging: two ways tos set the password aging
       1- onetime using 'change' command to a user
       2- makin default for every new user by making change in "/etc/login.def" file

-chage: 
    chage [-m min days] [-M maxdays] [-d lastday] [-I inactive] [-E expiredate] [-W warnday] <username>
        
        -m: no.of days required a user is allowed to change password
        -M: mac no. of days password is valid
        -d: days since Jan 1, 1970 that password was last changed
        -I: no. of days after password expire, account is disable
        -E: days since Jan 1, 1970 that password last changes (expire)
        -W: no. of days before password expire, user will be warn

-details:

ibtu : $6$.n : 19317 : 0 : 99999 : 7 : : :
username : encrypted password : last password change : min password age : max password age: warning period: inactivity period: expiration date: unused

-change a pssword age to 90 day expire and warn 10 day before: 
          chage -M 90 -W 10 <username>

-to set to bydefault we have to change /etc/login.defs file:
         vi /etc/login.defs | grep PASS
         then make changes to :  PASS_MAX_DAYS 90
                                 PASS_MIN_DAYS 10
                                 PASS_MIN_LEN 6
                                 PASS_WARN_AGE 10
