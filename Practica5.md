# GUIONES/ SCRIPTS
### $
 $variable -> Ejemplo-> echo home vale $HOME \

````bash
  -> $(orden) = `orden ` 
````
  ACENTO GRAVE -> `   `

### \ 
echo \$PATH contiene $PATH 
La \ quita el significado al caracter siguiente
ls a* -> ls a\*

### COMILLAS SIMPLES Y COMILLAS DOBLES
Si está entre comillas se asumirá como una cadena. \
Pero las comillas dobles si interpretan los carácteres \ ` y $. \
Ejemplo \
echo 'la variable HOME contiene $HOME' \
echo "la variable HOME contiene $HOME" -> conserva el significado 

### ORDEN FILE
Especifica la extencion del archivo, aunque su extensión no esté visible. 
Ejemplo 
```bash
pedro@Polifemo:~$ file fichero_sin_extension
````


  
