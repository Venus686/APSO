### Ejercicio 1
Muestre por pantalla el texto "Practica 2: Manejo de Shell - Inicio..."
```bash
lucia.zamudio@polifemo:~$ echo "Practica 2: Manejo de Shell - Inicio..."
```

### Ejercicio 2
Muévase al directorio ~/ModuloI/Practica1/
```bash
lucia.zamudio@polifemo:~$ cd ModuloI/Practica1/
```

### Ejercicio 3
Cree un directorio, dentro de ModuloI, llamado Practica2. (Se deberá usar una ruta relativa).
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica1$ mkdir ../Practica2
```

### Ejercicio 4
Haga que los permisos del directorio Practica2 sean 'rwx------'. Se deberá usar la notación numérica. (Se deberá usar una ruta relativa).
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica1$ chmod 700 ../Practica2
```

### Ejercicio 5
Cree, dentro del directorio Practica2, un fichero llamado solucion2. Dicho fichero deberá contener la solución de la presente práctica.
```bash
lucia.zamudio@polifemo:~$ cd ModuloI/Practica2
lucia.zamudio@polifemo:~/ModuloI/Practica2$ joe solucion2
```

### Ejercicio 6
Volviendo a la primera sesión, muévase al directorio Practica2. (Se deberá usar una ruta absoluta)
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica1$ cd /home/lucia.zamudio/ModuloI/Practica2
```

### Ejercicio 7
Visualice, con la orden find, todos los directorios (sólo directorios) que cuelguen a partir de /var y cuyo nombre contenga la cadena 'data'.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ find /var type -d -name "*data*"
```

### Ejercicio 8
Visualice, con la orden find, todos los ficheros regulares (sólo ficheros) que cuelguen a partir de /etc y cuyo contenido haya sido modificado hace menos de 100 días.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ find -type f /etc -mtime -100
```

### Ejercicio 9
Copie el fichero /etc/passwd y el fichero /etc/group al directorio Practica2.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ cp /etc/passwd /etc/group .
```

### Ejercicio 10
Busque su nombre de usuario en los ficheros passwd y group que acaba de copiar.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ grep lucia.zamudio passwd
```

### Ejercicio 11
Visualice el número de caracteres del fichero group.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ wc -c group
1046 group
```

### Ejercicio 12
Visualice la longitud de la línea más larga del fichero passwd.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ wc -l passwd
202 passwd
```

### Ejercicio 13
Visualice el contenido del fichero group ordenado alfabéticamente en orden inverso.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ sort -r group
```

### Ejercicio 14
Visualice las tres primeras líneas del fichero passwd.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ head -3 passwd
```

### Ejercicio 15
Visualice las tres últimas líneas del fichero passwd.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ tail -3 passwd
```

### Ejercicio 16
Cree en su directorio de usuario un enlace simbólico llamado versos, que apunte al fichero fichcancion.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ ln -s ../Practica1/Datos/fichcancion versos
```

### Ejercicio 17
Busque las líneas del fichero "versos" creado anteriormente que comiencen por "Cobi".
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ grep -i 'Cobi' versos
```

### Ejercicio 18
Visualice los usuarios conectados al sistema, donde aparezca también la línea de cabecera de las columnas.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ lucia.zamudio@polifemo:~/ModuloI/Practica2$ who
 -H
```

### Ejercicio 19
Visualice el identificador de su grupo de usuarios.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ id -g
100
```

### Ejercicio 20
Visualice el calendario del mes de enero de 2022.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica2$ cal 01 2022
     Enero 2022
do lu ma mi ju vi sá
                   1
 2  3  4  5  6  7  8
 9 10 11 12 13 14 15
16 17 18 19 20 21 22
23 24 25 26 27 28 29
30 31
```

### Ejercicio 21
Visualice la fecha actual con el formato: "Año: 2023, Mes: 02, Dia: 08".
```bash
lucia.zamudio@polifemo:~$ date +"Año: %Y, Mes: %m, Dia:%d"
Año: 2025, Mes: 03, Dia:09
```

### Ejercicio 22
Visualice el Terminal desde el que está conectado.
```bash
lucia.zamudio@polifemo:~$ tty
```

### Ejercicio 23
Ejecute el monitor del sistema top.
```bash
lucia.zamudio@polifemo:~$ top
```

### Ejercicio 24
Abra una nueva sesión y cámbiese a ella.
```bash

```

### Ejercicio 25
Mate (enviar la señal 9) el proceso correspondiente a la orden top.
```bash
lucia.zamudio@polifemo:~$ ps -u lucia.zamudio
  PID TTY          TIME CMD
12699 ?        00:00:00 systemd
12700 ?        00:00:00 (sd-pam)
12780 ?        00:00:00 sshd
12784 pts/0    00:00:00 bash
13009 ?        00:00:00 sshd
13015 pts/2    00:00:00 bash
13652 pts/2    00:00:00 top
13930 pts/0    00:00:00 ps
lucia.zamudio@polifemo:~$ kill -9 pid-13652
-bash: kill: pid-13652: arguments must be process or job IDs
lucia.zamudio@polifemo:~$ kill -9 pid-13652
-bash: kill: pid-13652: arguments must be process or job IDs
```

### Ejercicio 26
Envíe un mensaje al usuario usuario.destino que desee y que esté conectado con la frase "Práctica 2 a punto de finalizar por <nombre.usuario>".
```bash
lucia.zamudio@polifemo:~$ write ruben.conde
"Práctica 2 a punto de finalizar por <nombre.usuario>"

```

### Ejercicio 27
Deshabilite la llegada de mensajes instantáneos y probar con algún compañero/a.
```bash
lucia.zamudio@polifemo:~$ mesg n
lucia.zamudio@polifemo:~$ write ruben.conde
write: write: you have write permission turned off.
```

### Ejercicio 28
Muestre en pantalla el mensaje "Práctica 2: Manejo de Shell... Finalizada".
```bash
lucia.zamudio@polifemo:~$ echo "Práctica 2: Manejo de Shell... Finalizada".
Práctica 2: Manejo de Shell... Finalizada.
```

### Ejercicio 29
Salga adecuadamente del sistema.
```bash
lucia.zamudio@polifemo:~$ exit
```
