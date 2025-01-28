# 29 Como USAR el CICLO FOR en PHP (EJEMPLOS)
Es un ciclo que se utiliza cuando ya tenemos definida la cantidad de repeticiones que deben realizarse

## Sintaxis solo PHP
```php
for (var; Condicion; incre|decre){
    Código a ejecutar
    }
```

## Sintaxis PHP+HTML5
```php
for(var; Condicion; incre|decre):
    Código a ejecutar
endfor;
```

## Ejemplos

### 1. Contador del 1 al 20
```php
#Incremento
<?php
    for($i=1; $i<=20; $i++){
        echo $i."<br>";
    }
```

### 2. Contador del 20 al 1
```php
#Decremento
<?php
    for($i=20; $i>=1; $i--){
        echo $i."<br>";
    }
```

### 3. Diseñe un programa que imprima los números del 1 hasta el 20. (Incremento y decremento)
```php
#Incremento
<?php
    for($i=1; $i<=20; $i++){
        echo $i."<br>";
    }
```
```php
#Decremento
<?php
    for($i=20; $i>=1; $i--){
        echo $i."<br>";
    }
```

### 4. Diseñe un programa que imprima la tabla de multiplicar de un numero dado, desde el factor 1 hasta el 12. (Incremento y decremento).
```php
#Incremento
<?php
    $num=5;
    for($i=1; $i<=12; $i++){
        echo $num*$i.'<br>';
    }
```

```php
<?php
    $num=5;
    for($i=12; $i>=1; $i--){
        echo $num*$i.'<br>';
    }
```
