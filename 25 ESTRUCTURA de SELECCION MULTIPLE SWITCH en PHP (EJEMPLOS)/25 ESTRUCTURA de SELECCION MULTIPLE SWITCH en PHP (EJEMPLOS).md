# 25 ESTRUCTURA de SELECCION MULTIPLE SWITCH en PHP (EJEMPLOS)

Es utilizado para comparar sdistintos valores sobre una misma variable. Practicamente reemplaza el uso de muchos ifelse.

### Es de igualdad debil, por lo que no corrobora tipos de datos.

## Sintaxis
```php
switch ($variable) {
    case valor1:
        // Código que se ejecuta si $variable es igual a valor1
        break;
    case valor2:
        // Código que se ejecuta si $variable es igual a valor2
        break;
    case valor3:
        // Código que se ejecuta si $variable es igual a valor3
        break;
    default:
        // Código que se ejecuta si ningún caso coincide
        break;
}
```
### Ejemplo 1
```php
<?php
    $fruta ='Apple';

    switch($fruta){
        case 'Apple':
            echo 'Es una manzana';
            break;
        case 'Banana':
            echo 'Es una banana';
            break;
        case 'Frutilla':
            echo 'Es una frutilla';
            break;
        default:
            echo 'No es ni una manzana, ni una banana, ni una frutilla';
            break;
    }
```

### Ejemplo 2
### 1. Se desea diseñar un programa que escriba los nombres de los días de la semana en función del valor de una variable DIA.Los días de la semana son 7; por consiguiente, el rango de valores de DIA será 1..7, y caso de que DIA tome un valor fuera de este rango se deberá producir un mensaje de error advirtiendo la situación anómala.

```php
$dia = 5;

    switch($dia){
        case 1:
            echo 'Lunes';
            break;
        case 2:
            echo 'Martes';
            break;
        case 3:
            echo 'Miercoles';
            break;
        case 4:
            echo 'Jueves';
            break;
        case 5:
            echo 'Viernes';
            break;
        case 6:
            echo 'Sabado';
            break;
        case 7:
            echo 'Domingo';
            break;
        default:
            echo 'Dia fuera de rango. Ingresar valores del 1 al 7';
            break;
    }
```