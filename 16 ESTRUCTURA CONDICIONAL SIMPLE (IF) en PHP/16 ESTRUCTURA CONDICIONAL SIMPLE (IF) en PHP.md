# 16 ESTRUCTURA CONDICIONAL SIMPLE (IF) en PHP 

## Estructura solo PHP
```php
<?php
    if(9!=1){
        echo 'Juan Martn Manuek';
    }
```

## Estructura PHP + HTML5
```php
#opcion 1
<?php
    if(9!=1):
        echo 'Martinm man juenal';
    endif;
?>
```
```php
#opcion 2
    <?php if(1!=11){?>
    <h1>Esto es una condicion verdadera<h1>
    <?php }?>
```
## Importante
Al utilizar PHP dentro de un codigo HTML, si queremos interactuar con los elementos debemos poner POR LINEA la etiqueta de apertura y cierre como en el ejemplo de opcion 2