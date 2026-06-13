SED: stream editor, took all content as a input from a file and perform task which expression we will give it

-to print a specific line : sed -n '3p' rec.txt
-to print a last line     : sed -n '$p' rec.txt
-to print a range lines   : sed -n '3,5p' rec.txt
-to print a line with specific data : sed -n '/Luci/p' rec.txt
-to print multiple expression : sed -n -e '2p' -e '4p' -e '9p' rec.txt
-to print from specific multiple data: sed -n -e '/UAE/p' -e '/UK/p' rec.txt
-to print 4 lines from 2nd line : sed -n '2,+4p' rec.txt
-to print even or odd lines : sed -n '1~2p' rec.txt
-to use expression from a file: sed -n -f ex_file rec.txt         # in ex_file= 3d
                                                                                6d                                                                                    
                                                                                9d

-to replace a word : sed 's/luci/michelle/g' rec.txt        #it is only showing not save in actual file
-to replace a word but only at specific line not all: sed '2 s/USA/uk/g' rec.txt     #2 mean 2nd line
-to replace everything expect specific line : sed '6! s/UAE/Uk/g' rec.txt           #6! mean not on 6th line

-to modify file use any expression with (-i): sed -i '2 s/USA/UAE/g' rec.txt
-print specific data for specific person: sed '/ibtu/ s/USA/UAE/g' rec.txt   # it will search ibtu first then apply

-to delete a line : sed '1d' rec.txt
-to delete last line : sed '$d' rec.txt
-to delete a range : sed '2,6d' rec.txt
-to delete for a specific data : sed '/belgium/d' rec.txt
-to delete an empty line: sed '/^$/d' rec.txt

-to get a specific data and copy them in to a new file: sed '/UK/ w uk_user' rec.txt     #it will filter and make a new file

-to add data after a specific line : sed '3 a 4 ibtu 400' rec.txt     #it will add line after 3rd line
-to add data after a specific word's line: sed '/luci/ a 6 michelle 280' rec.txt 

-to modify a line: sed '4 c 5 luka 680' rec.txt

-to modify on the first line and all data down it: sed '1 i 0 admin 1000' rec.txt     #1 is line number

-to see a hidden special characters: sed -n 'l' rec.txt      # it will show $ which is end of the line
-to customise the view: sed -n 'l 10' rec.txt       #it will only show 10 chracter then on next line

-to print data from another file: sed '3 r test.txt' rec.txt      # it will print data form test after the 3rd line

-to print only one time a specific data: sed '/USA/ q' rec.txt

-to print a linux expression(date): sed '2 e date' rec.txt       #it will print date on 2nd line
                             (pwd): sed '3 e pwd' rec.txt        #it will print current position
-to see a line number: sed '=' rec.txt
-to print words with specific chracter: sed -n '/b/p' rec.txt
-to print set of chracter: sed -n '/[df]p/' rec.txt
-to print range of chracter: sed -n '/[A-D]p/' rec.txt

-to print data of a specific class: sed -n '/[[:digit:]]/p' rec.txt    #it will only print digits
                                    sed -n '/[[:upper:]]/p' rec.txt    #it will only print uppercase
                                    sed -n '/[[:lower:]]/p' rec.txt    #it will only print lowercase
                                    sed -n '/[[:space:]]/p' rec.txt    #it will only print lines with space
                                    sed -n '/[[:punct:]]/p' rec.txt    #it will only print lines with punctuation
                                    sed -n '/[[:alpha:]]/p' rec.txt    #it will only print line with alphabets