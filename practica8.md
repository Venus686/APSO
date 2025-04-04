# CONTENIDO
• /etc/passwd\
• /etc/shadow\
• /etc/group\
• /etc/adduser.conf\
• adduser\ -> creación de usuarios
• addgroup\
• usermod\
• deluser\
• delgroup\
• chsh\
• chage\
• ulimit\
• quotachek\
• quotaon\
• quota\
• edquota\
• repquota

man 5 password -> para ver la sección 5 de password\
man shadow -> te da directamente los campos que aparecen

### EJERCICIO 1
1. Visualice el contenido del fichero /etc/passwd y el fichero /etc/shadow. Identifique los distintos campos
```bash
 lucia@lucia-VirtualBox:~$ sudo cat /etc/shadow
```
### EJERCICIO 2
2. Visualice el contenido del fichero /etc/group Identifique los distintos campos.
```bash
 lucia@lucia-VirtualBox:~$ sudo cat /etc/shadow
 man group -> lista de usuarios que pertenecen a ese grupo
 man gshadow
```
fichero de contraseñas de los grupos sudo cat /etc/gshadow

### EJERCICIO 3
3. Visualice el contenido del fichero /etc/adduser.conf. Identifique las distintas opciones.\
man useradd
```bash
man adduser-> puede crear tanto grupos como usuarios. 

```

### EJERCICIO 4
4. Añada un nuevo usuario de sistema llamado usuariosistema. Compruebe los archivos /etc/passwd y /etc/group.
```bash
lucia@lucia-VirtualBox:~$ sudo adduser --system usuariosistema
lucia@lucia-VirtualBox:~$ grep usuariosistema /etc/passwd

```

### EJERCICIO 5
5. Cree un nuevo grupo de usuarios llamado practica8. Compruebe el fichero
/etc/group.
```bash
man adduser-> puede crear tanto grupos como usuarios. 
lucia@lucia-VirtualBox:~$ grep usuariosistema /etc/passwd
lucia@lucia-VirtualBox:~$ sudo addgroup practica8
lucia@lucia-VirtualBox:~$ grep practica8 /etc/group
```

### EJERCICIO 6
6. Modifique el fichero /etc/adduser.conf para que todos los nuevos usuarios creados se añadan por defecto al grupo practica8.
```bash
man adduser.conf
lucia@lucia-VirtualBox:~$ more /etc/adduser.conf adduser.conf
lucia@lucia-VirtualBox:~$ more /etc/adduser.conf 

```

### EJERCICIO 7
7. Cree dos usuarios con nombres user1 y user2. Compruebe el fichero /etc/passwd.
```bash
lucia@lucia-VirtualBox:~$ sudo adduser user1
lucia@lucia-VirtualBox:~$ sudo adduser user2
info: Añadiendo el usuario `user2' ...
info: Selecting UID/GID from range 1000 to 59999 ...
info: Añadiendo el nuevo grupo `user2' (1002) ...
info: Adding new user `user2' (1002) with group `user2 (1002)' ...
info: Creando el directorio personal `/home/user2' ...
info: Copiando los ficheros desde `/etc/skel' ...
Nueva contraseña: 
CONTRASEÑA INCORRECTA: La contraseña tiene menos de 8 caracteres
Vuelva a escribir la nueva contraseña: 
passwd: contraseña actualizada correctamente
Cambiando la información de usuario para user2
Introduzca el nuevo valor, o presione INTRO para el predeterminado
	Nombre completo []: usuario2
	Número de habitación []: 6
	Teléfono del trabajo []: 333333
	Teléfono de casa []: 4444
	Otro []: si
¿Es correcta la información? [S/n] s
info: Adding new user `user2' to supplemental / extra groups `users' ...
info: Añadiendo al usuario `user2' al grupo `users' ...


```

### EJERCICIO 8
8. Haga que los usuarios user1 y user2 formen parte también del grupo 100 (users). Compruebe el fichero /etc/group.
```bash
lucia@lucia-VirtualBox:~$ sudo adduser user2 users
grep users /etc/group

grep pract /etc/assuser.conf
```

### EJERCICIO 9
9. Modifique el directorio home del usuario user2 por el de /home/user2b. Haga que se mueva su información al nuevo directorio cuando se cambie.
```bash
man usermod
-m mueve el contenido a home
lucia@lucia-VirtualBox:~$ sudo usermod -d /home/user2b -m user2

```

### EJERCICIO 10
10. Acceda a la cuenta del usuario user2 y compruebe su directorio de usuario. Luego vuelva a entrar con su usuario normal
```bash

```

### EJERCICIO 11
11. Elimine del sistema el usuario user1, haciendo una copia de seguridad de  sus datos en el directorio home y eliminando todos sus ficheros del sistema.
```bash
lucia@lucia-VirtualBox:~$ sudo delsuser --remove-home user2

