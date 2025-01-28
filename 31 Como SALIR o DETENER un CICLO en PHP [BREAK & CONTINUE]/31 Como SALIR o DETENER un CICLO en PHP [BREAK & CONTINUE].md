# 31 Como SALIR o DETENER un CICLO en PHP [BREAK & CONTINUE]
- ### Break = Detener iteracion
- ### Continue = Saltear iteracion

## Break
### Break con While
```php
<?php
    $c=1;
    while($c<=20){
        echo $c.'<br>';
        if($c==10){
            break;
        }
        $c++;
    }
```
### Break con Foreach
```php
    $notebook=['Hp', 'Pavilion X360', 'Intel I7 10ma', 'Intel Iris Plus'];

    foreach($notebook as $datos){
        echo $datos.'<br>';
        if($datos == 'Intel I7 10ma'){
            break;
        }
    };
```

## Continue

### Continue con Foreach
```php
    $notebook=['Hp', 'Pavilion X360', 'Intel I7 10ma', 'Intel Iris Plus', 'SIsi'];

    foreach($notebook as $datos){
        if($datos == 'Intel I7 10ma'){
            continue;
        }
        echo $datos.'<br>';
    };
```

### Continue con For
```php    
    for($i=1; $i<=10; $i++){
        if($i==5){
            continue;
        }
        echo $i."<br>";
    }
```