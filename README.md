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
i - Insert mode. Start writing


















