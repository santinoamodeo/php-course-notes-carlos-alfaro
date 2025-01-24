# 19 EJEMPLOS de ESTRUCTURA CONDICIONAL DOBLE (IF-ELSE)

### 1. Calcular el total que una persona debe pagar en una llantera, el precio de cada llanta es de $800 si se compran menos de 5 llantas y de $700 si se compran 5 o mas.

```php
<?php
    $cantidad_llantas = 9;
    if($cantidad_llantas < 5){
        $total = $cantidad_llantas * 800;
        }else{
        $total = $cantidad_llantas * 700;
    }

    echo $total;
```

### 2. Determinar si un alumno aprueba o reprueba un curso, sabiendo que aprobara si su promedio de tres calificaciones es mayor o igual a 7.0; reprueba en caso contrarioEJERCICIOS (IF -ELSE)

```php
    $nota1 = 10;
    $nota2 = 1;
    $nota3 = 8;
    $promedio = ($nota1 + $nota2 + $nota3) / 3;

    echo 'El promedio es de '.$promedio;
    
    if($promedio >= 7 || $promedio >= 7.0){
        echo 'El alumno APRUEBA';
    }else{
        echo 'El alumno DESAORUEBA';
    }
    ?>
```