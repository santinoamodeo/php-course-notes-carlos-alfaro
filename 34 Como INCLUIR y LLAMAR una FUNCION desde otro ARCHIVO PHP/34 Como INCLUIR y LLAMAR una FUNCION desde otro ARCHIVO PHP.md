# 34 Como INCLUIR y LLAMAR una FUNCION desde otro ARCHIVO PHP
Es practicamente el import que usabamos en React, con include o require traigo el archivo deseado.

```php
# incluir_funciones.php
<?php
include("funciones/funciones.php");

echo 'El promedio es: '.promedio_alumno(5,10,4);
```

```php
# funciones.php
<?php
function promedio_alumno($nota_1, $nota_2, $nota_3){
    $promedio = ($nota_1 + $nota_2 + $nota_3)/3;
    return $promedio;
};
```

### Al hacer esto, desde el archivo incluir_funciones.php, puedo utilizar una funcion que estaba definida e inicializada en el archivo funciones.php, que se halla en otra carpeta

