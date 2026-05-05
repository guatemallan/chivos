# UNIX / LINUX commands

COMANDO |USO                    |DESCRIPCION
:--:    |--                     |--
find    |`find . -name '*.xml'` |The find command in Unix is used to search for files and directories based on specific criteria such as name, type, size, or modification date. It recursively scans the specified directory and its subdirectories to locate matching files.
uptime  |`uptime`               |You can use the uptime command in Unix to check how long the machine has been running. It will display the current time, how long the system has been up, the number of users logged in, and the system load averages.

  

ps
Lists process running on the box 
 
| (Pipe)
Concatenates commands, sending output from the left command to the right command as input.
grep
Returns every line from a string that contains the text passed as parameter.
nohup
Runs your command in the background.
sleep
Sleeps the console for the number of seconds passed as parameter.
ls &

df -hl
Disc usage information
/usr/sbin/prtconf | grep Memory
Memory usage information
sudo
Use permissions from a higher user
ls -lt | awk ‘{print $6, $7, $8, $9}’ > rob
Ls -lt prints a tabbed list of files with properties of the current dir. Awk gets columns 6 trough 9 and puts them in a file called rob.
sed -e ‘s/Mounted on/Mounted_on/g’ test > test.tmp
Replaces every occurrence of Mounted on for Mounted_on on the file ‘test’ and puts the result into test.tmp.
cat filename | tr ‘\’ ‘\n’ > newfile; mv newfile filename
Replaces every occurrence of \ for \n in newfile. Then it will replace the original file with the new one (Command Stacking).
man
Gives you a manual on how to use some commands from the console.
find

