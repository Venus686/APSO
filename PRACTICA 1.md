# PRÁCTICA 1.1

**1. Cree en vuestro directorio personal un directorio llamado prac1 con rutas relativas.**
lucia.zamudio@polifemo:~$ mkdir prac1

**2. Copie el fichero p1.txt que se encuentra en /home/so/velez/MI en el directorio prac1 con rutas absolutas.**
lucia.zamudio@polifemo:~$ cp /home/so/velez/MI/p1.txt /home/lucia.zamudio/prac1

**3. Abra una nueva sesión (sesión 2)(nuevo terminal). En esta nueva sesión muévase al directorio prac1 con rutas relativas. Edite con el joe el fichero p1.txt mediante rutas absolutas. Desde esta sesión sólo se podrá modificar el fichero p1.txt para ir añadiendo las soluciones a cada pregunta. Las siguientes preguntas se harán desde la primera sesión.**


**4. Cree dentro del directorio prac1, mediante ruta absoluta, el directorio prac11. Muévase al directorio prac11 mediante ruta relativa.**\
lucia.zamudio@polifemo:~$ mkdir /home/lucia.zamudio/prac1/prac11 \
lucia.zamudio@polifemo:- $ cd prac1 \
lucia.zamudio@polifemo:-/prac1$ cd prac11 

**5. Cree desde aquí, con un solo comando, y mediante rutas relativas, cuatro directorios que sean hijos de prac1, llamándolos prac12, prac13, prac14 y prac15.**
lucia.zamudio@polifemo:~/prac1/prac11$ mkdir ../prac12 ../prac13 ../prac14 ../prac15

**6. Muévase al directorio raíz con el comando más corto posible. Visualice desde aquí el contenido del fichero p1.txt que ha copiado en su directorio prac1 mediante rutas relativas. Muévase al directorio prac13 mediante ruta relativa. Visualice desde aquí el fichero p1.txt del directorio prac1 mediante rutas relativas.**\
lucia.zamudio@polifemo:~/prac1/prac11$ cd /   \
lucia.zamudio@polifemo:/$ more home/lucia.zamudio/prac1/p1.txt \
lucia.zamudio@polifemo:/$ cd home/lucia.zamudio/prac1/prac13 \
lucia.zamudio@polifemo:~/prac1/prac13$ more ../p1.txt

**7. Cree mediante rutas absolutas con el joe un fichero llamado prueba13 en el directorio prac13 cuyo contenido sea:  Esto es un fichero de prueba perteneciente al usuario (tu nombre de usuario) Cree con el joe un fichero llamado prueba12 en el directorio prac12 mediante rutas relativas cuyo contenido sea: Esto es un fichero de prueba perteneciente al usuario (tu nombre de usuario)**\
lucia.zamudio@polifemo:~/prac1/prac13$ joe /home/lucia.zamudio/prac1/prac13/p
rueba13 \
Ctrl+k, x -> guardar \
lucia.zamudio@polifemo:~/prac1/prac13$ joe ../prac12/prueba12

**8. Cree con el comando joe un fichero llamado ejemplo01 en el directorio prac11, usando rutas relativas, que contenga la frase: Esto es un fichero ejemplo creado con el joe en la practica 1**
lucia.zamudio@polifemo:~/prac1/prac13$ joe ../prac11/ejemplo01

**9. Copie los ficheros prueba12 y prueba13 al directorio prac11, mediante rutas relativas.**
lucia.zamudio@polifemo:~/prac1/prac13$ cp ../prac12/prueba12 ../prac13/prueba13 ../prac11

**10. Copie el fichero prueba12 del directorio prac12 al directorio prac14, mediante rutas relativas, con el nombre prueba14.**
lucia.zamudio@polifemo:~/prac1/prac13$ cp ../prac12/prueba12 ../prac14/prueba14

**11. Cree dentro del directorio prac12 dos directorios llamados temp1 y temp2, con rutas relativas.** \
lucia.zamudio@polifemo:~/prac1/prac13$ mkdir ../prac12/temp1 ../prac12/temp2 \

**12. Muévase al directorio prac1 con rutas relativas. Mueva el fichero prueba13 del directorio prac13 al directorio temp1 con rutas relativas. Copie los ficheros prueba12 del 
directorio prac12 y prueba14 al directorio temp1 con rutas relativas y con un solo comando y sin usar construcciones globales.**
lucia.zamudio@polifemo:~/prac1/prac13$ cd ..
lucia.zamudio@polifemo:~/prac1$ mv prac13/prueba13 prac12/temp1 \
lucia.zamudio@polifemo:~/prac1$ cp prac12/prueba12 prac14/prueba14 prac12/temp1


**13. Copie todos los ficheros del directorio temp1 que empiecen por p, el penúltimo carácter sea un 1 y terminen en un número del 1 al 5 al directorio temp2 utilizando las construcciones globales adecuadas y rutas relativas.**
lucia.zamudio@polifemo:~/prac1$ cp prac12/temp1/p*1[1-5] prac12/temp2

**14. Borre todos los ficheros del directorio temp1 cuyo penúltimo carácter sea un número usando construcciones globales y rutas absolutas**
lucia.zamudio@polifemo:~/prac1$ rm /home/lucia.zamudio/prac1/prac12/temp1/*[0-9]?

**15. Borre el directorio temp1 con rutas absolutas. Borre el directorio temp2 sin borrar previamente los ficheros que hay dentro y con rutas relativas (Se usa el comando rm con una opción. Busque la opción adecuada con la ayuda del comando man).**\
lucia.zamudio@polifemo:~/prac1$ man rm\
lucia.zamudio@polifemo:~/prac1$ rmdir /home/lucia.zamudio/prac1/prac12/temp1\
lucia.zamudio@polifemo:~/prac1$ man rm\
lucia.zamudio@polifemo:~/prac1$ rm -r prac12/temp2

**16. Muévase a su directorio personal con el comando más breve posible. Compruebe que está en su directorio personal con el comando correspondiente.**
lucia.zamudio@polifemo:~/prac1$ cd \
lucia.zamudio@polifemo:~$ pwd\
/home/lucia.zamudio 

**17. Vaya a la sesión en la que tiene editado el fichero p1.txt (sesión 2) con el joe. Salve el fichero con el nombre solp1.txt. Debe quedar grabado en el directorio prac1 con el nombre solp1.txt. Vuelva a la primera sesión.**

**19. Ejecute el comando: chmod 700 prac1/solp1.txt. Si nos da un error compruebe que el fichero solp1.txt tiene el nombre correcto y que se encuentra en el directorio prac1. Si no da errores, hemos terminado.**

