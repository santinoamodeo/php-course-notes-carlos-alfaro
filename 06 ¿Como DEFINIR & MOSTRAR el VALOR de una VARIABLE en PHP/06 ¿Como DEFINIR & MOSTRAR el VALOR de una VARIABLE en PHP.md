# 06 ¿Como DEFINIR & MOSTRAR el VALOR de una VARIABLE en PHP?

* Se definen con signo dolar
* Empiezan con una **letra** mayus/minus o un **guion bajo**. **NUNCA** con un numero
* Las escribiremos en **Lower Camel Case** (lowerCamelCase)

```php
<?php 
    $nombre = "Santino";
    echo $nombre;
```

### Listado de variables globales 
NO podemos utilizar sus referencias para nuestras variables
* $_GLOBALS
* $_SERVER
* $_GET
* $_POST
* $_FILES
* $_REQUEST
* $_SESSION
* $_ENV
* $_COOKIE