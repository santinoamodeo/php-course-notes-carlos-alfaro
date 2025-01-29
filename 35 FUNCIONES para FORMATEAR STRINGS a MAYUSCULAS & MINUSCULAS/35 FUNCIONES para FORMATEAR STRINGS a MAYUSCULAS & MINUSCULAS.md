# 35 FUNCIONES para FORMATEAR STRINGS a MAYUSCULAS & MINUSCULAS

## String a minusculas
`strtolower()`
```php
<?php
    $texto = 'Hola este es mi texto';
    echo strtolower($texto);
```
## String a mayusculas
`strtoupper()`
```php
<?php
    $texto = 'Hola este es mi texto';
    echo strtoupper($texto);
```
## Primera letra del string mayuscula
`ucfirst()`
```php
<?php
    $texto = 'Hola este es mi texto';
    echo ucfirst($texto);
```

## Primera letra de cada palabra del string mayuscula
`ucwords()`
```php
<?php
    $texto = 'Hola este es mi texto';
    echo ucwords($texto);
```