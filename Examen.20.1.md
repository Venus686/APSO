# EJERCICIOS PARA PRACTICAR
## INFO UTIL
Si se rompe el path
/usr/bin\
EXAMEN\
CTRL + ALT+ F3\
Login: usuario\
password: usuario00\
usuario@pc...$killall gnome-shell -> no hacerlo\ 
usuario@pc..$ssh lucia...@172.17.21.248\
polifemo login:
CTRL + ALT + F4\
y ademas no tienes que matar el entorno gráfico más


fichero1 -nt fichero2 Verdad si fichero1 es más reciente (según la fecha de modificación) que fichero2.\
fichero1 -ot fichero2 Verdad si fichero1 es más antiguo que fichero\
-eq	Igual a (equal)	5 -eq 5 → Verdadero\
-ne	No igual a (not equal)	5 -ne 10 → Verdadero\
-gt	Mayor que (greater than)	10 -gt 5 → Verdadero\
-lt	Menor que (less than)	5 -lt 10 → Verdadero\
-ge	Mayor o igual que (greater or equal)	10 -ge 5 → Verdadero\
-le	Menor o igual que (less or equal)	5 -le 10 → Verdadero\
Números:

-eq, -ne, -gt, -lt, -ge, -le (para comparar números)

Cadenas:

=, !=, <, >, -z, -n (para comparar cadenas)

Archivos:

-e, -f, -d, -r, -w, -x, -s, -L (para trabajar con archivos y directorios)

Lógica:

!, -o, -a (operadores lógicos)

x -lt y Verdad si x menor que y\
x -le y Verdad si x menor o igual que y\
x -eq y Verdad si x igual que y\
x -ge y Verdad si x mayor o igual que y\
x -gt y Verdad si x mayor que y\
x -ne y Verdad si x no igual que y


repquota:
Propósito: Muestra un informe sobre el uso actual de cuotas de disco.

Cuándo se usa: Se utiliza cuando deseas ver el estado actual de las cuotas de disco para los usuarios o grupos en el sistema. Muestra información sobre el uso de espacio en disco y las cuotas asignadas.

Función: Muestra las cuotas actuales y el uso de disco en los sistemas de archivos donde las cuotas están habilitadas. Puede mostrarte las cuotas asignadas, el uso de disco de cada usuario y si se han superado las cuotas.

Propósito: Realiza una comprobación y corrección de las cuotas de disco en los sistemas de archivos.

Cuándo se usa: Se utiliza para verificar y corregir la base de datos de cuotas, en caso de que se haya dañado o si se ha añadido o modificado un sistema de archivos con cuotas habilitadas. Esto también es necesario después de reiniciar el sistema o montar un sistema de archivos que tenga cuotas activadas.

Función: quotacheck escanea el sistema de archivos y crea o actualiza los archivos de cuotas (aquota.user y aquota.group) que contienen la información sobre las cuotas de usuario y grupo. Si los archivos de cuotas están dañados o no se han actualizado, quotacheck puede corregir estos archivos.

## EJERCICIO 1
 1) Cambie el passwd de su cuenta.
 ```bash
passwd  
```
## EJERCICIO 2
  2) 0,25 puntos Cree la siguiente estructura de directorios en su cuenta de usuario:
     ![Captura de pantalla 2025-03-31 203445](https://github.com/user-attachments/assets/25538b49-5cf5-41ce-9df2-b19241144bee)
 ```bash
lucia.zamudio@polifemo:~$ mkdir -p ExS2/ficheros/trash ExS2/guiones/temporal
```

## EJERCICIO 3
 3) 0,25 puntos Modifique los permisos del directorio pruebaL1 para que los miembros del grupo y el resto de usuarios no tengan ningún permiso. 
Haga que el directorio ficheros tenga como permisos rwxr-xr--
 ```bash
lucia.zamudio@polifemo:~$ chmod 700 ExS2
lucia.zamudio@polifemo:~$ chmod 754 ExS2/ficheros
```

## EJERCICIO 4
4) 0,25 puntos Copie todos los ficheros de /home/so/ficheros cuyo nombre contenga un número en la tercera posición de su nombre al directorio ficheros
 ```bash
lucia.zamudio@polifemo:~$ cp /home/so/ficheros/??[0-9]* ExS2/ficheros/
```

## EJERCICIO 5
  5) 0,25 puntos Mueva aquellos ficheros del directorio ficheros cuyo nombre finalice en bak al directorio trash
```
lucia.zamudio@polifemo:~$ mv ExS2/ficheros/*bak ExS2/ficheros/trash/
```
## EJERCICIO 6
 6) 0,25 puntos Borre el directorio trash
