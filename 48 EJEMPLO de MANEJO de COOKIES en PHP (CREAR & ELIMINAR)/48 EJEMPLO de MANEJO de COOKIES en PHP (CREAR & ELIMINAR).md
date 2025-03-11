# 48 EJEMPLO de MANEJO de COOKIES en PHP (CREAR & ELIMINAR)
Las cookies son pequenios archivos donde almacenamos datos, estos quedan en el navegador del cliente. No se guardan datos sensibles, se suelen guardar preferencias de idioma, seguimiento de anuncios, etc.

## Formato
Deben crearse en un archivo con formato html, **ANTES de la etiqueta DOCTYPE**

```php
setcookie('Nombre', valor, expiracion, dir, dominio, secure, httponly);
```
`nombre` => nombre de la cookie

`valor` =>  contenido que almacenará la cookie

`expiracion` => fecha en la que 

`dir` => donde estara disponible

`secure` => la cookie solo se crea cdo la conexion sea segura (HTTPS)

`httponly` => la cookie solo se crea en el protocolo HTTP

## HTML
```php
<?php
setcookie('Idioma', 'es', time()+60*60*34*365, '/', 'localhost', false, true);
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
`time()+60*60*34*365` => sec * min * hor * day

`'/'`  => para todos los directorios del servidor

`'localhost'` => dominio donde funcionara

`false` => para conexiones no seguras

`true` => unicamente para protocolo HTTP