# 17 EJEMPLOS de ESTRUCTURA CONDICIONAL SIMPLE (IF)

### 1. Realizar un programa en donde se pide la edad del usuario; si es mayor de edad debe aparecer un mensaje indicándolo.

Se asume que la edad del usuario es la que se coloca en la variable. NO es dinamico.
```php
<?php
    $edad_usuario = 20;

    if($edad_usuario >= 18){
        echo 'Es mayor de edad';
    }
```

### 2. En un almacén se hace un 20% de descuento a los clientes cuya compra supere los $100 ¿Cuál será la cantidad que pagara una persona por su compra?

```php
# Forma correcta
    if($monto_cliente_1 > 100){
        $total = $monto_cliente_1-($monto_cliente_1 * 0.20);
        echo "El monto que debera pagar el cliente 1 es de {$total}";
    }
```

```php
    $descuento_cuenta = 0.20;
    $descuento_deuna = 0.80;
    $monto_cliente_1 = 150;


    if($monto_cliente_1 > 100){
        $multiplicacion = $monto_cliente_1 * $descuento_cuenta;
        $total_a_pagar = $monto_cliente_1 - $multiplicacion;
        echo $total_a_pagar;
    }
```

```php
    if($monto_cliente_1 > 100){
        echo $monto_cliente_1 * $descuento_deuna;
    }
```
