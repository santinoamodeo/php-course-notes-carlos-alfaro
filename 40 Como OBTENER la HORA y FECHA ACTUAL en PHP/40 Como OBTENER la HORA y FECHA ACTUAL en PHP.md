# 40 Como OBTENER la HORA y FECHA ACTUAL INGLES en PHP 

## 1. Definir zona horaria

[Zonas horarias - Manual PHP](https://www.php.net/manual/es/function.date-default-timezone-set.php)

```php
#Funcion base
date_default_timezone_set()
```
* Ingrsar a listado de zonas horarias
* Copiar la correspondiente y pegarla en la funcion, dentro de un string

```php
#Funcion con zona horaria
date_default_timezone_set('America/Argentina/Buenos_Aires')
```
## 2. Accionar funcion date()
[Parametros date() - Manual PHP](https://www.php.net/manual/es/function.date.php)

```php
date('j');
```