```bash
lucia.zamudio@polifemo:~$ rm -r ExS2/ficheros/trash/
```

## EJERCICIO 7
 7) 0,25 puntos Haga que la ruta al directorio de trabajo esté siempre disponible en el PATH al acceder al sistema.
 ```bash
PATH=:.
```
## EJERCICIO 8
 8) 0,25 puntos Haga que cada vez que se acceda al sistema se cree una variable llamada GUIONES que contenga la ruta absoluta al directorio guiones
```bash
GUION=/home/lucia.zamudio/ExS2/guiones
export GUION
lucia.zamudio@polifemo:~$ echo $GUION
/home/lucia.zamudio/ExS2/guiones
```

## EJERCICIO 9
 9) 0,5 puntos Encuentre todos los enlaces simbólicos que existan a partir del directorio /usr, cuyo nombre contenga la cadena head, que hayan sido modificados hace más de 10 días y cuyo tamaño sea superior a 30 palabras (de 2 bytes).  Por cada fichero  encontrado debe visualizarse una linea con el contenido “Fichero: “ seguido de la ruta al fichero. La salida de dicha orden debe almacenarse en un fichero llamado elfind  y la salida de errores en otro llama errorfind, ambos en el directorio ficheros.
```bash
 -size n
 `w'    for two-byte words
