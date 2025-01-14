# 12 ASIGNACION por REFERENCIA en PHP
Se basa que en mas de una variable apunta a un mismo dato. Pero al hacerla con asignacion por referencia, si el valor de la variable original cambia, la nueva variable tambien cambiara.

```php
<?php
    $texto = 'Hola peridida';
    $texto_sin_asignacion = $texto;
    $texto_con_asignacion = 'piripipi';

    echo $texto; //Hola peridida
    echo $texto_sin_asignacion; //Hola peridida
    echo $texto_con_asignacion; //piripipi
```