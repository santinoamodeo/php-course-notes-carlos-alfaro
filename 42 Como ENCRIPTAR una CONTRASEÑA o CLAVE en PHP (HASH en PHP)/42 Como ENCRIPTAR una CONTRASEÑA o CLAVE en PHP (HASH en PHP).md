# 42 Como ENCRIPTAR una CONTRASEÑA o CLAVE en PHP (HASH en PHP)
[password_hash - Manual PHP](https://www.php.net/manual/es/function.password-hash.php)
## md5
```php
<?php

$clave = 'HolaMundo123';
echo md5($clave); // 5b6b89a334ac2d95be7e053566d81466
```

## sha1
```php
<?php

$clave = 'HolaMundo123';
echo sha1($clave); // 47dd16b35e08b74d688de0724f76f66ce62fe072
```

## Funcion hash() multialgoritmica
```php
<?php

$clave = 'HolaMundo123';
echo echo('md5',$clave); // 5b6b89a334ac2d95be7e053566d81466
```

## Ver todos los algoritmos soportados por la funcion hash()
```php
foreach(hash_algos() as $algoritmos){
    echo $algoritmos.' - '.hash($algoritmos,$clave).'<br>';
}   
```

## Funcion password_hash(), la que debemos usar
### Con algoritmo PASSWORD_DEFAULT
Este algoritmo va cambiando a medida que se actualiza PHP
```php
echo password_hash($clave, PASSWORD_DEFAULT);
```
### Con algoritmo PASSWORD_BCRYPT
cost es cuantas veces se hashea la password
```php
echo password_hash($clave, PASSWORD_BCRYPT, ['cost'=>14]);
```
### ¿Cómo elegir un buen cost?
- **Bajo (8-10)**: Rápido, pero menos seguro. Útil si necesitas procesar muchas contraseñas rápidamente.
- **Medio (11-13)**: Balance entre seguridad y rendimiento.
- **Alto (14+)**: Más seguro, pero más lento. Ideal para sistemas críticos con alta seguridad.

## Funcion password_verify()
Se utiliza para chequear que la password original y la password hasheada son la misma
```php
if(password_verify($clave, $password_procesada);){
    echo "Las claves coinciden";
}else{
    echo "Las claves NO coinciden";
}
```