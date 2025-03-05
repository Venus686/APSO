
# Ejercicios

## Ejercicio 1
Muestre por pantalla el texto "Practica 3: Manejo de Shell – Inicio…"
```bash
lucia.zamudio@polifemo:~$ echo o “Practica 3: Manejo de Shell – Inicio…”
```

## Ejercicio 2
Cree un directorio llamado Practica3 dentro de ModuloI. Acceda dentro del directorio ModuloI.
```bash
lucia.zamudio@polifemo:~$ cd ModuloI
lucia.zamudio@polifemo:~/ModuloI$ mkdir Practica3fin
```
## Ejercicio 3
Use la orden find para visualizar los nombres y los tamaños de todos los ficheros (sólo los ficheros) que cuelguen de su directorio de usuario y cuyo tamaño sea inferior a 100 caracteres. Sólo deben aparecer los nombres de ficheros (sin la ruta) y los tamaños.
```bash
lucia.zamudio@polifemo:~/ModuloI$ find ~ -type f -size -100c -printf '%f...%b\n'
```
## Ejercicio 4
Copie el fichero /home/so/ficheros/infinito al directorio Practica3.
```bash
lucia.zamudio@polifemo:~/ModuloI$ cp /home/so/ficheros/infinito Practica3
```
## Ejercicio 5
Haga que el fichero infinito tenga permisos de ejecución para todos.
```bash
lucia.zamudio@polifemo:~/ModuloI$ chmod a+x Practica3/infinito
```
## Ejercicio 6
Ejecute el fichero infinito.
```bash
lucia.zamudio@polifemo:~/ModuloI$ ./Practica3/infinito

```
## Ejercicio 7
En un nuevo terminal, visualice los procesos que está ejecutando.
```bash
lucia.zamudio@polifemo:~$ ps -ef
```
## Ejercicio 8
Vuelva al terminal donde ejecutó infinito y aborte el proceso (CTRL+C).
```bash
^C
```
## Ejercicio 9
Ejecute nuevamente el programa infinito, pero esta vez en segundo plano.
```bash
lucia.zamudio@polifemo:~/ModuloI$ ./Practica3/infinito &
```
## Ejercicio 10
En el mismo terminal donde se está ejecutando infinito, visualice los procesos que está ejecutando.
```bash
lucia.zamudio@polifemo:~/ModuloI$ Esto no acaba .....
ps
```
## Ejercicio 11
Recupere (traiga a primer plano) el proceso infinito. Abórtelo una vez recuperado.
```bash
lucia.zamudio@polifemo:~/ModuloI$ fg 34037
^C
```
## Ejercicio 12
Haga que el resultado devuelto por la orden del punto 3 quede en un fichero llamado pequeños en el directorio Practica3.
```bash
lucia.zamudio@polifemo:~/ModuloI$ find ~ -type f -size -100c -printf '%f...%b\n' >Practica3/pequeños

```
## Ejercicio 13
Cambiamos al directorio Practica3.
```bash
lucia.zamudio@polifemo:~/ModuloI$ cd Practica3
```
## Ejercicio 14
Usando las órdenes necesarias, cree un fichero llamado minfo, dentro del directorio Practica3, que contenga tres líneas: la primera con su nombre de usuario, la segunda con el terminal que está usando, y la última con el nombre del grupo al que pertenece.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ id -nu >minfo
lucia.zamudio@polifemo:~/ModuloI/Practica3$ tty >>minfo
lucia.zamudio@polifemo:~/ModuloI/Practica3$ id -g>>minfo
```
## Ejercicio 15
Visualice los nombres de los ficheros que cuelgan del directorio /etc y que hace más de 100 días que han sido modificados. Los errores no deben aparecer por la pantalla.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ find /etc -type f -mtime +100 2>/dev/null
```
## Ejercicio 16
Haga que los errores generados en el punto anterior se almacenen en un fichero llamado err del directorio Practica3.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ find /etc -type f -mtime +100 2>err
```
## Ejercicio 17
Genere un fichero en el directorio Practica3, llamando crons, que contenga el resultado de buscar todos los ficheros que cuelguen a partir del directorio /var que comiencen por cr. Los errores también deben aparecer en el fichero.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ find /var -type f -name "cr*" >crons
```
## Ejercicio 18
Visualice el número (sólo el número) de directorios que existan a partir de su directorio de usuario.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ find ~ -type d |wc -l
31
```
## Ejercicio 19
Genere un fichero, en el directorio Practica3, llamado usersort, que contenga los nombres de los usuarios conectados al sistema en ese instante, ordenados alfabéticamente en orden inverso.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ who| sort -r >usersort
```
## Ejercicio 20
Con una única orden busque, a partir de su directorio de usuario, todos los ficheros que comiencen por f o s, y visualice el contenido de todos ellos pantalla a pantalla. (Use sustitución de comandos).
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ more $(find ~ -type f -name "[fs]*"
```
## Ejercicio 21
Con una única orden, copie cualquier fichero que esté en vuestro directorio ModuloI, o dentro de cualquier subdirectorio, y cuyo tiempo de acceso hace más de 2 días, al directorio mas2 creado de manera previa dentro del directorio Practica3. (Use sustitución de comandos).
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ mkdir mas2
lucia.zamudio@polifemo:~/ModuloI/Practica3$ cp $(find ~/ModuloI/ -type f -atime +2) ./mas2/
```
## Ejercicio 22
Muestre en pantalla el mensaje "Práctica 3: Manejo de Shell… Finalizada".
```bash

lucia.zamudio@polifemo:~/ModuloI/Practica3$ echo "Práctica 3: Manejo de Shell… Finalizada".
```
## Ejercicio 23
Salga adecuadamente del sistema.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica3$ exit
```
