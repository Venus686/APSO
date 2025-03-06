### Contenido:
### Tipos de shell (sh, ksh, bash)
sh -> tipo de shell basico, con distinta apariencia
Nosotros usamos bash
Se ejecutan con sh o ksh + ENTER
Se siguen ejecutando todos los programas a la vez, uno encima de otro
Con los exits se va saliendo de cada uno de los tipos de shell

### BASH
OPCIONES DE BASH
ls -d ?? -> muestra los nombres de los directorios cuyo nombre tenga 2 caracteres, no muestra su contenido
set -o -> que opciones estan encendidos del bash y que comportamientos estan desactivos
history on -> recuperar ordenes amtiguas(con la fecha)
noglob-> no utilices expresiones globales (?, [], *)
set -o | more -> visualizas el contenido 
set +o noglob (+f) -> se apaga la opción
set -o noglob -> enciende la opción
si hacemos ls -d ?? , pone las ?? como si fuese un directorio y no como opción global
Existen abreviaturas para la mayoria de opciones.
HELP set -o
set -o verbose -> sobre date
set -o xtrace (-x)-> se ve como se hace la acción, cómo el la ejecuta, sirve para ver bien la sustitución


### Variables (set, unset)
### Alias
alias creadir ="mkdir"
Un alias también puede ser una búsqueda 

### Opciones
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

```
## Ejercicio 3
3. Muévase al directorio prac42. Cree con el cat un fichero en el directorio tmp1 que se llame prueba y contenga la frase Este es un fichero de prueba. Añada con el comando cat una nueva frase al fichero sin borrar la anterior que diga Esta frase se ha añadido después
```bash

```

## Ejercicio 4
4. Visualice el contenido de las primeras 52 variables del sistema. Muestre por
pantalla el contenido de la variable PATH (sólo esa variable) 
```bash

```

## Ejercicio 5

```bash

```

## Ejercicio 6

```bash

```


## Ejercicio 7

```bash

```


## Ejercicio 8

```bash

```

## Ejercicio 9

```bash

```
