# GUIONES/ SCRIPTS
### $
 $variable -> Ejemplo-> echo home vale $HOME \

````bash
  -> $(orden) = `orden ` 
````
  ACENTO GRAVE -> `   `

### \ 
echo \$PATH contiene $PATH 
La \ quita el significado al caracter siguiente
ls a* -> ls a\*

### COMILLAS SIMPLES Y COMILLAS DOBLES
Si está entre comillas se asumirá como una cadena. \
Pero las comillas dobles si interpretan los carácteres \ ` y $. \
Ejemplo \
echo 'la variable HOME contiene $HOME' \
echo "la variable HOME contiene $HOME" -> conserva el significado 

### ORDEN FILE
Especifica la extencion del archivo, aunque su extensión no esté visible. 
Ejemplo 
```bash
pedro@Polifemo:~$ file fichero_sin_extension
````

### CREACIÓN DE GUIONES
Los comentarios dentro del guion se hacen con #
```bash
pedro@Polifemo:~$ joe ejemplo_simple
date
ps
who
CTRL+k,x
File ejemplo_simple saved

## DAMOS PERMISO DE EJECUCIÓN 
pedro@Polifemo:~$ chmod a+x ejemplo_simple

# COMO EJECUTARLO DE MANERA ABSOLUTA
pedro@Polifemo:~$ /home/pedro/ejemplo_simple
lun mar 16 13:53:37 CET 2020
 PID TTY TIME CMD
 5826 pts/0 00:00:00 bash
25761 pts/0 00:00:00 bash
25763 pts/0 00:00:00 ps
pedro :1 2020-03-16 07:51 (:1)

 # CON RUTA RELATIVA
pedro@Polifemo:~$ ./ejemplo_simple
lun mar 16 13:53:40 CET 2020
 PID TTY TIME CMD
 5826 pts/0 00:00:00 bash
25765 pts/0 00:00:00 bash
25767 pts/0 00:00:00 ps
pedro :1 2020-03-16 07:51 (:1)

#PARA QUE SEA RECONOCIBLE COMO GUIÓN (colorea la sintaxis)
#!/bin/bash
```
Con WHICH ves la ruta del bash o del ksh \
PARA LA EJECUCIÓN :
```bash
pedro@Polifemo:~$ cat ejemplo_entorno
#!/bin/bash
VARIABLE1=V1
echo la variable VARIABLE1 vale $VARIABLE1
echo fin del guión
pedro@Polifemo:~$ ./ejemplo_entorno
la variable VARIABLE1 vale V1
fin del guión
pedro@Polifemo:~$ echo el valor de VARIABLE1 ES $VARIABLE1
el valor de VARIABLE1 ES

```
### ENTRADA, SALIDA Y FINALIZACIÓN DE UN GUIÓN
Read-> crea una variable o la sobreescribe, para q el usuario pueda escribir\
EJEMPLO
```bash
#!/bin/bash
echo Introduce una ruta
read LARUTA
find $LARUTA -maxdepth 1 -type d 2>dev/null
ls -ld ~$'find $LARUTA -maxdepth 1 -type d 2>dev/null'

```
Con el exit se finaliza un guion

Segunda manera de ejecutar un proceso, es crear un proceso nuevo que sea g2. Entonces bash habrá creado un proceso.


# Ejercicios

### Ejercicio 1
Cree con un solo comando el siguiente árbol de directorios a partir de su directorio personal mediante rutas absolutas. 
```bash

```

### Ejercicio 2
2. Añada en el fichero .profile a la variable PATH una nueva ruta, la ruta hasta el directorio guiones que hemos creado en el apartado 1. Esta nueva línea no tendrá efecto hasta que no ejecutemos el fichero .profile. Ejecute el fichero .profile de la forma adecuada para que el nuevo PATH tome efecto. Visualice de nuevo la variable PATH para asegurarse que tiene lo que tenía en la práctica 4 más la nueva ruta que hemos añadido en este apartado. \
IMPORTANTE!!! No continúe adelante si no ha conseguido añadir esa nueva ruta a la variable PATH. Si continúa con el resto de apartados sin hacer los anteriores no podrá realizarlos correctamente. 
```bash

```

### Ejercicio 3

### Ejercicio 4

### Ejercicio 5

### Ejercicio 6

