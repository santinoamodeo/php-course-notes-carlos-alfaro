# 52 EXPRESIONES REGULARES: VALIDAR FORMULARIOS con PHP [preg_match]

Se utilizan para validar formularios desde el frontend y desde el backend

## Frontend
```html
    <input type="text" name="usuario" pattern="[a-zA-Z]{3,10}"
      maxlength="10">
```
`pattern` => defino las minusculas y mayusculas aceptadas y luego la cantidad de caracteres aceptados.
 
`maxlength` => Deja de escribir a los 10 caracteres
## Backend
```php
<?php
   
   if(!preg_match("/^[a-zA-Z]{3,10}$/",$_POST['usuario'])){
        echo 'El usuario no coincide con el formato solicitado';
        exit();
   }
    
   if(!preg_match("/^[a-zA-Z0-9$-+]{3,30}$/",$_POST['clave'])){
        echo 'La clave no coincide con el formato solicitado';
        echo $_POST['clave'];
        exit();
   }

   if($_POST['usuario'] == 'Carlos' && $_POST['clave'] == '123456789'){
        session_name('LOGIN');
        session_start();

        $_SESSION['Nombre']='Santino';
        $_SESSION['apellido']='Amodeo';
        $_SESSION['pais']='Argentina';

        if(headers_sent()){ //si hay encabezados o salidas a pantalla
            echo "<script> window.location.href='contador.php' <script/>;";
        }else{
            header('Location: contador.php');
        }

    }else{
        echo 'Credenciales incorrectas, intente nuevamente';

    }
?>
```
`preg_match` => caracteres y rangos numericos aceptados y de donde debe controlar esos datos
