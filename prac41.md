### Contenido:
### Tipos de shell (sh, ksh, bash)
sh -> tipo de shell basico, con distinta apariencia
Nosotros usamos bash
Se ejecutan con sh o ksh + ENTER
Se siguen ejecutando todos los programas a la vez, uno encima de otro
Con los exits se va saliendo de cada uno de los tipos de shell

### BASH
OPCIONES DE BASH
ls -d ?? -> muestra los nombres de los directorios cuyo nombre tenga 2 caracteres, no muestra su contenido \
set -o -> que opciones estan encendidos del bash y que comportamientos estan desactivos
history on -> recuperar ordenes amtiguas(con la fecha) \
noglob-> no utilices expresiones globales (?, [], *) \
set -o | more -> visualizas el contenido \
set +o noglob (+f) -> se apaga la opción \
set -o noglob -> enciende la opción \
si hacemos ls -d ?? , pone las ?? como si fuese un directorio y no como opción global
Existen abreviaturas para la mayoria de opciones. \
HELP set -o \
set -o verbose -> sobre date
set -o xtrace (-x)-> se ve como se hace la acción, cómo el la ejecuta, sirve para ver bien la sustitución

### Variables (set, unset)
V1 ="Mensaje 1"
echo V1 -> sale V1
echo  $V1
$V1 para usarla
unset V1 -> eliminar la variabler
PATH -> variable que contiene rutas

### Alias
alias creadir ="mkdir"
Un alias también puede ser una búsqueda 
Para eliminar el alias ->unalias creadir
alias -> te dice que alias has creado

### Opciones
etc/profile -> lo que hay cada vez que iniciamos sesion(login nuevo, global) ->/etc/login
shell nuevo(terminal nuevo) -> /etc/bash.basrc
.profile (visualizar)
grep bashrc .profile
MODIFICAR EL BASHRC -> cambiar la configuración que está establecida para siempre

cp .bashrc basrc_original
joe .bashrc

echo $USER
echo $SHELL
which bash
echo $HOME -> directorio de usuario de la variable user
echo $HISFILE


### Ficheros de arranque

#Ejercicios

## Ejercicio 1
1. Cree con un solo comando el siguiente árbol de directorios a partir de su
directorio personal. 
```bash
lucia.zamudio@polifemo:~$ mkdir -p prac4/prac41  prac4/prac42/tmp1 prac4/prac42/tmp2  prac4/prac43
````

## Ejercicio 2
2. Muévase al directorio prac43. Quite todo tipo de permisos para el grupo y el resto de los grupos al directorio prac4, prac42, tmp1 y tmp2 con un sólo comando y usando rutas relativas.
```bash
lucia.zamudio@polifemo:~$ cd prac4/prac43
lucia.zamudio@polifemo:~/prac4/prac43$ chmod 700 ../ ../prac42 ../prac42/tmp1 ../prac42/tmp2
```
## Ejercicio 3
3. Muévase al directorio prac42. Cree con el cat un fichero en el directorio tmp1 que se llame prueba y contenga la frase Este es un fichero de prueba. Añada con el comando cat una nueva frase al fichero sin borrar la anterior que diga Esta frase se ha añadido después
```bash
lucia.zamudio@polifemo:~/prac4/prac43$ cd ../prac42
lucia.zamudio@polifemo:~/prac4/prac42$ cat > ./tmp1/prueba.txt
Este es un fichero de prueba.
lucia.zamudio@polifemo:~/prac4/prac42$ cat >> ./tmp1/prueba.txt

Esta frase se ha añadido después
```

## Ejercicio 4
4. Visualice el contenido de las primeras 52 variables del sistema. Muestre por
pantalla el contenido de la variable PATH (sólo esa variable) 
```bash
lucia.zamudio@polifemo:~/prac4/prac42$ set | head -52
lucia.zamudio@polifemo:~/prac4/prac42$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

## Ejercicio 5
5. Cree una variable llamada ORIGEN que contenga la ruta absoluta al directorio /home/so/velez/MI. Cree dos variables llamadas DESTINO1 y DESTINO2 con la ruta absoluta al 
 directorio tmp1 y tmp2 respectivamente del directorio prac42. Visualice el contenido de estas dos variables (sólo de estas dos). Use las variables ORIGEN y DESTINO1 para copiar todos los ficheros del directorio /home/so/velez/MI que contienen una p en su nombre y terminan en .txt al directorio tmp1 de prac42
```bash
lucia.zamudio@polifemo:~/prac4/prac42$ ORIGEN="/home/so/velez/MI"
lucia.zamudio@polifemo:~/prac4/prac42$ DESTINO1="/home/prac42/tmp1/"
lucia.zamudio@polifemo:~/prac4/prac42$ DESTINO2="/home/prac42/tmp2/"
lucia.zamudio@polifemo:~/prac4/prac42$ $DESTINO1

```

## Ejercicio 6
6. Muévase al directorio prac43 con rutas relativas. Cree un alias llamado fnuevos que busque los ficheros (no directorios) a partir de su directorio personal a los que se haya accedido hace menos de 3 horas, empiecen por punto y terminen en e, y o c y visualice su contenido uno a uno 
```bash

```


## Ejercicio 7
7. Visualice todos los alias del sistema. Cree cinco nuevos alias:
Uno se llamará dir y visualizará página a página todos los ficheros del directorio en el que está (incluso los que empiezan por punto), con todos los permisos en orden alfabético.dirinverso hará lo mismo pero saldrán ordenados en orden inverso

 Otro se llamará fecha y visualizará la fecha con el siguiente formato:
Hoy es <día de la semana>, <día del mes> de <mes> de <año>. Chao

El otro se llamará hora y visualizará la hora con el siguiente formato:
Son las <hora> horas y <minuto> minutos. Chao
El último debe conseguir que cuando ejecute cd.. (sin el espacio en blanco entre el cd y los dos puntos) no produzca error 

```bash

```


## Ejercicio 8
8. Cree un fichero llamado usuarios en el directorio tmp2 con la lista de todas las sesiones que hay abiertas en este instante ordenadas alfabéticamente.
Use rutas relativas 
```bash

```

## Ejercicio 9
. Muévase al directorio prac4. Ejecute el interprete de comandos ksh. Visualice las variables activas en este interprete de comandos. Modifique el prompt para que visualice la frase Comando::>
```bash

```
## Ejercicio 10
10. Salga del interprete de comandos ksh y vuelva al bash. Cuente con la ayuda del who y del wc el número de sesiones que hay abiertas (debe salir un número) 

```bash

```

## Ejercicio 11
11. Modifique el prompt principal para que visualice su nombre de usuario en vez del nombre de la máquina. A continuación el directorio donde está mediante ruta absoluta y al final debe aparecer el símbolo > (Ejemplo: Para el usuario velez actualmente sale velez@Polifemo:~/prac4$. Después de modificar el prompt debe salir velez: /home/velez/prac4> ) 
```bash

```

## Ejercicio 12
12. Modifique el prompt secundario para que emita el siguiente mensaje: cierre las comillas, por favor
```bash

```
## Ejercicio 13
13. Edite con el joe el fichero .profile. Modifique la variable PATH para que siempre se ejecuten los ficheros que se encuentran en el directorio actual. Añada la variable ORIGEN creada en el apartado 5 para que se pueda usar siempre que entre en una nueva sesión 

```bash

```

## Ejercicio 14
14. Cierre la sesión. Vuelva a entrar. Añada los alias hora y fecha al .profile para que siempre se puedan ejecutar. Haga lo necesario para que los alias introducidos en el .profile se vuelvan activos y puedan ser usados. 
```bash

```

