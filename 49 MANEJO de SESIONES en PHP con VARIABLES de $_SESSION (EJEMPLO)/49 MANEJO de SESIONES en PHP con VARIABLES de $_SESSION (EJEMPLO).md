# 49 MANEJO de SESIONES en PHP con VARIABLES de $_SESSION (EJEMPLO)
Al igual que cookie almacena datos, pero los guarda en el servidor
## Archivo .php
```html
<?
    session_name('CONT');
    session_id('Iddcont');
    session_start();
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <a href="index.php">Ir al inicio</a>
    <a href="cerrar.php">Cerrar sesion</a>
</body>
</html>
```

Justo arriba de una estructura simple HTML, tenemos:

`session.start()`  => Iniciar sesion

`session.name()`  => Cambiar nombre de sesion

`session.id()`  => Cambiar id de sesion

Las dos utilmas deben hacerse antes de iniciar la sesion

### **La sesion debe iniciarse en todos los archivos donde querramos tenerla**

## Variables de sesion
Podemos utilizarlas en todos los archivos que abarque la sesion iniciada.
```php
   if(isset($_SESSION['contador'])){
        $_SESSION['contador']++;
    }else{
        $_SESSION['contador']=1;
    }
```
Si esta definida la variable de sesion 'contador', cada vez que se recargue la sesion, le sumo 1, sino, la creo y le asigno el valor 1.
### Archivo contador.php 
```php
<?php
    session_name('CONT');
    session_start();

    if(isset($_SESSION['contador'])){
        $_SESSION['contador']++;
    }else{
        $_SESSION['contador']=1;
    }
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <?php echo 'Has recargado esta pagina '.$_SESSION['contador'].' veces';?>
    <a href="index.php">Ir al inicio</a>
    <a href="cerrar.php">Cerrar sesion</a>
</body>
</html>
```

En este archivo va la logica del contador y se muestra un echo con la cantidad de veces que se recargo la sesion

### Archivo index.php
```php
<?php
    session_name('CONT');
    session_start();
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <?php echo 'Has recargado esta pagina '.$_SESSION['contador'].' veces'?>
    <form action="login.php" method="POST">
        <label>Usuario</label>
        <input type="text" name="usuario">
        <br>
        <label>Clave</label>
        <input type="password">
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
```
En este archivo simplemente se muestra un echo con la cantidad de veces que se recargo la sesion

## LOGIN COMPLETO
### index.php
```html
<?php
    session_name('LOGIN');
    session_start();
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form action="login.php" method="POST">
        <label>Usuario</label>
        <input type="text" name="usuario">
        <br>
        <label>Clave</label>
        <input type="password" name='clave'>
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
```
### contador.php
```php
<?php
    session_name('LOGIN');
    session_start();

    if(isset($_SESSION['contador'])){
        $_SESSION['contador']++;
    }else{
        $_SESSION['contador']=1;
    }
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <?php echo 'Hola '.$_SESSION['Nombre'].', bienvenido!';?>
    <a href="cerrar.php">Cerrar sesion</a>
</body>
</html>
```
### login.php
```php
<?php
    if($_POST['usuario'] == 'Carlos' && $_POST['clave'] == '1234'){
        session_name('LOGIN');
        session_start();

        $_SESSION['Nombre']='Santino';
        $_SESSION['apellido']='Amodeo';
        $_SESSION['pais']='Argentina';

        echo 'Bienvenido, sesion iniciada con exito';
    }else{
        echo 'Credenciales incorrectas, intente nuevamente';
    }
?>
```
### cerrar.php
```php
<?php
    session_name('LOGIN');
    session_start();

    session_destroy();
?>
```