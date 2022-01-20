# Bash-info

## Useful bash commands


Change directory
`cd`

See which directory you are in
`pwd`

List all files in the directory you are in
`ls`
See Permisions for files
`ls -l`
Show hidden files also
`ls -la`
See Permisions for files
`ls -lsah`



## HELP

Use the flag 
`--help`
Example `pwd --help`
## FLAGS

`-` flag = short version example `ls -a`
`--` flag = long version example `ls --all`

Pass parameters to flags
Example show all directorys but ingore snap
`ls --ignore=snap`  or `ls --ignore snap` or `ls -I snap` or do now show ubuntu folder `ls --ignore ubuntu /home` or `ls -ignore=ubuntu /home`

## Tilda ~
Goes to home directory `cd ~`

## Slash /
Goes to root `cd /`


## Tab completion
Use tab to complete to the file name
`cat i` PRESS TAB will autocomplete to `cat index.html` if you have that file in your directory


## Reverse Search
Find old commands that you wrote from latest to oldest
Press CTRL + R and search for the command. Press CTRL + R to find the next

## Bash history

If you wrote a secret in the terminal remove it from the history
`.bash_history`
Is located in in your home directory `~/.bash_history`

## !! Bang BANG

Runs the latest command
example if you wrote `echo hello`
and then you type `!!`
it will run `echo hello`again
use `sudo !!` to execute with sudo permisions

## SHORTCUTS

CTRL + A  -takes you to begging of the line
CTRL + E  -takes you to the end of the line
CTRL + K  - Delete/yank everything after the cursor
CTRL + U  - Delete/yank everything before the cursor
CTRL + Y  - paste everthing you "yanked"
CTRK + L  - Clear the screen
CTRL + R  - Reverse search through history
Shift + CTRL + C  - Copy
SHIFT+CTRL+V      - PASTE


## Signals
Send a nofication to the program

CTRL + C - SIGINT - Interrupt what the program is doing and stop
CTRL + D - SIGQUIT - Quits the program. sometimes works. Try `exit` closes the terminal

SIGTERM if you use `kill` program it sends SIGTERM to the program to kill it

SIGKILL if you want to kill a program NOW execute `kill -9`or `kill -SIGKILL`
to see more signals run `kill -l`


## Text editors
### nano
`nano textfile.txt` creates a text file with nano
`^`represents CTRL example CTRL+ G is Help in the menu
`M-` is the meta key. ALT on windows Option on MAC
CTRL - O Write out/ Will save the file
CTRL - X Exit Nano

### Vim Vi IMproved
`vim textfile.txt`
Shortcuts
Press ESQ
i - Insert mode. Start writing
:d - Delete a line where the cursor is
:d3 - Delete three lines from the cursor
:help tutor - Learn to use vim
:w - save your file
:q - quit your file 
:q! - quit without saving
:qa! - will quit without saving if nothing else works
:wq - save and quit the file

### Interaction with files
`less` - read the file, quit with by press `q`, `/`to search .press `n` to go to the next. `N`to prevoius
`man`- too see manual
`cat` - reads the file and outputs in the the standard output
`head` - read the 10 first lines of the file `head -n 3 yourfile.txt` show just first 3 lines
`tail` - read the 10 last lines of the file `tail -n 3 yourfile.txt` show just first 3 lines
`mkdir` - create new folder/directory `mkdir -p create/a/folder/for/every/name`
`rm` - remove a file  `rm file.txt` or `rm -r folder` remove with confirmation or remove forcefully `rm -rf folder`
`cp` - copy a file `cp file.txt file2.txt` `cp file2.txt` or to copy to a folder `cp file.txt folder/` or  to copy a folder an everything  in  it to another folder`cp -R source-directory destination-directory`
`mv` - move a file/folder to another place or rename it `mv fil.txt newfil.txt`
`tar` - stuck files togetether  to a single tar file `tar -cf archive.tar file1.txt file2.txt` to compress use `tar -zcf archive.tar.gz file1.txt file2.txt` to unzip write `tar -xzf archive.tar.gz -C destination-folder`

### WILDCARDS

to remove many files with a wildcard forexample  matches only 1 charachter`rm file*.txt` or `rm file?.txt` to remove everything but not file.txt
or to show files `ls file*.txt` or `ls file?.txt`
`ls file[1-5].txt` - matches file1.txt file2.txt file3.txt file4.txt file5.txt
`ls file[^1-5].txt` - Do NOT match file1.txt file2.txt file3.txt file4.txt file5.txt

## TO create many files
`touch file{1,2,3}.txt` - creates file1.txt file2.txt file3.txt or `touch file{ONE,TWO,THREE}.txt`
`touch file{0..10}.txt` - creates files file1.txt tp file10.txt
`touch file{a..z}.txt - create filea.txt - filez.txt
`touch file{0..100..2}.txt` create every other number from  0 - 100 
`touch {100..0..5.}.txt` - create files with every 5th number
`touch{a..z}{1..5}.txt` - create files a1.txt a2.txt etc

## STREAMS AND PIPES

stddin, stdout and stderr
Replaces the content in the file `>`
`echo "Will get the output to the file and not the stdout" 1> new-file.txt` - replaces "Will get the output to the file and not the stdout" in to new-file-txt 

`cat new-file.txt 1> another-new-file-txt`

To append to a end of the end of the file use `>>`
`ls -lsah 1>> ls.txt` - Appends the outpout to ls.txt
To redirect an "error" stderr `2>`
`cat fileblablaDoesntexist.txt 2> error-log.txt` - Will out out the error

`ls -lsah 1> stdout.txt 2> stderr.txt` - output stdout to stdout.txt and errors to stderr.txt
or if you want put in same file use `ls -lsah 1> ls.txt 2> ls.txt`
or just `ls -lsah > ls.txt` will output both stdout and stderr to ls.txt 
or `ls -lsah >> ls.txt` to append both stdout stderr to ls.txt

## /dev/null
`ls -lsah 1> /dev/null` - Will throw all stdout to the trash and just

## stdin
You can direct the contents of a file into a program
`cat < ls.txt`
`grep "error-log.txt" < ls.txt` - will find error-log-txt in ls.txt

## using stdin & stdout
`grep "error-log-txt" < ls.txt 1> ls2.txt 2> /dev/null` throw away errors

## Pipes
takes stdout and put it in stdin
`cat ls.txt | grep "error-log.txt` - finds error-log.txt in the output of ls.txt
`ps aux | grep "ps aux"` - find just aux from all the processes
`yes n | rm -i *.txt` - answers no to all removals 

## Users, Grpups & Permissions

`whoami` - will output the current user

## user permissionss


























