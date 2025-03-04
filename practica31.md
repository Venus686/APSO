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
 
