# 21 EJEMPLO de OPERADOR TERNARIO en PHP
### 1. Hacer un programa que calcule el total a pagar por la compra de camisas. Si se compran tres camisas o mas se aplica un descuento del 20% sobre el total de la compra y si son menos de tres camisas un descuento del 10%.

```php
<?php
    $cantidad_camisas = 32;
    $precio_camisa = 150;
    $total = $cantidad_camisas * $precio_camisa;

    $total=($cantidad_camisas >= 3) ? $total = $total-($total*0.20) : $total = $total-($total*0.10);
    echo 'El precio total es de $'.$total.'. Y se lleva '.$cantidad_camisas.' camisas';
```