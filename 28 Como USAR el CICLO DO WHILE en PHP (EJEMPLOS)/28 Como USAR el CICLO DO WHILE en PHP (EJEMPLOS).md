# 28 Como USAR el CICLO DO WHILE en PHP (EJEMPLOS)
### Es igual que el ciclo while, solo que se verifica la condicion al final de la iteracion, y no al principio como el while

## Sintaxis
```php
#Unica
do{
    codigo a ejecutar
}while(condicion);
```

## Ejemplos

### 1. Diseñe un programa que imprima los números del 1 hasta el 20. (Incremento y decremento).

```php
<?php
    #Del 1 al 20
    $c = 1;
    
    do{
        echo $c.'<br>';
        $c++;
    }while($c<=20);
```

```php
<?php
$c = 20;

do{
    echo $c."<br>";
    $c--;
}while($c >= 1);
```

### 2.Diseñe un programa que imprima la tabla de multiplicar de un numero dado, desde el factor 1 hasta el 12. (Incremento y decremento).


```php
# De 1 a 12
$c=1;
$num=5;

do{
    echo $c * $num."<br>";
    $c++;
}while($c<=12);
```

```php
# De 12 a 1
$c=12;
$num=5;

do{
    echo $c * $num."<br>";
    $c--;
}while($c>=1);
```