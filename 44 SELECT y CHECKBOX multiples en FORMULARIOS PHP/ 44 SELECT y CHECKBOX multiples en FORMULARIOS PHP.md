#  44 SELECT y CHECKBOX multiples en FORMULARIOS PHP
## Select multiple
```html
<html>
<body>

    <form action="index.php" method="POST">

        <label for="asignatura">Asignatura</label>
        <select name="asignatura[]" id="asignatura" multiple>
            <option value="Ingles">Ingles</option>
            <option value="Matematica">Matematica</option>
            <option value="Ciencia">Ciencia</option>
            <option value="Lenguaje">Lenguaje</option>
        </select>
</body>
</html>
```
Dentro de la etiqueta `select`, se le agregan corchetes al `name`, porque pasa a ser un array. Se agrega el atributo `multiple` dentro de la etiqueta

## index.php
```php
<?php
$materias = $_POST['asignatura'];

foreach($materias as $asignatura){
   echo $asignatura.'<br>';
}
```
Al relacionarlo por medio de POST o de GET, no deben colocarse los corchetes, ya que interpreta automaticamente que es un array.

## Checkbox multiple
```html
<body>
    <form action="index.php" method="POST">
        <label for="opcion-1">
            <input type="checkbox" value='Banana' id='opcion-1' name='frutas[]'>
            Banana
        </label>

        <label for="opcion-2">
            <input type="checkbox" value='Pera' id='opcion-2' name='frutas[]'>
            Pera
        </label>
        
        <label for="opcion-3">
            <input type="checkbox" value='Manzana' id='opcion-3' name='frutas[]'>
            Manzana
        </label>
    
        <br><br><br>
    
        <button type='submit'>Enviar</button>
    </form>
```
Dentro de la etiqueta `input`, se le agregan corchetes al `name`, porque pasa a ser un array. Obligatoriamente debe coincidir el `id` del `input` con el `for` del `label`

## index.php
```php
$frutas = $_POST['frutas'];
foreach($frutas as $contenido){
    echo $contenido.'<br>';
}
```
Misma historia que el select.
