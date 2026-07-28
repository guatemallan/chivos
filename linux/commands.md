# LINUX / UNIX commands

## | (Pipe)
> Concatenates commands, sending output from the left command to the right command as input.

## cat
> `cat filename | tr ‘\’ ‘\n’ > newfile; mv newfile filename`
Replaces every occurrence of \ for \n in newfile. Then it 
will replace the original file with the new one (Command Stacking).

## chmod
>**chmod** est une commande utilisée dans les systèmes Unix et Unix-like pour modifier les permissions d'accès des fichiers. Elle permet de définir qui peut lire, écrire ou exécuter un fichier. La commande chmod gère trois types de permissions :
> - Lecture (r) : Permet de lire le contenu du fichier.
> - Écriture (w) : Permet de modifier le contenu du - fichier.
> - Exécution (x) : Permet d'exécuter le fichier comme un programme.
> - (*-*) : pas de permissions
> ![Interpreter les permissions](/linux/commands.chmod.01.png)
>
>**Mode numérique**: 
> - 4 : lecture
> - 2 : écriture
> - 1 : exécution
> - 0 : aucun
> ![mode numérique](/linux/commands.chmod.02.png)
>
> `chmod u+r fichier.txt`
Ajoute la permission de lecture pour le propriétaire.
> `chmod g-w fichier.txt`
Retire la permission d'écriture pour le groupe.
> `chmod o+x fichier.txt`	Ajoute la permission d'exécution pour les autres.
> `chmod 644 fichier.txt`
Définit les permissions à lecture et écriture pour le propriétaire, et lecture pour le groupe et les autres.

## df
> `df -hl`
Disc usage information

## Find
> `find . -name '*.xml'`
The find command in Unix is used to search for files and directories based on specific criteria such as name, type, size, or modification date. It recursively scans the specified directory and its subdirectories to locate matching files.

## grep
> `grep text`
Returns every line from a string that contains the text passed as parameter.

## History
> `history` 
Lists and annotates the last 1000 commands issued in the terminal emulator. Each command has a number associated with it.
> `history 20`
Constrain the amount of results to a specific number. This is useful if you know roughly when a command you are looking for was issued. You should see only the last 20 results listed.
> `!20`
This will reissue the coomand on the history list with the number 20. **Note**: There's no space between the exclamation mark and the number. 

## ls
> `ls`
Prints a list of files and sub directories on the current directory. 
> `ls -lt`
Prints a tabbed list of files with properties of the current dir.
> `ls -lt | awk ‘{print $6, $7, $8, $9}’ > rob`
Awk gets columns 6 trough 9 and puts them in a file called rob.

## man
> Gives you a manual on how to use some commands from the console.

## Memory usage information
> `/usr/sbin/prtconf | grep Memory`

## nohup
> Runs your command in the background.

## NPM
> `npm` est le gestionnaire de paquets par défaut pour l'environnement d'exécution JavaScript Node.js. Il permet de gérer les dépendances des projets et d'accéder à un vaste registre de package

### npm list
> `npm list -g --depth=0`
Lists NPM installed packages. `-g` indicates the command to search in all users's directories, without it only searches in current. `--depth=0` indicates the command to not include dependencies. 

## ps
> Lists process running on the box

## Reverse search
> `ctrl+r`
Type a search term and you should see the last command issued that contained this term. For example we added the search term sudo to show the previous commands issued with sudo privileges. 

## RPM
> RPM, the Red Hat Package Manager, is used to manage packages on Red Hat-based distributions like CentOS and Fedora. It’s a powerful tool for listing and querying installed software with detailed information.

### rpm qa
> `rpm qa`
`rpm qa | grep node`
Queries the installed packages.

## sed
> `sed -e ‘s/Mounted on/Mounted_on/g’ test > test.tmp`
Replaces every occurrence of Mounted on for Mounted_on on the file ‘test’ and puts the result into test.tmp.

## sleep
> Sleeps the console for the number of seconds passed as parameter.

## sudo
> Use permissions from a higher user

## tail
> Mostrar las ultimas lineas de un archivo 
> `tail ./myFile.txt`
> `tail -100 ./myFile.txt` en versiones anteriores, muestra las ultimas 100 lineas. La sintaxis actual es `tail -n 100 ./myFile.txt`.
> `tail +100 ./myFile.txt` muestra las lineas desde la linea 100 hasta el final del archivo. La sintaxis actual es `tail +n 100 ./myFile.txt`.
> `tail -f ./myFile.txt` muestra las ultimas 10 lineas y se mantiene monitoreando el archivo, mostrando lineas mientras se agregan.
> `tail -v ./myFile.txt` muestra las ultimas 10 lineas del archivo precedido por su nombre. 
> `tail ./myFile.txt ./myFile2.txt` muestra las ultimas 10 lineas de cada archivo. 

## Uptime
> `uptime`
You can use the uptime command in Unix to check how long the machine has been running. It will display the current time, how long the system has been up, the number of users logged in, and the system load averages.

## Which
> `which node`
This command searches the directories specified by the PATH environment variable and displays the full path of the executable file associated with the given command.
