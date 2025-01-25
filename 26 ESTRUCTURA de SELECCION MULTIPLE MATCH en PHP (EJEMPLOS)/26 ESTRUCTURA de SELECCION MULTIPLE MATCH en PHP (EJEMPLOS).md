# 26 ESTRUCTURA de SELECCION MULTIPLE MATCH en PHP (EJEMPLOS)
Es como switch, pero no necesita break, compara especificamente **(===)** y devuelve un valor. Se lo debe igualar a una variable. Se lo cierra con ;. Es tipo arrowfunction de JS.

## Sintaxis
```php
$resultado = match ($variable) {
    $valor1 => resultado1,
    $valor2 => resultado2,
    $valor3 => resultado3,
    default => resultado_por_defecto
};
```
### Ejemplo 
```php
<?php
    $a=7;

    $v=10;
    $k=11;
    $x=7;

    $resultado = match($a){
        $v => 'Valor igual a v',
        $k => 'Valor igual a k',
        $x => 'Valor igual a x',
        default => 'No coincide con ninguna variable'
    };  

    echo $resultado;
```
Basicamente evalua si las variables **$v, $k, $x** son **ESTRICTAMENTE** iguales a la variable **$a**. 