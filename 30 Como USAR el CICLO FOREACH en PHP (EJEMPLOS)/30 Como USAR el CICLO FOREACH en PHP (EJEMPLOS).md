# 30 Como USAR el CICLO FOREACH en PHP (EJEMPLOS)
Utilizado unicamente para iterar sobre arrays

## Sintaxis para recorrer solo valores
```php
foreach($array as $valor){
    $valor tendrá en cada iteración
    un valor del array
    }
```
### Ejemplo
```php
$notebook=['Hp', 'Pavilion X360', 'Intel I7 10ma', 'Intel Iris Plus', 'RAM 16GB'];

foreach($notebook as $valor){
    echo $valor.'<br>';
}
```

## Sintaxis para recorrer claves y valores
```php
foreach($array as $clave => $valor){
    $clave tendrá en cada iteración
    una clave del array
    $valor tendrá en cada iteración
    un valor del array
}
```
### Ejemplo
```php
foreach($frutas as $clave => $valor){
    echo $clave.' => '.$valor.'<br>';
}
```

## Ejemplo picante => extraccion de datos de una DB
```php
    $productos = [
        ['codigo' => 'A0001', 'descripcion' => 'Mouse'],
        ['codigo' => 'A0002', 'descripcion' => 'Teclado'],
        ['codigo' => 'A0003', 'descripcion' => 'Monitor'],
        ['codigo' => 'A0004', 'descripcion' => 'Impresor'],
    ];

    foreach($productos as $prod){
        echo $prod['codigo'].' - '.$prod['descripcion'].'<br>';
    }
```
Para utilizar foreach en array multidimensionales, se pone unicamente ($array as $valor), y al llamar $valor, abrimos corchetes y llamamos a la clave deseada

```php
foreach($array as $valor){
    echo $valor['clave'];
}
```