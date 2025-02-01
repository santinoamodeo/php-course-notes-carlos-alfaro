# 39 FORMATEAR NUMERO o CANTIDADES de DINERO en PHP

## Sintaxis
`number_format(cantidad, decimales, sep_decimales, sep_millar);`
```php
<?php
    $cantidad_1 = 1256.12;
    $cantidad_2 = 1931.81;

    echo number_format($cantidad_1); # 12,733
    echo number_format($cantidad_1,2); # 12,732.77
    echo number_format($cantidad_1,2, '.', ',').'<br>'; # 12,732.77
    echo number_format($cantidad_1,2, ',', '.').'<br>'; # 12.732,77