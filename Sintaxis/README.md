# Sintaxis Básica

### :mage: _**¿Cómo crear etiquetas HTML en PugJS?**_
Para crear etiquetas HTML en un archivo **.pug** solo se pone el nombre de la etiqueta, es decir, si quieres poner una etiqueta de párrafo solo tendrías que poner la _**p**_, o si quieres poner una encabezado solo tendrías que poner  _**h1**_.

*Ejemplo:*

archivo.pug
```
h1 Título del encabezado
p Este es un párrafo
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<h1>Título del encabezado</h1>
<p>Este es un párrafo</p>
```

### :purple_circle: _**¿Cómo puedo anidar etiquetas HTML en PugJS?**_
Para adinar etiquetas o poner una o varias etiquetas dentro de otras, solo tenemos que utilizar la identación o las tabulaciones con un salto de línea. Observa el siguiente ejemplo para que quede mas claro.

*Ejemplo:*

archivo.pug
```
form
    div         
        p Este es un parrafo
        small Este es un texto pequeño
            b Este es un bold dentro del small
        
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<form>
    <div>
        <p>Este es un parrafo</p>
        <small>Este es un texto pequeño<b>Este es un bold dentro del small</b></small>
    </div>
</form>
```

### :purple_circle: _**¿Cómo puedo añadir atributos a las etiqutas HTML en PugJS?**_
Para añador los atributos de las etiquetas se debe colocar entre parentesis los valores que requieras, estos se pueden separar por espacios o por comas, por ejemplo:

```
etiqueta(atributo="valorDelAtributo") 
```
*Ejemplo:*

Para crear un link:

archivo.pug
```
a(href="http://www.google.com" target="_blank") Google
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<a href="http://www.google.com" target="_blank">Google</a>
```
*Ejemplo 2:*

archivo.pug
```
form(method="POST" action="pagina.php")
    input(type="text")
    button(type="submit") Aceptar
        
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<form method="POST" action="pagina.php">
    <input type="text" />
    <button type="submit">Aceptar</button>
</form>
```

### :purple_circle: _**¿Cómo puedo añadir clases o id's a las etiqutas HTML en PugJS?**_
Puedes agregar de dos formas las clases y los ids en los archivos **.pug**:

**1. Como si añadieras atributos a la etiqueta**

archivo.pug
```
a(href="http://www.google.com" target="_blank" class="btn btn-primary" id="boton") Google
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<a href="http://www.google.com" target="_blank" class="btn btn-primary" id="boton">Google</a>
```
**2. Como si fueran estilos CSS.**

archivo.pug
```
a#boton.btn(href="http://www.google.com" target="_blank") Google
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<a class="btn" id="boton" href="http://www.google.com" target="_blank">Google</a>