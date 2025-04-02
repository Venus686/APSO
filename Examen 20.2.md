# EJERCICIOS PARA PRACTICAR
## INFO UTIL


## EJERCICIO 1
 1) Cambie el passwd de su cuenta.
 ```bash
passwd  
```
## EJERCICIO 2
 2) 0,25 puntos Cree la siguiente estructura de directorios en su cuenta de usuario con un sólo
 comando, usando rutas relativas:
 ![Captura de pantalla 2025-04-01 202240](https://github.com/user-attachments/assets/1fdca903-18c2-4bc6-8360-bef6f26a7beb)
 ```bash

```

## EJERCICIO 3
 3)  0,25 puntos Modifique los permisos del directorio pruebaL3 para que los miembros del
 grupo y el resto de usuarios no tengan permiso de lectura y escritura pero si de ejecución y
 el propietario tenga todos los permisos.
 Quite los permisos de lectura y escritura para miembros del grupo y resto de usuarios
 sobre los directorios varios y  guion.
 ```bash

```

## EJERCICIO 4
4) 0,25 puntos Sin hacer uso del find copie todos los ficheros de /home/so/ficheros
 cuyo nombre contenga un numero en la tercera posición de su nombre al directorio
 varios usando rutas absolutas
 ```bash

```

## EJERCICIO 5
  5) 0,25 puntos Cambie al directorio pruebaL3. Sin hacer uso del find mueva aquellos
 ficheros del directorio varios cuyo nombre finalice en bak al directorio basura con
 rutas relativas
```

```
## EJERCICIO 6
 6) 0,25 puntos Borre el directorio basura
```bash

```

## EJERCICIO 7
 7) 0,25 puntos s Haga que la ruta al directorio guion y al directorio actual (directorio .)
 estén siempre disponibles en el PATH al acceder al sistema.
 ```bash
PATH=:.
```
## EJERCICIO 8
 8) 0,25  Haga que cada vez que se acceda al sistema se cree una variable llamada
 GUION que contenga la ruta absoluta al directorio guion y que se cree un alias llamado
 cdvarios que se mueva al directorio varios, independientemente de donde se
 ejecute
```bash

```

## EJERCICIO 9
 9) 0,5 puntos Cree un fichero en el directorio varios llamado nodir, que contenga
 todos los nombres de ficheros que no son directorios a partir del directorio “/home” que
 empiecen con una letra (sea mayúscula o minúscula), tengan una e como segundo carácter
 y algún número en su nombre, ordenado alfabéticamente y con una sola línea de comando
 (Deben salir sólo los ficheros y sólo su nombre - no la ruta) (Cada nombre de fichero
 estará en una línea del fichero). Los errores no deben salir por pantalla sino guardarse en
 un fichero errores9 en la carpeta temp
```bash

```

## EJERCICIO 10
10) Añada al final del fichero nodir, creado en el punto anterior, la hora del
 sistema con el siguiente formato: “Hola. Son las horas:minutos:segundos. Esta en
 nombre servidor. Es dia de la semana, dia del mes de mes en letras de año”.
```bash

```
## EJERCICIO 11
 11) 0,25 puntos Cree un enlace simbólico en el directorio varios llamado enlace que
 apunte al fichero errores9, creado en el apartado 9
```bash

```
## EJERCICIO 12
12) 0,5 puntos.  Liste todos los ficheros que se encuentran en su carpeta personal, incluso los
 que empiezan por punto, ordenados en orden inverso. La salida irá a un fichero llamado
 listadoL3.txt en la carpeta varios.
```bash

```
## EJERCICIO 13
13) 0,5 puntos Con una sola orden, copie todos los ficheros que se encuentren a partir de la
 carpeta /home/so/ficheros que hayan sido modificados hace más de dos horas y
 contengan un número en el segundo carácter de su nombre al directorio temp.
```bash

```
## EJERCICIO 14
 14) 0,33 puntos  Compruebe que el servidor ssh está activo
```bash

```

## EJERCICIO 15
 15) 0,33 puntos Cree dos nuevos usuarios llamados us1 y us2 con uids 1100 y 1101
```bash

```
## EJERCICIO 16
16) 0,25 puntos  Cree un nuevo grupo llamado junio20 que tenga como gid 1005
```bash


```
## EJERCICIO 17
17) 0,34 puntos  Visualice página a página los dos ficheros en los que se encuentran las
 cuentas de todos los grupos
```bash


```
## EJERCICIO 18
 18) (2,25 puntos) Cree un guión, en el directorio guion llamado guardar al que se le pase
 un parámetro y realice lo siguiente:
 Comprueba que se le ha pasado un sólo parámetro y si no es así visualiza un mensaje de
 error y termina.
 Lee un número de teclado. Si no es mayor o igual que 1 y menor o igual que 10, saca
 mensaje de error y termina.
 Genera un fichero en la carpeta varios con el nombre introducido como parámetro en el
 que guardaremos el número leído tantas veces como indique ese número.
```bash
#!/bin/bash
if [ $# -n2 1 ];then
    echo "Error. Se debe de pasar un solo parámetro."
    exit 10
fi
echo "Introduce un número por teclado, entre 1 y 10."
read NUMERO
if [ $NUMERO -lt 1 ] | [ $NUMERO -gt 10 ];then
   echo "Error el numero debe de ser entre 1 y 10"
   exit 10
fi
i=0
while [ $i -lt $NUMERO ]
do
   echo "$NUMERO" 1>/home/lucia.zamudio/ExS2/varios/$1
   i=$(expr $i + 1)
done 
```
## EJERCICIO 19
 19)  (0.25 puntos)  Ejecute el guión anterior pasando como parámetro fichp
```bash

```
## EJERCICIO  20
20)  (2.5 puntos) Cree un guión, en el directorio guion, llamado ejecut que tome dos
 parámetros y realice lo siguiente:\
 Comprueba que se pasan dos parámetros y que el primero es un directorio. De no ser así
 da un mensaje de error y finaliza.\
 Guarda en el directorio pasado como primer parámetro un fichero llamado como se indica
 en el segundo parámetro, los nombres de ficheros normales (con su ruta) que cuelgan a
 partir de tu directorio personal a los que se haya accedido hace menos dos horas
 ordenados alfabéticamente en orden inverso. Cada nombre de fichero debe encontrarse en
 una línea diferente. Es obligatorio el uso del for para la realización de este ejercicio.
```bash
#!/bin/bash
if [ $# -ne 2 ];then
   echo "Error, se deben de poner dis parámetros."
   exit 10
fi
if [ ! -d $1 ];then
   echo "Error, el primer parámetro debería ser un fichero."
   exit 10
fi

for i in $(find ~  -mtime -2h  printf"%h \n")
do
     sort -r $i 1>$1/$2
 done
```

