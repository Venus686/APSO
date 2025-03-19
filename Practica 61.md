```markdown
#Contenido:
- Estructuras de control en guiones.
- if, case
- for, while, until
- break, continue

; -> acaba la orden y empieza otra nueva.
```bash
date;ps
```
```
###EVALUCIÓN ARITMÉTICA
expr-> devuelve el resultado de la siguiente operación
```bash
expr=6+8
RES=$( expr 5 + 8 )
RES=$(( 5000 + 8 )) -> DEJAR ESPACIO ENTRE LOS PARÉNTESIS Y LOS NÚMEROS
```
### EXPRESIONES CONDICIONALES
man test-> para ver las expresiones condicionales y las comparaciones
x -lt y - x menor que y

### IF
siempre va al comienzo de una línea, excepto si está separado por un ;
```bash
if condición
then
      comandos
[elif condición
 then
      comandos ]
[else
      comandos_alternativos ]
fi

```
### CASE
```bash
case expresion in
       valor1) comandos1
       comandos1;;
 valor2) comandos2
       comandos2;;
 ...
 *)      otros_comandos
       otros_comandos;;
esac
```
```bash
#!/bin/bash
 # Ejemplo de uso del case
 echo OPCIONES
 echo --------
 echo L - listar información del fichero $1
 echo V - visualizar contenido del fichero $1
 echo E - editar fichero $1
 echo R - borrar fichero $1
 echo
 echo -n "Selecciona una opción: "
 read OPCION
 clear
 case $OPCION in
       L) ls -l $1;;
       E) joe $1;;
       V) more $1;;
       R) rm -f $1;;
       l|e|r|a|v) echo Debes escribir la opción en mayúsculas.;;
       *) echo Esa opción no existe;;
 esac

```
-n -> la lectura a continuación de la línea (NO HAY SALTO DE LÍNEA)
doble ; -> para hacer el break

### FOR -> recorrer una lista
```bash
for variable in conjunto
do
       comandos
done
```
```bash
#!/bin/bash
# Ejemplo de uso del for
for i in 8 10 2 5 pepe
do
      echo "Esta es la iteracion para $i"
      echo "Visualizo la iteracion +10 = $(($i+10))"
done
```
```bash
for ((i=1; i<10;i++))
do 
      echo
done
```

### WHILE
```bash
while condición
do
       comandos
done
```

### UNTIL
```bash
until condición
do
       comandos
done
```
# Ejercicios