```

### EJERCICIO 12
12. Añada un nuevo usuario al sistema, llamado user3, asigándole como UID 500 y haciendo que su cuenta esté deshabilitada hasta que le demos una clave.
```bash
ucia@lucia-VirtualBox:~$ sudo adduser --uid 500 -disable -login user3
Option disable is ambiguous (disabled-login, disabled-password)
Unknown option: login
adduser [--uid id] [--firstuid id] [--lastuid id]
        [--gid id] [--firstgid id] [--lastgid id] [--ingroup group]
        [--add-extra-groups] [--encrypt-home] [--shell shell]
        [--comment comment] [--home dir] [--no-create-home]
        [--allow-all-names] [--allow-bad-names]
        [--disabled-password] [--disabled-login]
        [--conf file] [--extrausers] [--quiet] [--verbose] [--debug]
        user
    Add a normal user

adduser --system
        [--uid id] [--group] [--ingroup group] [--gid id]
        [--shell shell] [--comment comment] [--home dir] [--no-create-home]
        [--conf file] [--extrausers] [--quiet] [--verbose] [--debug]
        user
   Add a system user

adduser --group
        [--gid ID] [--firstgid id] [--lastgid id]
        [--conf file] [--extrausers] [--quiet] [--verbose] [--debug]
        group
addgroup
        [--gid ID] [--firstgid id] [--lastgid id]
        [--conf file] [--extrausers] [--quiet] [--verbose] [--debug]
        group
   Add a user group

addgroup --system
        [--gid id]
        [--conf file] [--extrausers] [--quiet] [--verbose] [--debug]
        group
   Add a system group

adduser [--extrausers] USER GROUP
   Add an existing user to an existing group


```


### Ejercicio 13
Cambie la shell por defecto del usuario user3 a ksh. Instale ksh si fuese necesario.
```bash
lucia@lucia-VirtualBox:~$ sudo apt install ksh
lucia@lucia-VirtualBox:~$ which ksh
/usr/bin/ksh
lucia@lucia-VirtualBox:~$ sudo usermod -s /usr/bin/ksh user3
grep user3/etc/psswd

```


### Ejercicio 14
14. Visualice cuando expira su cuenta de usuario
```bash
man chage
lucia@lucia-VirtualBox:~$ sudo chage -l user
```

### Ejercicio 15
15. Haga que la cuenta del usuario user2 expire el 1 de junio de 2023. Compruebe que se ha modificado
```bash
sudo chage -E 2026-07-01 user2
```
### Ejercicio 16
16. Borre el grupo practica8. ¿Qué ocurre?
```bash
sudo delgrpoup practica8
```
### Ejercicio 17
17. Instale el paquete quota.
```bash
lucia@lucia-VirtualBox:~$ sudo apt install quota
```
### Ejercicio 18
18. Visualice los dispositivos montados
```bash
mount
df -> que hay montado en el sistema
partición donde tienes asignado el sistema

```

### Ejercicio 19
19. Modifique el archivo fstab para que permita cuotas de usuarios en /.Después de modificarlo, remonte el sistema de archivos con sudo mount -o remount /.
```bash
lucia@lucia-VirtualBox:~$ sudo cp /etc/fstab /etc/fstab.original
defaults,usrquota 0 1 swap
sudo mount -o remount /
sudo systemctl daemon-reload
```


### Ejercicio 20
20. Chequee el estado del sistema de cuotas
```bash
sudo quotacheck 
sudo quotacheck -umv /
ls /
aquota.user
```
### Ejercicio 21
21. Comprueba la existencia de aquota.user en el directorio /
```bash
h
```
### Ejercicio 22
22. Active las cuotas de usuario
```bash
sudo quotaon -u /
```
### Ejercicio 23
23. Cree un nuevo usuario llamado user4
```bash
h
```
### Ejercicio 24
24. Edite las cuotas del usuario user4, y ponga como limite blando de inodos 120, y como límite duro 150. Si no tiene instalado el editor joe, hágalo antes de editar las cuotas.
```bash
h
```
### Ejercicio 25
25. Visualice las cuotas de todos los usuarios del sistema
```bash
h
```

### Ejercicio 26
26. Establece el periodo de gracia general a 3 días, tanto para bloques como
para inodos
```bash
h
```

### Ejercicio 27
27. Asigne una contraseña al usuario user4 y acceda al sistema con dicho usuario.
```bash
h
```
### Ejercicio 28
28. Compruebe las cuotas
```bash
h
```
### Ejercicio 29
29. Pruebe a superar la cuota establecida para el usuario user4.
```bash
h
```
