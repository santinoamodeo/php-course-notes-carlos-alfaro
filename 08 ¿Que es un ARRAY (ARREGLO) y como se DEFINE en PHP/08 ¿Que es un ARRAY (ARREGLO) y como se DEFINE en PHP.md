# 08 ¿Que es un ARRAY (ARREGLO) y como se DEFINE en PHP?


## Escalares
Accedemos a los elementos del array por medio del numero indice, que arranca en 0. 

### Crear un array

```php
// manera vieja
<?php
    $estudiantes=array('Carlos', 'Santino', 'Marcos');

//manera nueva
    <?php
    $estudiantes=[
        'Carlos', 
        'Santino', 
        'Marcos'
    ];
```

### Mostrar en pantalla un elemento
```php
    echo $estudiantes[1];
```

### Modificar el valor de un elemento

```php
    $estudiantes[1] = "Juan Manuel";
```

## Asociativos
Accedemos a los elementos del array por medio de la clave que contiene el valor que nos interesa.

### Crear un array
```php
$tutor=[
    'nombre' => 'claudia',
    'apellido' => 'merendez',
    'edad' => 45
];
```

### Mostrar en pantalla un elemento del array por medio de una clave
```php
    echo $tutor['nombre'];
```

### Modificar el valor de un array por medio de su clave
```php
$tutor['nombre'] = 'Martin';
```


## Multidimensionales
Es un array que en sus valores contiene arrays. Para buscar los elementos se hace por medio del numero indice dentro de cada dimension. Utiliza tantos pares de corchetes como dimensiones.

### Crear array
```php
$tutor_2=[
    'nombre' => 'Vanessa',
    'apellido' => 'Alfarez',
    'edad' => 35,
    'cursos' => ['PHP',
        'Python',
        'React Js'
    ]
    'multi_asoc' => [
        'nombre' => 'Martin',
        'apellido' => 'Perez',
        'edad' => 12,
    ]
];
```

### Mostrar un valor del array multidimensional escalar
```php
## Nombro la clave donde se contiene ese array escalar pongo el indice
    echo $tutor_2['cursos'][1];
```
### Mostrar un valor del array multidimensional asociativo
```php
## Nombro la clave donde se contiene ese array asociativo y pongo su clave
    echo $tutor_2['multi_asoc']['edad'];
```

### Modificar el valor de un array multidimensional 
```php
### Multi escalar
$tutor_2['cursos'][2] = 'GitHub';

### Multi asociativo
$tutor_2['multi_asoc']['edad'] = 13;
```

--- 

### Contar cantidad de elementos de un array unidimensional
```php

    echo count($tutor_2);   
```

### Contar cantidad de elementos de un array multidimensional
```php
    echo count($tutor_2, COUNT_RECURSIVE);
```