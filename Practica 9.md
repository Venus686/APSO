# CONTENIDO
• /etc/default/grub\
• update-grub2\
• dmesg\
• systemctl\
• journalctl\
• pstree\
• cron\
• at\
• shutdown\
- systemdl\
- journalctl\
- uname -a
-lsb_release -a

### EJERCICIO 1 2  3 y 4
1. Copie el fichero /etc/default/grub al mismo directorio pero con
el nombre grub_original

2. Realice las siguientes modificaciones en el menú de arranque de
Grub2:
• Establezca el tiempo de elección del menú a 60 segundos\
• Haga que no se muestren la opción de recovery mode en el menú.\
• Establezca la resolución inicial a 800x600\
• Haga que suene un pitido al aparecer el menú\
• Haga que no aparezca memtest en el menú.

3. Reinicie el sistema y compruebe que los cambios han tenido efecto.
4. Si en lugar del pitido colocamos esta secuencia “410 668 1 668 1 0 1668 1 0 1 522 1 668 1 0 1 784 2 0 2 392 2”, ¿a qué os suena?
```bash
lucia@lucia-VirtualBox:-$ sudo cp /etc/default/grub /etc/default/grub.original \
lucia@lucia-VirtualBox:~$ sudo joe /etc/default/grub \
GRUB_TIMEOUT_STYLE=hidden -> a menu \
GRUB_TIMEOUT=0 -> a 60 \
#GRUB_DISABLE_RECOVERY="true" \
#GRUB_GFXMODE=640x480 -> 800x600 \

/etc/grub.d \
chmod a-x ./20_memtest86+ 

update-grub2 (basandose en los nucleos disponibles y en los ficheros que tengas)\
Para saber si ha funcionado hay que arrancas de nuevo.
```
### EJERCICIO 5
5. Elimine del arranque la versión más antigua que tenga del kernel. Actualice grub y compruebe que ya no está disponible reiniciando el sistema (es posible que en caso de no haber ninguna versión anterior para eliminar tuviera que instalarlo siguiendo el procedimiento descrito en la documentación del tema).\
5. Visualice los mensajes del kernel durante el arranque. Filtre aquellos mensajes que contienen la expresión EXT4.

En mi caso tendría que eliminar vmlinuz-6.11.0-17-generic y todo lo que tuviese esa misma versión.\
```bash
lucia@lucia-VirtualBox:~$ sudo dmesg |more  
lucia@lucia-VirtualBox:~$ sudo dmesg |grep EXT4
[    3.601461] EXT4-fs (sda2): mounted filesystem 89f79d54-c75e-47bb-b528-188f9b2e2ddd ro with ordered data mode. Quota mode: none.
[    4.289287] EXT4-fs (sda2): re-mounted 89f79d54-c75e-47bb-b528-188f9b2e2ddd r/w. Quota mode: none.
```
6. Visualice todos los servicios del sistema cuyo estado sea ‘activo’
```bash
man systemctl
man journalctl
pstree-> arbol de servicios o procesos del sistema
pstree -p (ids)
systemctl --list

```
7. Visualice los mensajes para el servicio NetworkManager en el
registro de Systemd, que contengan la cadena Starting
```bash
lucia@lucia-VirtualBox:~$ systemctl list-units --type=servise --state=active
lucia@lucia-VirtualBox:~$ journalctl -u NetworkManager
lucia@lucia-VirtualBox:~$ journalctl -u NetworkManager | grep starting
```

8. Visualice el target establecido por defecto para aquellos servicios
que no lo indiquen en su fichero de configuración.
```bash
man systemctl
systemctl get-default


```

### SERVICIOS
10. Instale el servidor ssh
```bash
lucia@lucia-VirtualBox:~$ sudo apt install ssh
```
11. Compruebe que el servidor ssh está activo, y esperando peticiones. Si no lo está, inicie el servicio. Haga una conexión a localhost de prueba y salga.
 Los servicios pueden estar activos o inactivos y habilitados o deshabilitados y enmascarado(puede estar encendido pero no puedo encenderlo) o desenmascarado.\
Activo -> is-active, start, stop, restart
Habilidados -> is-enable, enable, disable
Enmascarado -> mask, unmask
```bash



```

12. Determine el estado del servicio ssh 
```bash
lucia@lucia-VirtualBox:~$ systemctl is-active ssh
inactive
lucia@lucia-VirtualBox:~$ systemctl status ssh
Unit ssh.service could not be found.
lucia@lucia-VirtualBox:~$ systemctl status ssh.service
```
13. Visualice el fichero /lib/systemd/system/ssh.service. ¿En que situación se reinicia el servidor ssh, según dicho fichero de configuración?
 sudo systemctl start ssh
 ssh apso@localhost
Cada servicio tiene asociado un archivo de configutación, es un archivo .service

15. Detenga el servidor de ssh.
```bash
sudo systemctl stop ssh.socket
```

17. Deshabilite el servidor ssh.
```bash
sudo systemctl stop ssh.socket
sudo systemctl stop ssh
sudo systemctl disable ssh
sudo systemctl status ssh
```

16. Enmascare el servidor ssh
```bash
sudo systemctl mask ssh
```
18. Determine el estado del servicio ssh
```bash
sudo systemctl status ssh
```

19. Realice las acciones necesarias para que el servidor ssh esté activo, aunque no habilitado (no se inicie con el sistema).
```bash
sudo systemctl unmask ssh
sudo systemctl start ssh
```

### TAREAS PERIODICAS
20. Haga que el servidor ssh se inicie en el arranque del sistema, asegurándose de que se actualicen los enlaces simbólicos necesarios
systemctl status cron.service

20. Cree un script llamado repetidor que se ejecute cada hora, y que haga que se añada una línea al fichero /home/user- apso/cadahora, con el mensaje “Ejecutado cron a las <fecha y hora>”
```bash
joe repetidor
!/bin/sh
date +"Ejecutando cron a las %H:%M" >>/home/apso/cadahora 
lucia@lucia-VirtualBox:~$ chmod a+x repetidor
```
sudo systemctl restart cron 

22. Instale la utilidad at\
-> Tareas para futuro
    
24. Visualice la hora del sistema.
    
25. Haga que se añada una linea al fichero /home/user- apso/cadahora con el mensaje “linea generada por la orden at a las <fecha y hora>”, de forma automática 4 minutos después de la hora obtenida en el punto 22


26. Copie el script creado en el punto o 20 a su directorio de usuario con el nombre programado.

27. Programe una tarea para que el script programado se ejecute dentro de 15 minutos.

28. Visualice las tareas programadas para la orden at.
 
30. Elimine la tarea programada en el punto 25 Compruebe que ha sido
eliminada.

31. Programe un apagado del sistema para dentro de 3 minutos, informando a todos los usuarios con el mensaje “guardad y salid que esto se va a apagar”.




