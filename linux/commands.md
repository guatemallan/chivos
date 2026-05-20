# LINUX / UNIX commands

## chmod
>**chmod** est une commande utilisée dans les systèmes Unix et Unix-like pour modifier les permissions d'accès des fichiers. Elle permet de définir qui peut lire, écrire ou exécuter un fichier. La commande chmod gère trois types de permissions :
> - Lecture (r) : Permet de lire le contenu du fichier.
> - Écriture (w) : Permet de modifier le contenu du - fichier.
> - Exécution (x) : Permet d'exécuter le fichier comme un programme.
> - (*-*) : pas de permissions
> ![Interpreter les permissions](/linux/commands.chmod.01.png)

>**Mode numérique**: 
> - 4 : lecture
> - 2 : écriture
> - 1 : exécution
> - 0 : aucun
> ![mode numérique](/linux/commands.chmod.02.png)

> `chmod u+r fichier.txt`
> Ajoute la permission de lecture pour le propriétaire.
> `chmod g-w fichier.txt`
> Retire la permission d'écriture pour le groupe.
> `chmod o+x fichier.txt`	Ajoute la permission d'exécution pour les autres.
> `chmod 644 fichier.txt`
> Définit les permissions à lecture et écriture pour le propriétaire, et lecture pour le groupe et les autres.

## Find
> `find . -name '*.xml'`
> The find command in Unix is used to search for files and directories based on specific criteria such as name, type, size, or modification date. It recursively scans the specified directory and its subdirectories to locate matching files.

## History
> `history`
> lists and annotates the last 1000 commands issued in the terminal emulator. Each command has a number associated with it.

> `history 20`
> Constrain the amount of results to a specific number. This is useful if you know roughly when a command you are looking for was issued. You should see only the last 20 results listed.

> `!20`
> This will reissue the coomand on the history list with the number 20. **Note**: There's no space. 

## Reverse search
> `ctrl+r`
> Type a search term and you should see the last command issued that contained this term. For example we added the search term sudo to show the previous commands issued with sudo privileges. 

## Uptime
> `uptime`
> You can use the uptime command in Unix to check how long the machine has been running. It will display the current time, how long the system has been up, the number of users logged in, and the system load averages.


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

