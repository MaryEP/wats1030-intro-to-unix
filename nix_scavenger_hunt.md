# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. 
Use the `pwd` command to find your "path to working directory"--your current location in the 
filesystem of your devbox. 
*Paste the output of the `pwd` command here: 
>> home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this 
directory. 
*What directories and files do you see when you run `ls`? 
>> LICENSE  challenge_files  nix_scavenger_hunt_stretch.md README.md nix_scavenger_hunt.md

* You can use *options* to modify how a command runs. 
Try using `ls -alh` to see the contents of your current directory. 
*How are the results different when you use the `-alh` options? 
>>ls shows the file names separated by tabs.  
>>ls -alh shows date, time, filename, size and other data, each on its own line.

* The `man` ("manual") command tells you more about how any given command works. 
(*WARNING:* CodeAnywhere does not support the man command. You can click the following link
to complete this task: http://linux.die.net/man/)
Run `man` to see instructions about how to use `man`. 
Then use `man` to learn what the `a`, `l`, and `h` options mean when used with 
the `ls` command. Write down what those options do.
>> ls -a: show all files including hidden
>> ls -l: use long list format
>> ls -h: show in human readable format

* Commands can also take *arguments*, which are usually the names of files or locations 
that you want the command to work with. Try running `ls /` to see what files are in the 
*root* directory of the filesystem. *What files and directories do you see listed?
>> bin  dev  fastboot  lib  media  opt  root  sbin  sys  usr  boot  etc  home  lib64  mnt
proc  run  srv  tmp  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. 
`/` indicates the *root* of the filesystem, meaning the top-most directory in the 
filesystem hierarchy. Use the `cd` ("change directory") command to move to the root 
directory. (Hint: Use `man` to look up the `cd` command if you have any issues) 
*Then run `pwd` and paste the output here: 
>> "/" (at root directory)

* Another special shortcut in Unix is the `~` location. This indicates the *user root* 
directory, meaning the top-most directory in the hierarchy that comes below your user 
account. Use `cd` to move to `~`. Run `pwd` and paste the response here: 
>> /home/cabox

* Change directory into the `challenge_files` directory. Use `ls` to find only the files 
with a `.demo` pattern. How many files do you find? 
>> Three: 2015_special_stuff.demo, cloaked-wookie.demo, scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?
>> cd challenge_files
Press the up arrow on your keyboard. What just happened?
>> Command line reverted to previous command.

* Press the up arrow a few more times. *What do you see? 
>> It selects commands I gave it previously. that's cool. 
Run the `history` command. What do you see? 
>> A list of commands! 

### Observing the System

* Discover what account you are logged into using the `whoami` command. 
*What username are you currently using?* 
>> cabox

* Discover who else is on your system with the `who` command. 
*Are any other users using your system? If so, list them here:*  
>> No, just cabox   pts/0 Apr 4 15:44 (54.186.244.104)

* How long has your system been running? Use `uptime` to see, and paste the result here:
>> 15:50:17 up 57 min, 1 user, load average: 0.00, 0.00, 0.00

Run `ps aux` and review the results. 
(Hint: Use `man` to learn more about the `ps` command and options.) 
*How do you interpret what you see here?*
>> It displays USER, PID %CPU %MEM VSZ RSS TTY  STAT START TIME COMMMAND - hard to make out
data since unclear where columns begin and end.  Shows hours and minutes working and 
server info.

* Run `top` and review the results. 
(Hint: You may need to use `ctrl-c` to get out of this app.) 
>> Thanks for the way out!

How do you interpret what you see here? 
>> Dynamic data on info similar to the above, in columns.
Interesting that it reports 2 users! But users are root, cabox, www-data, and syslog.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. 
Use the `*` wildcard to find all the files that have the word "credit" in the 
filename. *How many files did you find?
>> With the wildcard, I got 'permission denied', but then I used the find command and 
found 2 files:  credit_cards.txt, and credit-cards2.txt.

* Use the `more` command to view one of the `credit_cards` files you just discovered
(Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. 
Use your keyboard arrows to move up/down.) 
*What is the date in the file you have viewed? 
>> Last updated: 01-15-2015.

* Use the `find` command to search for files more effectively. 
Search the sub-directories under `challenge_files` to find the location of the 
file named `modi_laboriosam.txt`. Where is that file located? 
>> located in challenge_files/tmp:  tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. 
Use `grep` on all the `.user` files in `challenge_files` to find which files 
contain "WA" (the abbreviation for Washington state). 
*How many files did you find?  
>> Two: Britt-Erdman.user:O'Harachester, WA 37261, and Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in 
a file somewhere under the `challenge_files` directory. *Paste the result showing 
the file and line where the word "Waldo" shows up. 
>> (grep -r 'Waldo')
"serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi 
Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectet
ur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia."  

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for 
further analysis, reference, or processing. Try running `ls > files.txt`and see all the .user files)
Notice that the file `files.txt` was created. View that file using `more`. 
What do you see in the `files.txt` file?*
>> Options:                                                  
  -d        display help instead of ring bell             
  -f        count logical, rather than screen lines       
  -l        suppress pause after form feed                
  -p        suppress scroll, clean screen and disblay text
  -c        suppress scroll, display text and clean line ends                                                       
  -u        suppress underlining                          
  -s        squeeze multiple blank lines into one         
  -NUM      specify the number of lines per screenful     
  +NUM      display file beginning from line number NUM   
  +/STRING  display file beginning from search string match                                                         
  -V        output version information and exit  

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files 
scroll by very quickly. Sometimes it would be better to get the results in a 
paginated format. Try running `ls -alh | more`. *Describe what you see when you 
run `ls -alh | more`. 
>> I see the long list of user name files with date and read-write indicators, but more 
allows me to see them one at a time by pressing enter at --More-- command.

* Earlier, when you viewed the list of active processes on your devbox using 
`ps aux`, the list was probably really long. You can make this list more manageable
by using the pipe (`|`) to filter the results of `ps` using `grep`. 
Run `ps aux | grep <your_username>` to see what processes are running for your 
specific user. *Paste the list of processes that reference your username here:*
>> cabox@box-codeanywhere:~/workspace/challenge_files$ ps aux |
 grep cabox                                                 
root       515  0.0  0.6  63876  3348 ?        Ss   10:30   
0:00 sshd: cabox [priv]                                     
root       516  0.0  0.6  63876  3340 ?        Ss   10:30   
0:00 sshd: cabox [priv]                                     
root       519  0.0  0.6  63876  3496 ?        Ss   10:30   
0:00 sshd: cabox [priv]                                     
cabox      521  0.0  0.2  63876  1452 ?        S    10:30   
0:00 sshd: cabox@notty                                      
cabox      522  0.0  0.2  64012  1488 ?        S    10:30   
0:00 sshd: cabox@notty                                      
cabox      523  0.0  0.1  12784   832 ?        Ss   10:30   
0:00 /usr/lib/openssh/sftp-server                           
cabox      524  0.0  0.1  12784   880 ?        Ss   10:30   
0:00 /usr/lib/openssh/sftp-server                           
cabox      525  0.0  0.2  63876  1472 ?        S    10:30   
0:00 sshd: cabox@pts/0                                      
cabox      526  0.0  0.8  20624  4548 pts/0    Ss   10:30   
0:00 -bash                                                  
cabox      734  0.0  0.2  15520  1140 pts/0    R+   10:38   
0:00 ps aux                                                 
cabox      735  0.0  0.1   8816   764 pts/0    S+   10:38   
0:00 grep --color=auto cabox 

--END--