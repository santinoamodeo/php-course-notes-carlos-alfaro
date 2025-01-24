# 20 ¿Que es y como FUNCIONA el OPERADOR TERNARIO en PHP?   
Es un **if** en una sola linea. Tiene 3 partes, el operador y los resultados.

## Importante
No se puede utilizar **echo** dentro de los operadores ternarios
```
#Sintaxis
<operator> ? <true value> : <false value>
```
```php
#Estructura a utilizar
(9>5) ? 10*7 : 10*8;

# Guardando en variables
(9>5) ? $total = 10*7 : $total = 10*8;
```

```php
#Ejemplo
<?php
    $edad = 15;
    ($edad >= 18) ? $msj = 'Es mayor de edad' : $msj = 'Es menor de edad';
    echo $msj;
```