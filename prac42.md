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


9. Desde su directorio de usuario, ejecute la orden necesaria para copiar los
ficheros que haya desde el directorio raíz, que comiencen por rmt al
directorio temp creado anteriormente y observar el resultado (use para ello
sustitución de comandos).
10. Desactive el atributo activado en el punto anterior.
10.Cree una variable llamada P4 que contenga la ruta absoluta al directorio
Practica4.
11.Use la variable P4 para moverse al directorio Practica4
