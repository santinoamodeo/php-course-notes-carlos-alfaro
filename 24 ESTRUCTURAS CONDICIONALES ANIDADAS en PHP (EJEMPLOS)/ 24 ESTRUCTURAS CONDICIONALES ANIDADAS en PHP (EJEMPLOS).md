#  24 ESTRUCTURAS CONDICIONALES ANIDADAS en PHP (EJEMPLOS)

### 1. Pida a usuario la edad y el genero, para que la computadora le indique si ya puede jubilarse. Tome en cuenta que un Hombre se puede jubilar cuando tenga 60 años o más, en cambio, una mujer mayor se jubilara si tiene más de 54 años.

```php
<?php
    $edad = 61;
    $genero = 'F';

    if($genero == 'M'){
        if($edad >= 60){
            echo 'Puede jubilarse jefe';
        }else{
            echo 'No puede jubilarse jefe';
        }
    }elseif($genero == 'F'){
        if($edad >= 54){
            echo 'Puede jubilarse jefa';
        }else{
            echo 'No puede jubilarse jefa';
        }
    }else{
        echo 'Ingrese un valor valido';
    }
```
Parece un quilombo, pero basicamente es ordenar. Comienza por el genero, como hay 2 generos, chequea con 2 if (1 if y 1 elseif) A LA MISMA ALTURA. Una vez que entro al if, vuelve a corroborar pero ahora con la edad, si se cumple dicha condicion, muestra un mensaje, sino, muestra otro.
