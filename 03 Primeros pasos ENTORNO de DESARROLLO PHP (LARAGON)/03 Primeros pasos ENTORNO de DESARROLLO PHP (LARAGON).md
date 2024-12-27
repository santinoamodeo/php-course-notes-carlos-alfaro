# 03 Primeros pasos ENTORNO de DESARROLLO PHP (LARAGON)
## IMPORTANTE
* Cuando buscamos localhost, accedemos a: 'c:/laragon/www/index.php'. Podemos borrarlo para que solo aparezca 'Index Of'
* Lo que diga index, se ejecutara primero, por regla general

### Empezar un proyecto en PHP
1. Dentro de la carpeta www, creamos una carpeta con el nombre del proyecto
2. Creamos un archivo .php

### Hacer que VSCode detecte los errores
* En VSCode, en configuraciones, buscamos `php.validate.executablePath`
* Dentro del JSON reemplazamos la ruta de la version por la que estamos usando, poniendo la ubicacion del archivo

## Sintaxis en PHP
### Etiqueta de apertura y cierre
```
<?php 

?>
```


### Salidas a pantalla
```
<?php
    echo "Hola mundo, esto es una salida a pantalla";
```
* Si nos encontramos escribiendo **UNICAMENTE** codigo php, no es necesario que cerremos la etiqueta con **?>**
* Es totalmente obligatorio cerrar con **;** las lineas de codigo   

### Mostrar texto desde PHP en un HTML
En un archivo index.php
```html & php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>Hola mundo, un h1 desde HTML5</h1>
    <?php
        echo "Hola mundo desde PHP";
    ?>
</body>
</html>
```