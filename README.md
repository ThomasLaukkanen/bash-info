# CHEATSHEET BASH
CREDITS to Brian Holt from frontendmasters. These are commands learned from the great course introduction to the linux command line .

## Useful bash commands

`cd` - Change directory

`pwd` - See which directory you are in

`ls` -List all files in the directory you are in

`ls -l` - See Permisions for files

`ls -la` - Show hidden files also

`ls -lsah` - See Permisions for files



## HELP

Use the flag  `--help`

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
`cd /` - Goes to root 

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

`touch file{a..z}.txt` - create filea.txt - filez.txt

`touch file{0..100..2}.txt` create every other number from  0 - 100 

`touch {100..0..5.}.txt` - create files with every 5th number

`touch{a..z}{1..5}.txt` - create files a1.txt a2.txt etc

## STREAMS AND PIPES

stddin, stdout and stderr -Replaces the content in the file `>`

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
`whomami` - see which user you are

`cat /etc/passwd` - see all users

`sudo useradd thomas` - create user thomas

`sudo passwd thomas` - create password for thomas

`su thomas` - change user to thomas

`sudo userdel thomas` - delete user

`ls -l` - see permissions example d rwx rwx rwx | d or -  means that is a directory or file. | r = read  w = write x=execute | user - group - everyone

`sudo chown ubuntu:thomas file.txt ` - change owner of file group:user 

`sudo chmod u=rw,g=rw,o=rw file.txt` - u = user(read write) g = group(read write) o = other(read write)

`chmod 777 file.txt` - read write execute for user,group,other DANGEROUS ALL PERMISSIONS

`chmod +x file.txt` - adds exection permission for user,group,others (works with r and w also)

`chmod -x file.txt` - remove execetion permission for user,group, others (works with r and w also)

## Environments
  

`printenv` - see all envoirment variables'


`echo hello my name is $USER` - hello my name is root

`USER=thomas echo hello my name is $USER` - hello mt name is thomas(just for this command)

`GREETING=Hello this is a session variable` - Will stay allive until you close the terminal. use $GREETING

`/etc/environment`- will modify every users environment(BAD)

`/etc/profile`-  will modify every users environment(BAD)

`/etc/bashrc` -  will modify every users environment(BAD)

`.bashrc`-  in your home directory - Add your envoirment variables here export VARIABLE=value

`.bash_profile` - add this `if [ -f ~/.bashrc ]; then
    source ~/.bashrc
fi`

## Proceses

`ps` - see all processes running

`kill -s SIGKILL <pid>` - kill the process with pid

 `kill -9` - same as above
 
`ps aux` - shows all processes running  from everyone ,including all system processes

 `ps aux | grep ps` - find a process includes to things that have just `ps`  
 
  `sleep 200 &` - & MAKES THE PROCESS RUN IN BG GOOD FOR proceces or scripts that takes long time
  
  `jobs` - see what is running
  
  `bg 1` - resume the stopped proceces in the background
  
  `fg 1` -reattach to the process
  
  `jobs -l` - if you need the pid to kill it
  
  
  ## EXIT CODES
  `date` - shows date
  
  `echo $?` - how did the last program exit? 0 = exicited succesfully
  
  ### exit codes
    0: means it was successful. Anything other than 0 means it failed
    
    1: a good general catch-all "there was an error"
    
    2: a bash internal error, meaning you or the program tried to use bash in an incorrect way
    
    126: Either you don't have permission or the file isn't executable
    
    127: Command not found
    
    128: The exit command itself had a problem, usually that you provided a non-integer exit code to it
    
    130: You ended the program with CTRL+C
    
    137: You ended the program with SIGKILL
    
    255: Out-of-bounds, you tried to exit with a code larger than 255
`
  
  ## Run if first one succeeds
  `touch status.txt && date >> status.txt && uptime >> status.txt` - runs three commands in a row if previous command is succeful USE `&&`
  
  ## Run if first onee fails
  
  `false || echo IT FAILED` - USE `||` if you want to run a command after something failed
  
  ## Always run
  
  false ; true ; echo everything runs - USE `;` to always run
 
  ##Subcommands
  echo this show who the user is wuth a subcommand $(whoami) - use `$(yoursubcommand)`
  
  echo $(date +%x) - $(uptime) >> log.txt - log the date and uptime to log.txt
  
  
  ## SSH

  `ssh-keygen -t rsa` - generate a new ssh key
  
  `ls ~/.ssh` - idrsa(privatekey) idrsa.pub(public key)
  
  `cat ~/.ssh/id_rsa.pub` - copy this public key
  
  `vi ~/.ssh/autorized_keys` - paste the public key to the machine you want to connect to
  
  `chmod 700 ~/.ssh` - give the right permissons
  
  `chmod 600  ~/.ssh/authorized_keys` -give the right permissons
  
  `ifconfig` - find your ip that you can connect to
  
  `ssh <user>@<ip adress>` - connect to the target with the user and ip
  
  ## SFTP
  sftp <user>@<ip> - good for moving files from your computer to the host computer use `l` infront of the command you want to run on the targets computer
  
  `lpwd` -pwd on target machine
  
  `lls` - ls on target machine
  
  `get` - download from target machine
  
  `put` - upload something to target machine
  
  
  ### Servers
  `sudo less /var/log/auth.log` - see who tried to login to your server
  `sudo tail -f /var/log/auth.log` - see who tried to login to your server with `-f` follows
  
  ### ADD SSH FOR USER
  `usermod -aG sudo $USERNAME` - create a new user $USERNAME is your naew name
  `cd ~` - change to root
  
  `mkdir -p ~/.ssh` - create directory if it dosnt exist
  
  `vi ~/.ssh/authorized_keys` - open
  
`ssh <user>@ip` - log in with your new user
 
 `chmod 644 ~/.ssh/authorized_keys` - change permissions
`sudo vi /etc/ssh/sshd_config` - disable root login CHANGE `PermitRootLin` no
  `sudo servive sshd restart` - restart ssh deamon
  
  ## Nginx
  Reverse proxy
  Web server
  Proxy server
`sudo apt install nginx` - install nginx x on the server
  
`sudo service nginx start` - start nginx
  
`sudo less /etc/nginx/sites-available/default` - show nginx configuration
  
`sudo vi /var/www/html/index.html` - default page
  
`sudo apt install nodejs npm` - install nodejs and npm
  
 `sudo apt install git' - install git
  
 `sudo chown _R $USER:$USER /var/www` - change permissions
 
 `mkdir /var/www/app` - create app directory
  
