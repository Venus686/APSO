# Contenido:

Tipos de Shell: sh, ksh, bash
-Variables: set, unset
- Alias: alias, unalias
- Configuraciones: PS1, .profile, .bashrc


# Consejos:

- Use el tabulador para completar las rutas.
- Compruebe el resultado de las órdenes que ejecute.
- Use `man` para obtener ayuda de las distintas órdenes.
  
---

# Enunciado:

## Ejercicio 1
1. Muestre por pantalla el texto “Practica 4: Manejo de Shell – Inicio…”
```bash 
  lucia.zamudio@polifemo:~$ echo "Pracica4: Manejo de Shell – Inicio…"
  Pracica4: Manejo de Shell – Inicio…
```
## Ejercicio 2
2. Cree un directorio llamado Practica4 dentro de ModuloI. Dentro de este
último, cree otro llamado temp.
```bash
lucia.zamudio@polifemo:~$ mkdir -p ModuloI/Practica4/temp
lucia.zamudio@polifemo:~$ rm -r ModuloI/Practica4
lucia.zamudio@polifemo:~$ cd ModuloI/
lucia.zamudio@polifemo:~/ModuloI$ mkdir Practica4
lucia.zamudio@polifemo:~/ModuloI$ cd Practica4
lucia.zamudio@polifemo:~/ModuloI/Practica4$ mkdir temp
```

## Ejercicio 3
3. Visualice el valor de todas las variables definidas en el sistema
mostrándolas pantalla a pantalla
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica4$ set|more
```

4. Ejecute el shell ksh. ¿Qué cambios observa? ¿Funciona la tecla de
tabulación de la misma forma?
```bash
No
```

## Ejercicio 4
8. Ejecute el shell sh. ¿Qué cambios observa? ¿Funciona la tecla de
tabulación de la misma forma?
NO

## Ejercicio 5
5. Ejecute el shell sh. ¿Qué cambios observa? ¿Funciona la tecla de
tabulación de la misma forma?

## Ejercicio 6
6. Salga de las shell que ha ejecutado y vuelva a bash.
```bash
$ exit
~/ModuloI/Practica4 [5]$ exit
```

## Ejercicio 7
7. Active el atributo de la shell xtrace (para mostrar el comando a ejecutar).
```bash
lucia.zamudio@polifemo:~$ set -x
```

## Ejercicio 8-> (Revisar)
8. Desde su directorio de usuario, ejecute la orden necesaria para copiar los ficheros que haya desde el directorio raíz, que comiencen por rmt al directorio temp creado anteriormente y observar el resultado (use para ello sustitución de comandos).
 ```bash
lucia.zamudio@polifemo:~/ModuloI$ cp $(find / -type f -name "rmt*" 2>/dev/nu
ll)  ./Practica4/temp
```

## Ejercicio 9
9. Desactive el atributo activado en el punto anterior.
```bash
lucia.zamudio@polifemo:~/ModuloI$ set +x
+ set +x
```

## Ejercicio 10
10.Cree una variable llamada P4 que contenga la ruta absoluta al directorio Practica4.
```bash
lucia.zamudio@polifemo:~/ModuloI$ P4=/home/lucia.zamudio/ModuloI/Practica4
```
## Ejercicio 11
11.Use la variable P4 para moverse al directorio Practica4
```bash
lucia.zamudio@polifemo:~/ModuloI$ cd $P4
```
## Ejercicio 12
12.isualice la ayuda de la orden echo.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica4$ man echo
```
## Ejercicio 13
13.Visualice por pantalla el mensaje “El directorio de trabajo actual es <<ruta al directorio de trabajo actual>>”. Haga uso de la variable PWD.
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica4$ echo "El directorio de trabajo actual es $PWD"
El directorio de trabajo actual es /home/lucia.zamudio/ModuloI/Practica4
```

## Ejercicio 14
14.Elimine la variable HOME.
```bash

```

## Ejercicio 15
15.Muévase a su directorio de usuario mediante la orden cd sin argumentos. ¿Qué ocurre?
```bash
lucia.zamudio@polifemo:~/ModuloI/Practica4$ unset HOME
```

## Ejercicio 16
16.Cree un fichero llamado losalias, en el directorio Practica4, que contenga todos los alias definidos ordenados en orden inverso
```bash
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ alias | sort -
r >losalias
```

## Ejercicio 17
17.Cree un alias llamado fecha, que visualice la fecha en formato “23 del 11 de 2009”
```bash
%d-> día
%m -> mes
%Y -> Año
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ alias fecha='date +"%d del %m de %Y"'
```

## Ejercicio 18
18.Restaure la variable home a su directorio personal.
```bash
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ alias HOME=/home/lucia.zamudio
```

## Ejercicio 19
19.Cree un alias llamado p4, que cambie siempre al directorio Practica4 desde cualquier ubicación.
```bash
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ alias P4='cd /
home/lucia.zamudio/ModuloI/Practica4'
```

## Ejercicio 20
20.Cámbiese al directorio Practica2 y use el alias p4 para moverse al directorio Practica4.
```bash
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ cd ../Practica2
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica2$ P4
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$
```

## Ejercicio 21
21.Modifique el prompt para que muestre el nombre del usuario en vez del nombre de la máquina, únicamente en la sesión en la que se realiza esta orden.
```bash

```

## Ejercicio 22
22.Haga que la variable PATH incluya la ruta al directorio de usuario de forma
permanente.
```bash

```
## Ejercicio 23
23.Haga que cada vez que acceda al sistema, se muestre un mensaje de
bienvenida que incluya su nombre de usuario.
```bash

```
## Ejercicio 24
24.Elimine el alias p4 creado anteriormente
```bash
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ unalias P4
```
## Ejercicio 25
25.Muestre en pantalla el mensaje “Práctica 4: Manejo de Shell… Finalizada”
```bash
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ echo  “Práctica 4: Manejo de Shell… Finalizada”
“Práctica 4: Manejo de Shell… Finalizada”
```
## Ejercicio 26
26.Salga adecuadamente del sistema
```bash
lucia.zamudio@polifemo:/home/lucia.zamudio/ModuloI/Practica4$ exit
```
