# 09 CONCATENACION e INTERPOLACION de VARIABLES en PHP
## Concatenacion
Se utiliza para unir textos con datos como variables

```php
$nombre = 'Santino';
$apellido = 'Amodeo';

echo 'Mi nombre es: '.$nombre.'. Mi apellido '.$amodeo;
```

## Interpolacion de variables
Debe usarse **SIEMPRE** con doble comilla **" "**. Puede hacerse con o sin las llaves.

```php
$nombre = 'Santino';
$apellido = 'Amodeo';

echo "Mi nombre es {$nombre} y mi apellido $apellido";
```