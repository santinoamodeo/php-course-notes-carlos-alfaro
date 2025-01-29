# 36 FUNCIONES para CONTAR CARACTERES y PALABRAS de un STRING
## Contar caracteres en string
`strlen()`
```php
<?php
    $texto = 'Hola este es mi texto';
    $longitud = strlen($texto);
    echo $longitud;
```

## Contar cantidad de palabras en string
`str_word_count`
```php
    $palabras = str_word_count($texto);
    echo $palabras;
```