# 46 SUBIR o ENVIAR ARCHIVOS a SERVIDOR PHP con FORMULARIOS
Como paneo general para entender el funcionamiento hago dos archivos, uno visual y uno con procesamiento

## Informacion del archivo de subida

#### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carga de archivo</title>
</head>
<body>
    <h3>Subir archivo</h3>
    <form action="carga.php" method="POST" enctype="multipart/form-data">
        <input type="file" name="fichero">
        <br><br>
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
```

#### FORM
- `action` => Ruta donde ira mi informacion
- `method` => **POST** porque estoy enviando
- `enctype` => **multipart/form-data** se utiliza para subir archivos

#### PHP
```php
<?php
echo $_FILES['fichero']['name']."<br>";
echo $_FILES['fichero']['tmp_name']."<br>";
echo $_FILES['fichero']['type']."<br>";
echo $_FILES['fichero']['error']."<br>";
echo $_FILES['fichero']['size']."<br>";
```
Utilizo la variable global `$_FILES` para bajar los archivos.
- `name` = nombre del archivo
- `tmp_name` = nombre temporal del archivo hasta que se guarde o llegue
- `type`= formato 
- `error` = en caso de que hubiere lo identifica
- `size` = tamanio en bytes

## Cargar archivos al servidor
Estaran cargados dentro de una carpeta que se encuentra a la misma altura que los dos arhcivos que veremos a continuacion

### Archivo .html 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carga de archivo</title>
</head>
<body>
    <h3>Subir archivo</h3>
    <form action="carga.php" method="POST" enctype="multipart/form-data">
        <input type="file" name="fichero">
        <br><br>
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
```

### Archivo .php (procesamiento)

```php
<?php
if(!file_exists('archivos')){     #Si no existe la carpeta archivos
    if(!mkdir('archivos', 0777)){#Y si no se puede crear, con los permisos 0777(todos)
        echo 'Error inesperado al crear';
        exit();
    }   
}

chmod('archivos', 0777); #Si la carpeta existia, le doy todos los permisos

if(move_uploaded_file($_FILES['fichero']['tmp_name'],'archivos/'.$_FILES['fichero']['name'])){ #si pude mover el archivo de temporal a la carpeta definitiva
    echo 'Archivo subido con exito';
}else{
    echo 'Error al cargar el archivo';
} 

```
`move_uploaded_file(temp, definitiva)`

## Limitar formato de archivos
Puede hacerse desde HTML y desde PHP, pero debe hacerse desde PHP, asi no puede manipularse por el editor del navegador.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carga de archivo</title>
</head>
<body>
    <h3>Subir archivo</h3>
    <p>Solo se admiten archivos con formato .pdf y .png</p>
    <form action="carga.php" method="POST" enctype="multipart/form-data">
        <input type="file" name="fichero" accept=".pdf, .png">
        <br><br>
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
```
`accept` = poner el formato de archivo permitidos, debe coincidir por los autorizados en el codigo logico .php

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carga de archivo</title>
</head>
<body>
    <h3>Subir archivo</h3>
    <p>Solo se admiten archivos con formato .pdf y .png de hasta 5Mb</p>
    <form action="carga.php" method="POST" enctype="multipart/form-data">
        <input type="file" name="fichero" accept=".pdf, .png">
        <br><br>
        <button type="submit">Enviar</button>
    </form>
</body>
</html>
```

```php
<?php

if(mime_content_type($_FILES['fichero']['tmp_name']) != 'application/pdf' && mime_content_type($_FILES['fichero']['tmp_name']) != 'image/png'){ #Si nombre y ruta temporal (tmp_name) es distinto a al MIME application/pdf y si nombre y ruta temporal (tmp_name) es distinto a al MIME image/png, mensaje y salgo
    echo "Formato no soportado";    
    exit();
}

if(!file_exists('archivos')){     #Si no existe la carpeta archivos
    if(!mkdir('archivos', 0777)){#Y si no se puede crear, con los permisos 0777(todos)
        echo 'Error inesperado al crear';
        exit();
    }   
}

chmod('archivos', 0777); #Si la carpeta existia, le doy todos los permisos

if(move_uploaded_file($_FILES['fichero']['tmp_name'],'archivos/'.$_FILES['fichero']['name'])){ #Si se pudo mover el archivo de su ruta temporal a su ruta definitiva, dentro de la carpeta archivs/, msj en pantalla
    echo 'Archivo subido con exito';
}else{
    echo 'Error al cargar el archivo';
} 

echo "<br>";    
echo $_FILES['fichero']['tmp_name'];
```

## Limitar peso de archivos

```php
<?php

if(mime_content_type($_FILES['fichero']['tmp_name']) != 'application/pdf' && mime_content_type($_FILES['fichero']['tmp_name']) != 'image/png'){
    echo "Formato no soportado";    
    exit();
}

if(($_FILES['fichero']['size']/1024) > 5){ #Si el tamanio del archivo, dividido por 1024, para que sea en Mb, es mayor a 5, no puede subirlo
    echo 'El archivo supera los 5Mb, por favor suba un archivo mas chico';
    exit();
}

if(!file_exists('archivos')){     #Si no existe la carpeta archivos
    if(!mkdir('archivos', 0777)){#Y si no se puede crear, con los permisos 0777(todos)
        echo 'Error inesperado al crear';
        exit();
    }   
}

chmod('archivos', 0777); #Si la carpeta existia, le doy todos los permisos

if(move_uploaded_file($_FILES['fichero']['tmp_name'],'archivos/'.$_FILES['fichero']['name'])){
    echo 'Archivo subido con exito';
}else{
    echo 'Error al cargar el archivo';
} 

echo "<br>";    
echo $_FILES['fichero']['tmp_name'];
```
