# 33 Como CREAR y USAR FUNCIONES PROPIAS en PHP (con PARAMETROS)
Conjunto de instrucciones al que se le pueden pasar parametros. Sus nombres deben comenzar con **una letra o un guion bajo.**

## Sintaxis
```php
function nombre_de_la_funcion($parametros){
    Cosifo de la funcion
}

nombre_de_la_funcion();
```

### Devolver valores con return
```php
<?php
    function saludo(){
        return 'Hola a todos';
    }

    $sakudo = saludo();
    echo $sakudo;
```

### Funciones con parametros
```php
<?php
    function saludo($nombre){
        echo "Hola $nombre";
    }   

    saludo('Juan');
```

```php
<?php
    function saludo($nombre){
        echo "Hola $nombre";
    }   

    $usuario = 'Victoria';
    saludo($usuario);
```

### Funciones con calculos
```php
<?php
    function promedio_alumno($nota_1, $nota_2, $nota_3){
        $promedio = ($nota_1 + $nota_2 + $nota_3)/3;
        return $promedio;
    };

    $promedio = promedio_alumno(7,8,9);
    echo 'El promedio es '.$promedio;
```