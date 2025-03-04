#Practica3.1
**1. Cree con un solo comando el siguiente árbol de directorios a partir de su
directorio personal con rutas relativas.**\
lucia.zamudio@polifemo:~$ mkdir -p prac3/prac31/tmp1  prac3/prac32/tmp2 prac3/prac33/tmp3 .

**2. Quite todo tipo de privilegios para el grupo y el resto de los grupos a los directorios prac3, prac31, prac32 y prac33 usando rutas relativas. El propietario deberá tener todos los permisos sobre esos directorios**\
lucia.zamudio@polifemo:~$ chmod 700 prac3 ./prac3/prac31 ./prac3/prac32 ./prac3/prac33

**3. Visualice todos los ficheros y directorios de su directorio personal (incluso
los ocultos), con los permisos establecidos sobre cada uno de ellos.**\
lucia.zamudio@polifemo:~$ ls -l -a

**4. Con el comando find, el wc y las tuberías cuente cuántos directorios tiene a partir de su directorio personal que tengan una m o un número en su nombre.** 
lucia.zamudio@polifemo:~$ find /home/lucia.zamudio -type d -name "*[m0-9]*" |wc -l

**5. Busque, a partir del directorio /bin, todos los ficheros (no directorios) que comiencen por vocal y se hayan modificado hace más de 1 día. La salida de ese comando la debe enviar a un fichero llamado comandos que se guardará en el directorio tmp1 de prac31. No deben aparecer los errores por pantalla. Hágalo con sólo una línea de comando. **
lucia.zamudio@polifemo:~$ find /bin -type f -name "[aAeEiIoOuU]*" -mtime +1 >./prac3/prac31/tmp1/comandos.txt 2>/dev/null

** 6. Encuentre todos los ficheros del sistema (del tipo que sean: normales, directorios, enlaces, de dispositivo, etc....) cuyo primer carácter sea una vocal o un número, la segunda no sea un número, termine en .c o .p y su nombre tenga sólo 6 caracteres (contando el punto y la extensión). La salida debe ser visualizada página a página y los errores no deben mostrarse por pantalla.**
lucia.zamudio@polifemo:~$ more |(find / -type f -name "[aAeEiIoOuU0-9][!0-9]
??.[cp]" 2>/dev/null)

**7. Copie todos los ficheros que tenga a partir de su directorio personal que empiecen con el texto sol y tengan una p en su nombre en el directorio tmp2 del directorio prac32. Use para ello sustitución de comandos.**
lucia.zamudio@polifemo:~$ cp $(find ~ -type f -name "sol*p*") prac3/prac32/tmp2/

**8. Muévase al directorio prac33. Mueva todos los ficheros que a partir de su directorio personal terminan en ~ al directorio tmp3. Borre del directorio tmp3 todos los ficheros que terminan en ~. (Asegúrese antes que sólo tiene ficheros que terminan en ese carácter - Alt+126). **
lucia.zamudio@polifemo:~$ cd prac3/prac33
lucia.zamudio@polifemo:~/prac3/prac33$ mv $(find ~ -type f -name "*~") ./tmp3/

**9. Muévase al directorio prac3 con rutas relativas. Cree con el comando cal, y tras ejecutarlo 4 veces, un fichero llamado 2_cuatrimestre en el directorio prac32 con el calendario de los meses de marzo, abril, mayo y junio de este año.**
lucia.zamudio@polifemo:~/prac3/prac33$ cd ..
lucia.zamudio@polifemo:~/prac3$ cal 03 2025 >prac32/2_cuatrimestre.txt
lucia.zamudio@polifemo:~/prac3$ cal 04 2025 >>prac32/2_cuatrimestre.txt
lucia.zamudio@polifemo:~/prac3$ cal 05 2025 >>prac32/2_cuatrimestre.txt
visualizar
lucia.zamudio@polifemo:~/prac3/prac32$ cat 2_cuatrimestre.txt

**10. Introduzca la siguiente lista por teclado mediante el comando sort de forma que al final obtenga un fichero llamado ciudades en el directorio prac32 con la lista ordenada (en orden descendente) de lo introducido por teclado:**
cordoba
sevilla
huelva
almeria
cadiz
malaga
jaen
granada 
lucia.zamudio@polifemo:~/prac3$ sort -r 1> prac32/ciudades
visualizar lucia.zamudio@polifemo:~/prac3$ cat prac32/ciudades

**11. Cree un fichero llamado usuarios en el directorio prac32 con la lista de todos los directorios personales de los usuarios del sistema, ordenada alfabéticamente en orden ascendente y con una sola línea de comando (Para ello use el find con las opciones oportunas, el sort, tuberías y redirección)(Suponga que cada directorio del directorio /home es de un
usuario del sistema)(Deben salir sólo los directorios y sólo su nombre -no la ruta- (se consigue con la opción -printf))(Cada directorio estará en una linea del fichero)(No hay que adentrarse en las carpetas de cada usuario (opción -maxdepth). **
lucia.zamudio@polifemo:~/prac3$ find /home -type d -maxdepth 1 -printf "%f\n
" |sort >prac32/usuarios

**12. Cree en el directorio prac32 un fichero llamado personal que contenga 4 líneas con la siguiente información: nombre de usuario, identificador de usuario, nombre de grupo, identificador de grupo. No está permitido usar ningún editor de textos para crear este fichero (Hay que ejecutar 4 veces el comando id.**
-un -> nombre usuario
-u -> id usuario
-g -> id grupo
-gn ->nombre grupo
lucia.zamudio@polifemo:~/prac3$ id -un >prac32/personal
lucia.zamudio@polifemo:~/prac3$ id -u >>prac32/personal
lucia.zamudio@polifemo:~/prac3$ id -g >>prac32/personal
lucia.zamudio@polifemo:~/prac3$ id -gn >>prac32/personal

