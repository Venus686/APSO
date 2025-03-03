# Contenido:

- cd, mkdir, rmdir, pwd
- ls, cp, mv, rm, cat, more, echo
- Construcciones globales (*, ?, [1])
- Edición de ficheros (joe)
- Rutas Relativas y absolutas

# Consejos:

- Use el tabulador para completar las rutas.
- Compruebe el resultado de las órdenes que ejecute.
- Use man para obtener ayuda de las distintas órdenes.

# Enunciado:

*NOTAS:*

Antes de comenzar a realizar la práctica será indispensable haber cambiado la clave de acceso a Polifemo (orden: passwd).

Mientras no se indique, no se puede cambiar de directorio.

Será necesario usar los tipos de ruta que se indican en cada orden. Si no se indica ninguno, se podrá usar cualquiera.

1. Muestre por pantalla el texto “Practica 1: Manejo de Shell – Inicio…”
  shell
lucia.zamudio@polifemo:~$ echo o “Practica 1: Manejo de Shell – Inicio…”

2. Visualice la ruta de su directorio de trabajo (directorio en el que se encuentra).
  bash
lucia.zamudio@polifemo:~$ pwd


4. Visualice el contenido de su directorio de trabajo en formato largo (mostrando los detalles de cada fichero o directorio).
  bash
lucia.zamudio@polifemo:~$ ls -l

5. Cree un directorio que sea hijo de su directorio de usuario con el nombre ModuloI. (Atienda el uso de mayúsculas y minúsculas).
  bash
lucia.zamudio@polifemo:~$ mkdir ModuloI

6. Cree dentro de ModuloI un directorio llamado Practical. Use una ruta absoluta.
  bash
lucia.zamudio@polifemo:~$ mkdir /home/lucia.zamudio/ModuloI/Practica1

8. Muévase al directorio Practical. Se debe usar una ruta relativa.
  bash
lucia.zamudio@polifemo:~$ cd ModuloI/Practica1/

9. Dentro del directorio Practical, cree la siguiente estructura de directorios. Se deben usar rutas absolutas. (Consulte en el man la opción -p de mkdir).
  bash
lucia.zamudio@polifemo:~/ModuloI/Practica1$ mkdir -p /home/lucia.zamudio/ModuloI/Practica1/Datos/Temporal  /home/lucia.zamudio/ModuloI/Practica1/Datos/basura

8. Visualice el contenido de su directorio de trabajo en formato largo (mostrando los detalles de cada fichero o directorio). Se debe usar una ruta absoluta.
  bash
lucia.zamudio@polifemo:~/ModuloI/Practica1$ ls -l /home/lucia.zamudio

9. Visualice el contenido del directorio raíz en formato largo (mostrando los detalles de cada fichero o directorio). Se debe usar una ruta relativa.
  bash
lucia.zamudio@polifemo:~/ModuloI/Practica1$ ls -l ../..

11. Copie los ficheros soneto y cancion, que están en el directorio /home/so/ficheros, al directorio Practical con una sola orden. Use rutas relativas.
  bash
lucia.zamudio@polifemo:~/ModuloI/Practica1$ cp ../../../so/ficheros/soneto 
 ../../../so/ficheros/cancion .

12. Muévase al directorio ModuloI.
lucia.zamudio@polifemo:~/ModuloI/Practica1$ cd ..


14. Copie el fichero soneto del directorio Practical al directorio Temporal con el nombre estrofa. Use rutas relativas.
lucia.zamudio@polifemo:~/ModuloI$ cp ./Practica1/soneto ./Practica1/Datos/Temporal/estrofa


16. Mueva el fichero cancion desde el directorio Practical al directorio Datos.
lucia.zamudio@polifemo:~/ModuloI$ mv ./Practica1/cancion ./Practica1/Datos/

17. Visualice el contenido del fichero estrofa del directorio Temporal.
    lucia.zamudio@polifemo:~/ModuloI$ more ./Practica1/Datos/Temporal/estrofa
    lucia.zamudio@polifemo:~/ModuloI$ cat ./Practica1/Datos/Temporal/estrofa


19. Cambie el nombre del fichero soneto por el de verso.
lucia.zamudio@polifemo:~/ModuloI$ mv Practica1/soneto ./Practica1/verso
 

A partir de aquí se puede cambiar de directorio cada vez que se quiera. Se puede usar también cualquier tipo de ruta.

16. Copie todos los ficheros del directorio /home/so/ficheros cuyo nombre comience por f al directorio Datos.
  lucia.zamudio@polifemo:~/ModuloI$ cp /home/so/ficheros/f* ./Practica1/Datos/