## Ejercicio 1
### Cree con un solo comando el siguiente árbol de directorios a partir de su directorio personal mediante rutas relativas.
```bash
lucia.zamudio /home/lucia.zamudio>mkdir -p prac6/prac6 prac6/fuentes/tmp1 prac6/fuentes/tmp2 prac6/guiones
```
## Ejercicio 2
### Incluya dentro del fichero .profile la variable GUION con la ruta al directorio guiones creado anteriormente. Haga que tome efecto esta variable. Copie todos los ficheros que a partir de su directorio personal terminen en .txt en el directorio tmp1.
```bash
GUION=/home/lucia.zamudio/prac6/guiones
export GUION
lucia.zamudio /home/lucia.zamudio>cp $(find ~ -type f -name "*.txt" ./prac6/fuentes/tmp1
lucia.zamudio /home/lucia.zamudio>cp $(find ~ -type f -name "*.txt") ./prac6/fuentes/tmp1
lucia.zamudio /home/lucia.zamudio>ls prac6/fuentes/tmp1
```
## Ejercicio 3
### Muévase al directorio guiones. Cree un guión en el directorio guiones llamado tratafichero. Este guión debe recoger un único parámetro. Si el parámetro es un fichero ordinario debe visualizar su contenido con el comando more. Si se trata de un directorio, se debe ver el contenido del mismo con el comando ls -la. Si no es ni un fichero ni un directorio debe hacerse un echo del parámetro. (Se necesita usar el comando test y la estructura if).
```bash
lucia.zamudio /home/lucia.zamudio>cd prac6/guiones
if [ -f $1 ] ; then
        more $1
elsif test -d $1
        ls -la $1
else
        echo $1
fi
lucia.zamudio /home/lucia.zamudio/prac6/guiones>chmod u+x tratafichero
lucia.zamudio /home/lucia.zamudio/prac6/guiones>tratafichero ../fuentes/tmp1/f1.txt

```
## Ejercicio 4
### Muévase al directorio prac6 que está dentro de prac6. Ejecute desde aquí el guión anterior dos veces. La primera vez pásele como parámetro $HOME/prac2/f1.txt. La segunda pásele como parámetro la variable GUION creada en el apartado 2.
```bash
lucia.zamudio /home/lucia.zamudio/prac6/guiones>cd ../prac6
lucia.zamudio /home/lucia.zamudio/prac6/prac6>../guiones/tratafichero $HOME/
prac2/f1.txt
lucia.zamudio /home/lucia.zamudio/prac6/prac6>../guiones/tratafichero $GUION

/home/lucia.zamudio/prac6/guiones
```
## Ejercicio 5
### Muévase al directorio guiones. Cree un guión llamado fpfinal que copie todos los nombres de enlaces simbólicos encontrados en un directorio especificado, cuyo nombre coincida con el segundo parámetro, y los guarde en un archivo enlaces.txt dentro del tercer directorio especificado. Los errores no deben mostrarse en pantalla.
```bash
lucia.zamudio /home/lucia.zamudio/prac6/prac6>cd ../guiones
#!/bin/bash
if [ $# != 3 ]; then
        echo "Se necesitan al menos 3 parámetros"
elif test ! -d $1 | test ! -d $3; then
        echo "El primer y tercer parámetro han de ser directorios"
else
        find $1 -type l -name "$2" -printf "%f\n" 2> /dev/null > $3/enlaces.
fi

```
## Ejercicio 6
### Cree un guión llamado mtam que muestre, para cada fichero encontrado a partir del directorio pasado como primer parámetro cuyo nombre coincide con el segundo parámetro, su tamaño. Compruebe que el número de parámetros es el correcto y que el primero es un directorio. (Usa el for en el guión).
```bash
#!/bin/bash
if [ $# -eq 2 ] & [ -d $1 ];then
for i in $(find $1 -name "$2" )
do
         echo $(wc -c $i)
done
else
        echo"Ha habido un error."
fi
```
## Ejercicio 7
### Cree un guión llamado anida, al que se le pasará un parámetro y deberá hacer lo siguiente: Pedirá que se introduzca un número por el teclado y creará tantos directorios anidados como indique el número leído, a partir del directorio en el que nos encontramos.
```bash
lucia.zamudio /home/lucia.zamudio/prac6/guiones>joe anida
#!/bin/bash
BUCLE=0
dir=$PWD
echo  "Introduce un numero: "
read NUM
while [ $BUCLE -lt $NUM ]
do
        mkdir $dir/$1
        dir=$dir/$1
        BUCLE=$(($BUCLE + 1))
done
lucia.zamudio /home/lucia.zamudio/prac6/guiones>cd ../fuentes/tmp2
lucia.zamudio /home/lucia.zamudio/prac6/fuentes/tmp2>../../guiones/anida p6
Introduce un numero:
3
```

## Ejercicio 8
### Muévase al directorio guiones. Cree un guión llamado opcion que lea una palabra del teclado. Si la palabra empieza por un número almacena la palabra en un fichero llamado numero, en un fichero llamado vocal si empieza por vocal y en un fichero llamado otro para cualquier otro caso. Use el case para decidir en qué fichero guardar la palabra.
```bash
lucia.zamudio /home/lucia.zamudio/prac6/fuentes/tmp2>cd ../../guiones


```
## Ejercicio 9
### Modifique los permisos de los directorios tmp1 y tmp2 para que el propietario tenga todos los permisos menos el de ejecución, el grupo solo el de lectura y los otros solo el de ejecución.
```bash

```
## Ejercicio 10
### Consulte el número de procesos total que tiene activos en este preciso momento (contando los de todas las ventanas abiertas). (Se usa ps y wc).
```bash

```
