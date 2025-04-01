# EJERCICIOS PARA PRACTICAR
## INFO UTIL
Si se rompe el path
/usr/bin
EXAMEN
CTRL + ALT+ F3
Login: usuario
password: usuario00
usuario@pc...$killall gnome-shell
usuario@pc..$ssh lucia...@172.17.21.248
polifemo login:
CTRL + ALT + F4
y ademas no tienes que matar el entorno gráfico más
## EJERCICIO 1
 1) Cambie el passwd de su cuenta.
 ```bash
passwd  
```
## EJERCICIO 2
  2) 0,25 puntos Cree la siguiente estructura de directorios en su cuenta de usuario:
     ![Captura de pantalla 2025-03-31 203445](https://github.com/user-attachments/assets/25538b49-5cf5-41ce-9df2-b19241144bee)w
 ```bash
lucia.zamudio@polifemo:~$ mkdir -p ExS2/ficheros/trash ExS2/guiones/temporal
```

## EJERCICIO 3
 3) 0,25 puntos Modifique los permisos del directorio pruebaL1 para que los miembros del grupo y el resto de usuarios no tengan ningún permiso. 
Haga que el directorio ficheros tenga como permisos rwxr-xr-
 ```bash

```

## EJERCICIO 4
4) 0,25 puntos Copie todos los ficheros de /home/so/ficheros cuyo nombre contenga un número en la tercera posición de su nombre al directorio ficheros
 ```bash

```

## EJERCICIO 5
  5) 0,25 puntos Mueva aquellos ficheros del directorio ficheros cuyo nombre finalice en bak al directorio trash
```

```
## EJERCICIO 6
 6) 0,25 puntos Borre el directorio trash
    

## EJERCICIO 7
 7) 0,25 puntos Haga que la ruta al directorio de trabajo esté siempre disponible en el PATH al acceder al sistema.
 ```bash

```
## EJERCICIO 8
 8) 0,25 puntos Haga que cada vez que se acceda al sistema se cree una variable llamada GUIONES que contenga la ruta absoluta al directorio guiones
```bash

```

## EJERCICIO 9
 9) 0,5 puntos Encuentre todos los enlaces simbólicos que existan a partir del directorio /usr, cuyo nombre contenga la cadena head, que hayan sido modificados hace más de 10 días y cuyo tamaño sea superior a 30 palabras (de 2 bytes).  Por cada fichero  encontrado debe visualizarse una linea con el contenido “Fichero: “ seguido de la ruta al fichero. La salida de dicha orden debe almacenarse en un fichero llamado elfind  y la salida de errores en otro llama errorfind, ambos en el directorio ficheros.
```bash

```

## EJERCICIO 10
10) 0,25 puntos Añada al final del fichero elfind, creado en el punto anterior, la hora actual.
```bash

```
## EJERCICIO 11
 11) 0,25 puntos Cree un enlace simbólico en el directorio temporal llamado noacces que apunte al fichero errorfind, creado en el punto 9.
```bash

```
## EJERCICIO 12
12) 0,5 puntos. Visualice en orden inverso, todos los usuarios conectados al sistema cuyo nombre contenga la cadena va. La salida debe quedar en un fichero llamado p12.txt en el directorio ficheros.
```bash

```
## EJERCICIO 13
13) 0,5 puntos Con una sola orden, borre todos los ficheros que se encuentren a partir de su directorio de usuario y cuyo nombre finalice en 0 (cero).
```bash

```
## EJERCICIO 14
 14) 0,33 puntos Cree un fichero de texto (se puede hacer manualmente) llamado elgrub.txt, dentro del directorio ficheros, que contenga la linea del fichero de configuración de nuevos usuarios que indica el shell a usar por defecto cuando se crean nuevos usuarios
```bash

```

## EJERCICIO 15
 15) 0,33 puntos Busque en la cache de paquetes del sistema, aquellos relacionados con sgb.
 Haga que la salida quede en un fichero llamado paquetes.txt en el directorio ficheros.
```bash

```
## EJERCICIO 16
16) 0,25 puntos Visualice la situación actual de sus cuotas de disco. La salida debe quedar en un fichero llamado ocupacion.txt en el directorio ficheros.
```bash

```
## EJERCICIO 17
17) 0,34 puntos Visualice el estado del servicio webmin.service. Haga que la salida quede en un fichero llamado estado.txt en el directorio ficheros.
```bash

```
## EJERCICIO 18
 18) (1,5 puntos) Se debe crear un guión en el directorio guiones llamado g1, que tome dos parámetros y realice lo siguiente:
 • Solicitará que se introduzca un nombre por teclado, y lo almacenará en una variable llamada DIR
 • Dentro del directorio, cuya ruta se pasa como primer parámetro, creará un directorio con el nombre contenido en la variable DIR.
 • Creará un alias llamado minombre, que creará un fichero con el nombre del segundo parámetro, dentro de DIR que contendrá su nombre real.
```bash

```
## EJERCICIO 19
 19) (0.5 puntos) Ejecute el guión anterior, de forma que el alias y la variable estén disponibles al finalizar el guión, pasándole los parámetros $HOME/pruebaL1/ficheros y estudiante.txt. 
Ejecute el alias minombre tras ejecutar el guión
```bash

```
## EJERCICIO  20
20) (3 puntos) Cree un guión en el directorio guiones llamado g2 que realice lo siguiente:
 • Comprobará que se le han pasado dos parámetros, de no ser así, lo indicará con un mensaje de error y finalizará.
 • Si el primer parámetro no es un directorio válido, dará un mensaje de error y finalizará.
 • Inicializa una variable llamada TOTAL a 0
 • Por cada fichero que exista en el directorio que se pasa como primer parámetro, se comprobará que si su nombre:
 ◦ contiene la cadena que se pasa como segundo parámetro, se muestra su contenido.
 ◦ está compuesto de una f seguida de dos caracteres se suma uno a la variable
 TOTAL
 ◦ finaliza en número, se suma 1 a la variable TOTAL
 ◦ en cualquier otro caso, se resta 1 a la variable TOTAL
 • Visualiza un mensaje con el contenido de la variable TOTAL
```bash

```
