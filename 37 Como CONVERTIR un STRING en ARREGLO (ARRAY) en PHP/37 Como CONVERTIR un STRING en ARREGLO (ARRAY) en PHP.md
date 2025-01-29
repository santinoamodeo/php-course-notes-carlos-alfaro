#  37 Como CONVERTIR un STRING en ARREGLO (ARRAY) en PHP
Para transformar strings en arrays utilizamos explode()
## Sintaxis
```php
    explode(delimitador, string, limitador)
    # El limitador es opcional
```
### El delimitador es el caracter que marca la separacion
En 21/2/22 el delimitador es /, y queda, 21 2 22    
```php
<?php
    $fecha_1='21/2/2020';
    $fecha_2='25-6-2017';
    $numeros='Uno Dos Tres Cuatro Cinco Seis Siete';

    $array_fecha = explode('/', $fecha_1);
    echo $array_fecha[2];
```

### El limitador es la cantidad de secciones que tendra el array
En cuantos pedazos se parte el string
```php
<?php
    $fecha_1='21/2/2020';
    $fecha_2='25-6-2017';
    $numeros='Uno Dos Tres Cuatro Cinco Seis Siete';

    $array_fecha = explode(' ', $numeros, 3);
    echo $array_fecha[2];

```