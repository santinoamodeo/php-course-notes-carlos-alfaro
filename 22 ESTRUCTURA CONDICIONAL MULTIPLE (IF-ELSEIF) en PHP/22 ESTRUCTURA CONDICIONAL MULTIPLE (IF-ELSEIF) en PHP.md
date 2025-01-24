# 22 ESTRUCTURA CONDICIONAL MULTIPLE (IF-ELSEIF) en PHP
### Estructura solo PHP
```php
if($a>$b){
    echo 'A es mayor que B';
}elseif($a==$b){
    echo 'A es igual que B';
}else{
    echo 'A es menor que B';
}
```
Utilizando solo PHP, puedo expresasrlo como **else if**, pero se suele expresar como **elseif**

### Estructura PHP + HTML5
```php
if($a>$b):
    echo 'A es mayor que B';
elseif($a==$b):
    echo 'A es igual que B';
else:
    echo 'A es menor que B';
endif;
```
Utilizando PHP + HTML5 es obligatorio expresarlo como **elseif**.