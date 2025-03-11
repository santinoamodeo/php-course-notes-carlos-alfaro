# 51 REDIRECCIONAR paginas usando PHP (FUNCION HEADER) y JavaScript 
## Header
Al redireccionar con header, debo asegurarme de no tener salidas a pantalla antes, sino no funcionara
```php
<?php
    if($_POST['usuario'] == 'Carlos' && $_POST['clave'] == '1234'){
        session_name('LOGIN');
        session_start();

        $_SESSION['Nombre']='Santino';
        $_SESSION['apellido']='Amodeo';
        $_SESSION['pais']='Argentina';

        header('Location: contador.php');
    }else{
        echo 'Credenciales incorrectas, intente nuevamente';
    }
?>
```
`header` => location: el archivo al que deseo ser redireccionado 

## Con JS
```php
<?php
    session_name('LOGIN');
    session_start();

    session_destroy();

    echo "<script> window.location.href='index.php'; </script>";
    // header('Location: index.php'); #Puede hacerse asi tmb
?>
```

## Forma correcta de hacerlo
```php
<?php
    session_name('LOGIN');
    session_start();

    session_destroy();

    if(headers_sent()){ //si hay encabezados o salidas a pantalla
        echo "<script> window.location.href='index.php' <script/>;";
    }else{
        header('Location: index.php');
    }
?>
```
**Chequea** si puede hacerlo **nativo en php con header**, siempre y cuando no hayan **encabezados ni salidas a pantalla**, de lo contrario, utiliza **JS**