`cd /var/www/app` - change to the directory
  
`git init` - initialize git repo
  
`mkdir -p ui/js ui/html /ui/css` - create three directories
  
 `touch app.js` - create app.js files
  
  `npm init` - intialize project
  
  `npm i express --save` - install express
  
`vi app.js` - change app.js file create your express server
  
`node app.js` - run your app
 
`sudo vi /etc/nginx/sites-available/default` - change PORT to 3000

![image](https://user-images.githubusercontent.com/66567520/151360453-65547408-1fe2-4048-8f79-da39f01b057b.png)

`sudo service nginx reload` - restart yourg nginx server
  
`node app.js` - start your server again

  ## Process managaer
   keep the processes alive
  
  `sudo npm i -g pm2` - install process mananger globaly
  
  `pm2 start app.js` - start your server with pm2 in the background
  
  `pm2 startup` - setup auto restart the pm2 when you restart your server
  
  `pm2 status` - see status of server
  `pm2 save` - save file - save the config for startup
  
  ## github repo
   Create new repository
  
  `cd ~/.ssh/` - change to .ssh folder on the server
  
  `ssh-keygen` -create new key
  
  `cat id_rsa.pub` - copy key to github settings/add new ssh key
  
  `cd /var/www/app` - move to app directory on server
  
  `git remote add origin git@github.com:ThomasLaukkanen/nginx-server.git` - add ssh origin to your repo
  
`vi .gitignore` - add node_modules/
 
 `git commit -am 'modified' `- add all files that are modified
  
`git push origin master` - push files
  
`clone git@github.com:ThomasLaukkanen/nginx-server.git` - clone the repo to your computer and work from there. Pull changes on your server

  ## Find things on your server
  `find /var/log/nginx -type f -name "*.log*"`  - find all logg files
  
  `find / -type d -name log` - find all directories with the name log
  
  `zgrep FILE` - search inside gzip file
  
  `ps aux | grep node`
  
  ![image](https://user-images.githubusercontent.com/66567520/151387118-e246c44b-03ec-439b-894b-4685668dd0d4.png)
  
  ## nginx
  
  ![image](https://user-images.githubusercontent.com/66567520/151388361-765853a8-0b58-4382-be6c-471e83c7e1e9.png)
  
  ![image](https://user-images.githubusercontent.com/66567520/151388671-be683f52-0c97-449f-9bdb-20df3e64aa0a.png)
  
![image](https://user-images.githubusercontent.com/66567520/151389060-131707a4-2f42-4947-a56d-d944fb92436e.png)
 
 ## Security
  --SSH
  --Firewalls
  --Updates
  --Two facton authentication
  --VPN

  `sudo apt install unattended-upgrades` - install unattended upgrades
  
  `less /etc/apt/apt.conf.d/50unattended-upgrades`
  
`sudp apt install nmap` -install portscanner
  
  `nmap YOURIP` - scan open ports
  
  `nmap -sV IPADRESS` -more details
  
`less /etc/services` - see ports

  ![image](https://user-images.githubusercontent.com/66567520/151450874-3e2d4dd9-06ce-4a4b-82a2-c7868f42d1e5.png)
  
  `sudo ufw status` - see if firewall is running
  
  `sudo ufw enable`- start firewall
  
  `sudo ufw allow ssh` - allow ssh
  
  `sudo ufw allow http` - allow http
  
  `curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh - download node
  
  `sudo bash nodesource_setup.sh` - run bashscript
  
`sudo apt install nodejs` - install node
  
`sudo npm update -g` - update packages
  
## HTTP

  ![image](https://user-images.githubusercontent.com/66567520/151871390-167f6b54-fb9a-493b-be27-4ec97ae5790f.png)
  
  Get a https certifcate
  https://certbot.eff.org/
  