17. Ubicados en el directorio ficheros anterior, liste detalladamente todos los ficheros:
    lucia.zamudio@polifemo:~/ModuloI$ cd /home/so/ficheros
    a) cuyos nombres terminen con un número.
         lucia.zamudio@polifemo:/home/so/ficheros$ ls -l *[0-9]
        
    b) cuyos nombres no comiencen con ninguna vocal (ni mayúsculas ni minúsculas).
        lucia.zamudio@polifemo:/home/so/ficheros$ ls -l [!aAeEiIoOuU]*
      
        
    c) cuyos nombres no comiencen por ningún número.
        lucia.zamudio@polifemo:/home/so/ficheros$ ls -l [!0-9]*
     
        
    d) cuya extensión tenga exactamente 3 caracteres.
      lucia.zamudio@polifemo:/home/so/ficheros$ ls -l *.???
    
    e) cuya extensión tenga más de 3 caracteres.
      lucia.zamudio@polifemo:/home/so/ficheros$ ls -l *.????*
        
    f) cuya extensión sea bak y el nombre comience por una letra.
      lucia.zamudio@polifemo:/home/so/ficheros$ ls -l [a-zA-Z]*.bak
         
        
19. Borre todos los ficheros del directorio Datos cuyo nombre esté compuesto de dos caracteres.
    lucia.zamudio@polifemo:~$ cd /home/lucia.zamudio/ModuloI/Practica1/Datos/
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ rm ??
 

20. Copie todos los ficheros del directorio Datos, cuyo nombre finalice en un número, al directorio Temporal.
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ cp ./*[0-9] ./Temporal/
  

21. Visualice, de forma que se pare cada vez que se llene la pantalla, el contenido del fichero fichcacion.
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ more ./fichcancion
  

22. Visualice el contenido de su directorio de usuario, incluyendo el contenido de los subdirectorios, en formato largo y ordenados por tamaño de menor a mayor. Use el manual para conocer las opciones necesarias.
  cd ~
  man 1 ls
  Vemos que las opciones complementarias son -S y -R
  ls -l -S -R  ls -lSR
  

23. Consulte la ayuda de la orden rm. ¿Para qué se usa la opción –r?
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ man rm
  

24. Borre el directorio Temporal. Use las órdenes que sean necesarias. 
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ rm -r ./Temporal/
    
  

26. Cree un directorio llamado tmpfiles que sea hijo del directorio Datos.
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ mkdir tmpfiles
  

27. En el directorio tmpfiles, cree un archivo llamado file1.txt usando el editor joe.
      lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos/tmpfiles$ cat> file2.txt


28. En el directorio tmpfiles, cree un archivo llamado file2.txt mediante la orden cat.
  lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos/tmpfiles$ cat> file2.txt


29. Muestre por pantalla la conjunción de los ficheros creados anteriormente.
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ joe ./tmpfiles/file1.txt

30. Edite el fichero file1.txt con el editor joe para almacenar información de al menos 20 líneas.
    joe file1.txt
   

32. Muestre la información del fichero anterior, donde cada 5 líneas vaya pausando la salida por pantalla.
    more -5 file1.txt
  

33. En el mismo directorio tmpfiles, cree un fichero de la manera que desee y llámelo file-text.txt.
  lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos/tmpfiles$ mkdir filetext.txt
  

34. ¿Cómo listaría detalladamente los ficheros cuyo nombre contengan un guión?
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos/tmpfiles$ ls -l *[-]*
  

35. Acceda con una sola instrucción a su directorio usuario.
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos/tmpfiles$ cd
  

36. Estando en el directorio de trabajo Datos, elimine mediante ruta absoluta el fichero file2.txt que se ubica dentro del directorio tmpfiles.
    lucia.zamudio@polifemo:~$ cd ./ModuloI/Practica1/Datos/
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ rm /home/lucia.zamudio/ModuloI/Practica1/Datos/tmpfiles/file2.txt
  

37. Mediante ruta relativa, borre el directorio tmpfiles haciendo uso de los comandos que necesite.
    lucia.zamudio@polifemo:~/ModuloI/Practica1/Datos$ rm -r ./tmpfiles/
  

38. Limpie la pantalla.
  bash
  clear

39. Muestre en pantalla el mensaje “Práctica 1: Manejo de Shell… Finalizada”.
bash
echo “Práctica 1: Manejo de Shell… Finalizada”.

40. Salga adecuadamente del sistema.
  bash
exit
