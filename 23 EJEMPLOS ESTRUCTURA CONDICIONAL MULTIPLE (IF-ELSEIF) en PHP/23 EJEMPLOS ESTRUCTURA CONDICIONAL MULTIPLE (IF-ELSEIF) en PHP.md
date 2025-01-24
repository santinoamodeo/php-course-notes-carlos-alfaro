# 23 EJEMPLOS ESTRUCTURA CONDICIONAL MULTIPLE (IF-ELSEIF) en PHP
### 1. Se desea diseñar un programa que escriba los nombres de los días de la semana en función del valorde una variable DIA.

```php
<?php
    $dia = 7;
    
    if($dia == 1){
        echo 'Lunes';
    }elseif($dia == 2){
        echo 'Martes';
    }elseif($dia == 3){
        echo 'Miercoles';
    }elseif($dia == 4){
        echo 'Jueves';
    }elseif($dia == 5){
        echo 'Viernes';
    }elseif($dia == 6){
        echo 'Sabado';
    }elseif($dia == 7){
        echo 'Viernes';
    }else{
        echo 'El numero ingresado no es valido :(';
    }
```

### 2. En una fábrica de computadoras se planea ofrecer a los clientes un descuento que dependerá del número de computadoras que compre. Si las computadoras son menos de cinco se les dará un 10% de descuento sobre el total de la compra; si el número de computadoras es mayor o igual a cinco pero menos de diez se le otorga un 20% de descuento; y si son 10 o más se les da un 40% de descuento. El precio de cada computadora es de $700.EJERCICIOS (IF –ELSEIF)

```php
    $precio_computadora = 700;
    $cantidad_computadoras = 20;

    $total_a_pagar = $precio_computadora * $cantidad_computadoras;

    if($cantidad_computadoras < 5){
        $total_a_pagar = $total_a_pagar-($total_a_pagar * 0.10);
        echo 'Lleva '.$cantidad_computadoras.' computadoras. Su total es de '.$total_a_pagar.'.';
    }elseif($cantidad_computadoras >= 5 && $cantidad_computadoras < 10){
        $total_a_pagar = $total_a_pagar-($total_a_pagar*0.20);
        echo 'Lleva '.$cantidad_computadoras.' computadoras. Su total es de '.$total_a_pagar.'.';
    }elseif($cantidad_computadoras >=10){
        $total_a_pagar = $total_a_pagar-($total_a_pagar*0.40);
        echo 'Lleva '.$cantidad_computadoras.' computadoras. Su total es de '.$total_a_pagar.'.';
    }
```