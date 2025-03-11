# 47 SUBIR o ENVIAR ARCHIVOS con PHP y AJAX (API FETCH)
Se utiliza JS, despues de tanto!!!
Partimos del mismo ejemplo de la clase 46, pero dinamizamos con JS.

## HTML
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
    <form action="carga.php" method="POST" enctype="multipart/form-data" class="FormularioAjax">
        <input type="file" name="fichero" accept=".pdf, .png">
        <br><br>
        <button type="submit">Enviar</button>
    </form>
    <script src="ajax.js"></script>
</body>
</html>
```


- Vinculamos el **script** en ruta 'ajax.js'
- En **form**, agregamos una class llamada **'FormularioAjax'**, la cual nos permitira citar y reutilizar


## JS
```javascript
const formularios_ajax=document.querySelectorAll(".FormularioAjax");

function enviar_formulario_ajax(e){
    e.preventDefault();

    let enviar=confirm("Quieres enviar el formulario");

    if(enviar==true){

        let data= new FormData(this);
        let method=this.getAttribute("method");
        let action=this.getAttribute("action");

        let encabezados= new Headers();

        let config={
            method: method,
            headers: encabezados,
            mode: 'cors',
            cache: 'no-cache',
            body: data
        };

        fetch(action,config)
        .then(respuesta => respuesta.text())
        .then(respuesta =>{ 
            alert(respuesta); 
        });
    }

}

formularios_ajax.forEach(formularios => {
    formularios.addEventListener("submit",enviar_formulario_ajax);
});
```
En si no hay mucha explicacion, simplemente ese es el codigo, manipula el dom.