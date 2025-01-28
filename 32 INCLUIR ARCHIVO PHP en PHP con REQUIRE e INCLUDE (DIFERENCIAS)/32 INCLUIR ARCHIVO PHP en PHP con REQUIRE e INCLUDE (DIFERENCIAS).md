# 32 INCLUIR ARCHIVO PHP en PHP con REQUIRE e INCLUDE (DIFERENCIAS)
Incluyen codigo de un archivo .php dentro de otro archivo .php

## include
Incluye codigo de otro archivo a nuestro script, pero si este el codigo no existe o tiene errores, muestra por pantalla **warning** y el script **continua ejecutandose**

### Sintaxis
```php
include("ruta_archivo.php");
include"ruta_archivo.php";
```
```php
include_once("ruta_archivo.php");
include_once"ruta_archivo.php";
#include_once hace que solo se pueda agregar una vez
```

### Ejemplos
```php
<?php 
    include 'for.php';
```
```php
<?php 
    include_once 'for.php';
```

## require
Misma operacion que include, pero si el codigo no existe o tiene errores, muestra por pantalla **fatal error** y el script **no se ejecuta**

### Sintaxis
```php
require("ruta_archivo.php");
require"ruta_archivo.php";
```
```php
require_once("ruta_archivo.php");
require_once"ruta_archivo.php";
#require_once hace que solo se pueda requerir una vez
```

### Ejemplos
```php
<?php 
    require 'for.php';
```
```php
<?php 
    require_once 'for.php';
```

## Integracion con HTML5
Al igual que react, en un archivo raiz index, incluyo o requiero a los archivos necesarios, meto al nav en un archivo y lo llamo desde todas las paginas, lo mismo footer, etc.

```html
<!--index.php-->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <?php include_once("inc/nav.php");?>
    <main>
        <h1>Pagina principal</h1>
    </main>
    <?php include_once("inc/footer.php"); ?>
</body>
</html>
```

```html
<!--index2.php-->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <?php include_once("inc/nav.php");?>
    <main>
        <h1>Pagina secundaria</h1>
    </main>
    <?php include_once("inc/footer.php"); ?>    
</body>
</html>
```
```html
<!--nav.php-->

<header>
    <nav>
        <ul>
            <li><a href="index.php">Inicio</a></li>
            <li><a href="index2.php">Segundo</a></li>
        </ul>
    </nav>
</header>
```

```html
<!--footer.php-->
<footer>
    <h4>Pie de pagina</h4>
</footer>
```