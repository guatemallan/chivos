 # Crontab
 
 ## Programación de trabajos 

```
.------------- Minuto (0 - 59)
|  .---------- Hora   (0 - 23)
|  |  .------- Dia    (1 - 31)
|  |  |  .---- Mes    (1 - 12)
|  |  |  |  .- Dia semana (0-6, Dom = 0)
|  |  |  |  |               
15 10 *  *  1  usuario  /comando/a/ejecutarse.sh
```
Esta tarea se ejecuta todos los lunes a las 10:15 am. 

## Comandos

> `crontab -l > /some/location/filename`
To backup crontab from current user to a file

> `crontab /some/location/filename`
To restore the crontab of the current user from a file

> `crontab -l -u root > ./root.crontab`
To backup crontab from user root

> `crontab -u root ./root.crontab`
To restore the crontab of the user root from the file "root.crontab" on the current directory