lucia.zamudio@polifemo:~$ find /usr -name "*head*" -type l -mtime +10 -size +30w -printf "fichero: %h\n" >ExS2/ficheros/elfind 2>ExS2/ficheros/errorfind
```

## EJERCICIO 10
10) 0,25 puntos Añada al final del fichero elfind, creado en el punto anterior, la hora actual.
```bash
lucia.zamudio@polifemo:~$ date +"La hora actual es %R" >>ExS2/ficheros/elfin
d
lucia.zamudio@polifemo:~$ cat ExS2/ficheros/elfind
fichero: /usr/src/linux-headers-4.15.0-213-generic/scripts/selinux/genheaders
fichero: /usr/src/linux-headers-4.15.0-212-generic/scripts/selinux/genheaders
La hora actual es 11:30
```
## EJERCICIO 11
 11) 0,25 puntos Cree un enlace simbólico en el directorio temporal llamado noacces que apunte al fichero errorfind, creado en el punto 9.
```bash
lucia.zamudio@polifemo:~$ ln -s ExS2/ficheros/errorfind ExS2/guiones/temporal/noacces
lucia.zamudio@polifemo:~$ ls -l ExS2/guiones/temporal/noacces
lrwxrwxrwx 1 lucia.zamudio users 23 abr  1 11:36 ExS2/guiones/temporal/noacces -> ExS2/ficheros/errorfind
```
## EJERCICIO 12
12) 0,5 puntos. Visualice en orden inverso, todos los usuarios conectados al sistema cuyo nombre contenga la cadena va. La salida debe quedar en un fichero llamado p12.txt en el directorio ficheros.
```bash
lucia.zamudio@polifemo:~$ who |grep va | sort -r >ExS2/ficheros/p12.txt
lucia.zamudio@polifemo:~$ ls ExS2/ficheros/p12.txt
ExS2/ficheros/p12.txt
lucia.zamudio@polifemo:~$ cat ExS2/ficheros/p12.txt
marta.huelva pts/24       2025-04-01 17:05 (150.214.167.251)
marta.huelva pts/22       2025-04-01 17:05 (150.214.167.251)
ivan.porta pts/23       2025-04-01 17:32 (150.214.167.251)
```
## EJERCICIO 13
13) 0,5 puntos Con una sola orden, borre todos los ficheros que se encuentren a partir de su directorio de usuario y cuyo nombre finalice en 0 (cero).
```bash
lucia.zamudio@polifemo:~$ rm -r ~/*0
```
## EJERCICIO 14
 14) 0,33 puntos Cree un fichero de texto (se puede hacer manualmente) llamado elgrub.txt, dentro del directorio ficheros, que contenga la linea del fichero de configuración de nuevos usuarios que indica el shell a usar por defecto cuando se crean nuevos usuarios
```bash

```

## EJERCICIO 15
 15) 0,33 puntos Busque en la cache de paquetes del sistema, aquellos relacionados con sgb.
 Haga que la salida quede en un fichero llamado paquetes.txt en el directorio ficheros.
```bash
lucia.zamudio@polifemo:~$ apt-cache search sgb > /home/lucia.zamudio/ExS2/fi
cheros/paquetes.txt
lucia.zamudio@polifemo:~$ cat /home/lucia.zamudio/ExS2/ficheros/paquetes.txt
libbatteries-ocaml-dev - Batteries included: OCaml development platform - development files
libgeo-coordinates-osgb-perl - converting module between Lat/Lon and the British National Grid
python-dialog - Python 2 module for making simple terminal-based user interfaces
python3-dialog - Python module for making simple terminal-based user interfaces
sgb - The Stanford GraphBase: datos combinatorios y algoritmos
sgb-doc - Documentación para Stanford GraphBase


-------------------------------------------
lucia.zamudio@polifemo:~$ dpkg -l | grep sgb >> /home/lucia.zamudio/ExS2/ficheros/paquetes.txt
```
## EJERCICIO 16
16) 0,25 puntos Visualice la situación actual de sus cuotas de disco. La salida debe quedar en un fichero llamado ocupacion.txt en el directorio ficheros.
```bash
repquota -a: Muestra las cuotas de disco de todos los sistemas de archivos habilitados con cuotas (se debe haber configurado previamente las cuotas de disco).

-a: Muestra la información de todas las particiones que tengan cuotas habilitadas.

```
## EJERCICIO 17
17) 0,34 puntos Visualice el estado del servicio webmin.service. Haga que la salida quede en un fichero llamado estado.txt en el directorio ficheros.
```bash
lucia.zamudio@polifemo:~$ sudo repquota -a > /home/lucia.zamudio/ExS2/ficher
os/extado.txt
[sudo] password for lucia.zamudio:
lucia.zamudio is not in the sudoers file.  This incident will be reported.

```
## EJERCICIO 18
 18) (1,5 puntos) Se debe crear un guión en el directorio guiones llamado g1, que tome dos parámetros y realice lo siguiente:\
 • Solicitará que se introduzca un nombre por teclado, y lo almacenará en una variable llamada DIR\
 • Dentro del directorio, cuya ruta se pasa como primer parámetro, creará un directorio con el nombre contenido en la variable DIR.\
 • Creará un alias llamado minombre, que creará un fichero con el nombre del segundo parámetro, dentro de DIR que contendrá su nombre real.
```bash
#!/bin/bash
if [ $# -ne 2 ];then
        echo "Se deben introducir dos parámetros"
        exit 10
fi

echo "Introduce un nombre por teclado: "
read DIR


mkdir $1/$DIR
alias minombre="echo $USER > $1/$DIR/$2"
export minombre
```
## EJERCICIO 19
 19) (0.5 puntos) Ejecute el guión anterior, de forma que el alias y la variable estén disponibles al finalizar el guión, pasándole los parámetros $HOME/pruebaL1/ficheros y estudiante.txt. 
Ejecute el alias minombre tras ejecutar el guión
```bash
lucia.zamudio@polifemo:~$ source ExS2/guiones/g1 /home/lucia.zamudio/ExS2/fi
cheros/ estudiante.txt
Introduce un nombre por teclado:
pet
lucia.zamudio@polifemo:~$ alias minombre
alias minombre='echo lucia.zamudio > /home/lucia.zamudio/ExS2/ficheros//pet/estudiante.txt'
```
## EJERCICIO  20
20) (3 puntos) Cree un guión en el directorio guiones llamado g2 que realice lo siguiente:
 • Comprobará que se le han pasado dos parámetros, de no ser así, lo indicará con un mensaje de error y finalizará.\
 • Si el primer parámetro no es un directorio válido, dará un mensaje de error y finalizará.\
 • Inicializa una variable llamada TOTAL a 0\
 • Por cada fichero que exista en el directorio que se pasa como primer parámetro, se comprobará que si su nombre:\
 ◦ contiene la cadena que se pasa como segundo parámetro, se muestra su contenido.\
 ◦ está compuesto de una f seguida de dos caracteres se suma uno a la variable TOTAL
 ◦ finaliza en número, se suma 1 a la variable TOTAL\
 ◦ en cualquier otro caso, se resta 1 a la variable TOTAL\
 • Visualiza un mensaje con el contenido de la variable TOTAL\
```bash
#!/bin/bash
if [ $# -ne 2 ];then
        echo "Se necesitan 2 parámetros."
        exit 10
fi

if [ ! -d $1 ];then
        echo "El parámetro no es válido."
        exit 10
fi

TOTAL=0
for i in $(find $1 -type f)
do
        if  echo "$i" grep "$2" ;then
                cat $i
        elif [ echo "$i" grep *f??* ];then

                TOTAL=$(expr $TOTAL + 1)
        elif [ echo "$i" grep *[0-9] ];then
                TOTAL=$(expr $TOTAL + 1)
        else
                TOTAL=$(expr $TOTAL - 1)
        fi
done
echo "$TOTAL"
```
