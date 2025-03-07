# 45 SABER si una VARIABLE esta VACIA o DEFINIDA con isset() | empty()

## is_null()
Chequea si la variable es nula o no

```php
<?php
    $numero=NULL;

    if(is_null($numero)){
        echo 'Es nula';
    }else{
        echo 'No es nula';
    }
```

## unset()
Hace nula a una variable

```php
    $numero=9;
    unset($numero);
    
    if(is_null($numero)){
        echo 'Es nula';
    }else{
        echo 'No es nula';
    }
```

## empty()
Para corroborar si una variable esta vacia

Los siguientes valores son considerados como vacíos:

- "" (una cadena vacía)
- 0 (0 como un integer)
- 0.0 (0 como un float)
- "0" (0 como un string)
- null
- false
- array() (un array vacío)

```php
<?php
    $numero=9;
    
    if(empty($numero)){
        echo 'Esta vacia';
    }else{
        echo 'No esta vacia';
    }
```

## isset()
Chequea que la variable este definida y no sea NULL
```php
# Definida
<?php
    $numero=9;
    
    if(isset($numero)){
        echo 'Esta definida';
    }else{
        echo 'No esta definida';
    }
```

```php
# Indefinida
<?php
    $numero=9;
    
    unset($numero);

    if(isset($numero)){
        echo 'Esta definida';
    }else{
        echo 'No esta definida';
    }
```


