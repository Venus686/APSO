# EJERCICIOS PARA PRACTICAR
## EJERCICIO 1
(0,5 puntos)
 • Usando rutas relativas y con una sola orden cree la siguiente estructura de directorios:\
![Captura de pantalla 2025-03-31 161729](https://github.com/user-attachments/assets/537b3f00-5bde-4bcb-bc5c-e43f8990af76)

 • Muévase al directorio Temporal usando una ruta absoluta.\
 • Quite a todos los directorios creados, todos los permisos a los miembros del grupo y al resto de usuarios del sistema. Los permisos del propietario no deben cambiar. Use rutas relativas.
 ```bash

```
## EJERCICIO 2
 (0,75 puntos) – NO SE PUEDE USAR LA ORDEN find
 • Usando rutas absolutas, copie todos los ficheros del directorio /home/so/ficheros cuyo nombre  comience por una c (minúscula) o una C (mayúscula) al directorio Info.\
 • Usando rutas relativas, mueva los ficheros del directorio Info, cuyo nombre contenga un punto, seguido de cuatro caracteres o más al directorio Temporal.\
 • Usando rutas relativas, copie todos los ficheros del directorio Info, cuyo nombre contenga exactamente dos caracteres al directorio Resultados.\
 • Muévase a su directorio de usuario con la orden mas simple posible.\
 • Dé las ordenes necesarias para eliminar el directorio Temporal, incluyendo su contenido.
 ```bash

```

## EJERCICIO 3
 (0,75 puntos)
 • Modifique el fichero necesario para que después de “loguearse” en el sistema:\
 a. El directorio de trabajo (el directorio en que se encuentre en cada instante) esté incluido en la variable PATH.\
 b. Exista un alias llamado espacio que devuelva el espacio de disco disponible, expresado en Megabytes.\
 c. Muestre un mensaje de bienvenida, que incluya la hora y el día de la semana. Por ejemplo: “Bienvenido a Polifemo, son las hora:minutos del lunes”
 ```bash

```

## EJERCICIO 4
 (1 punto)
 • Genere un fichero en el directorio Resultados, llamado enlacesUSR que contenga la lista de enlaces simbólicos que cuelgan a partir del directorio /usr, que tienen exactamente dos caracteres en su nombre, y cuyo “estatus” haya cambiado hace más de 60 días. Los posibles  mensajes de error también deben aparecer en el fichero generado.\
 • Sin editar el fichero, añada al fichero generado anteriormente, una línea con su identificador de usuario y grupo y los grupos a los que pertenece.
 ```bash

```

## EJERCICIO 5
 (1 punto)
 • Visualice, el número (sólo el número) de instancias del proceso bash que están siendo ejecutadas en este instante por el usuario "pedro".\
 • Visualice, ordenadas alfabéticamente, las líneas de todos los usuarios conectados, que contengan la cadena “172.17.”\
 ```bash

```
## EJERCICIO 6
 (1 punto)
 • Con una sola orden, cuente las líneas que contengan la cadena include, de todos los ficheros que cuelguen a partir del directorio /usr y cuyo nombre comience por  “w” y finalice en “.c”
 ```bash

```

## EJERCICIO 7
 (0,75 puntos)
 • Descargue (sin instalar) el paquete jed\
 • Consulte en la caché de paquetes si está disponible el paquete tritium\
 • Programe una tarea con la orden at para que se ejecute a las 12:35 horas, que quite todos los permisos del directorio  ExamenS1.\
 • En su directorio de usuario, cree un fichero llamado examen.tgz que contenga el contenido comprimido de todo lo que contiene el directorio ExamenS1
 ```bash

```
## EJERCICIO 8
8)  (0,5 puntos)
 • Indique cómo eliminar del menú de arranque de grub, la versión del núcleo 3.8.0-29\
 • Indique si en Polifemo está activa la opción para que cada usuario creado pertenezca a un grupo con su nombre. En caso de que no sea así, ¿qué grupo se asigna?. Explique cómo ha obtenido la información.\
 • Visualice sus cuotas de disco, en formato “human-readable”.
```bash

```

## EJERCICIO 9
9) (1,25 puntos) Cree un guión, en el directorio Guiones, llamado Creador que tome un parámetro  y realice los siguiente:\
• Si el parámetro es una ruta a un directorio válido\
  ◦ Crea en dicho directorio un enlace simbólico llamado home que apunte a su directorio de usuario.\
 ◦ Crea una variable llamada RESULTADO que contenga la palabra LINK\
• En caso contrario,\
 ◦ Solicita por teclado un código de error\
 ◦ Crea una variable llamada RESULTADO que contenga el código de error introducido.\
 Ejecute el guión, pasándole como parámetro ~/ExamenS1/Guiones/Resultados/ y de forma que la variable NUEVOS esté disponible cuando el guión finalice.
```bash

```

## EJERCICIO 10
 10) (2,5 Puntos) Cree un guión, en el directorio Guiones llamado nuevos, que tome dos parámetros y realice los siguiente: \
 • Si el número de parámetros no es igual a 2 mostrará el mensaje “Se deben pasar dos  parámetros” y finalizará con un código de finalización -1.\
 • Si los dos parámetros  no son directorios válidos mostrará el mensaje “Ambos parámetros deben ser  directorios válidos” y finalizará.\
 • Para cada fichero, o directorio, que exista en el directorio pasado como primer parámetro (en dicho directorio, no en sus subdirectorios), que sea más nuevo que el directorio pasado como segundo parámetro, deberá añadir una línea con el mensaje “El fichero <ruta al fichero> es más reciente que <ruta al directorio>”, en un fichero llamado recientes dentro del directorio Resultados.\
 Al finalizar deberá mostrar el número de ficheros que cumplen la condición.\
 Ejecute el guión pasándole como parámetros las rutas a los directorios Info y /home/.
