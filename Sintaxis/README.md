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
Para anidar etiquetas o poner una o varias etiquetas dentro de otras, solo tenemos que utilizar la identación o las tabulaciones con un salto de línea. Observa el siguiente ejemplo para que quede más claro.

*Ejemplo:*

archivo.pug
```
form
    div         
        p Este es un párrafo
        small Este es un texto pequeño
            b Este es un bold dentro del small
        
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<form>
    <div>
        <p>Este es un párrafo</p>
        <small>Este es un texto pequeño<b>Este es un bold dentro del small</b></small>
    </div>
</form>
```

### :purple_circle: _**¿Cómo puedo añadir atributos a las etiquetas HTML en PugJS?**_
Para añadir los atributos de las etiquetas se debe colocar entre paréntesis los valores que requieras, estos se pueden separar por espacios o por comas, por ejemplo:

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

### :purple_circle: _**¿Cómo puedo añadir clases o id's a las etiquetas HTML en PugJS?**_
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
```

### :purple_circle: _**¿Cómo puedo añadir scripts en el archivo PugJS?**_
Para poder añadir una hoja de **JavaScript**, puedes hacer el mismo proceso de las etiquetas con su respectivo atributo o si es necesario tener escrito el codigo **JavaScript** directamente en la página, solo tienes que especificar el nombre de la etiqueta y después colocar un punto y seguir la regla de la identación/tabulación.

archivo.pug
```
script(src="js/archivo.js", async, defer,)

script.
    function saludar(nombre){
        alert(`Hola ${nombre}`);
    }
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<script src="js/archivo.js" async defer></script>
<script>
    function saludar(nombre) {
        alert(`Hola $ {nombre}`);
    }
</script>
```

### :purple_circle: _**¿Cómo puedo añadir estilos en el archivo PugJS?**_
Al igual que los script:
1. Se puede con el nombre de la etiqueta y sus atributos, esto para agregar una hoja de estilos, 
2. Con la etiqueta style seguido de un punto, puedes escribir todo el código CSS que quieras.
3. Dentro de las etiquetas con el atributo **style**, pero este atributo en lugar de ser solo el texto, es necesario pasar un objeto para que la etiqueta tome el valor deseado.

    :warning:	Si tu estilo utiliza propiedades que el nombre tenga una separación con una línea media, por ejemplo **font-size**, es necesario encerrar entre comillas esa propiedad, ya que, al enviar un objeto en los atributos, JavaScript no lo interpreta así.

archivo.pug
```
link(rel="stylesheet", href="style.css")

style.
    .rojo{
        color: red;
    }

a(href="#" style={color:"red", "font-size":"2em"}) Link
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<link rel="stylesheet" href="style.css" />

<style>
    .rojo {
        color: red;
    }
</style>

<a href="#" style="color:red;font-size:2em;">Link</a>
```

## :star: TIPs
### :zap:  **Omitir la etiqueta *div***
Puedes omitir la etiqueta **div** si esta tiene un ID o una clase, por ejemplo, **div.container** por **.container**, **pug** identificará que esa clase tendrá una etiqueta div. 

archivo.pug
```
.container
    a.link(href="#") Link
#otroDiv
    a.link(href="#") Link
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<div class="container"><a class="link" href="#">Link</a></div>
<div id="otroDiv"><a class="link" href="#">Link</a></div>
```

### :zap:  **Anidar sin salto de línea**
Puedes anidar una etiqueta dentro de otra colocando dos puntos ":" después de la etiqueta, esto significa que la etiqueta es hija y con esto puedes ahorrarte un salto de linea.

archivo.pug
```
div.container: a.link(href="#") Link
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<div class="container"><a class="link" href="#">Link</a></div>
```

:warning: Hay que tener cuidado, ya que si, después de esta etiqueta queremos agregar más etiquetas, esta al estar anidando con los dos puntos, agrupará lo que quieras ingresar suponiendo que las demás etiquetas son hijas de la anterior, esto se vé mejor en un ejemplo.

_Suponiendo que quieres hacer un menú._

archivo.pug
```
ul
    li: a.link(href="#") Abrir menú
        ul
            li Opción 1
            li Opción 2
            li Opción 3
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<ul>
    <li>
        <a class="link" href="#">Abrir menú
            <ul>
                <li>Opción 1</li>
                <li>Opción 2</li>
                <li>Opción 3</li>
            </ul>
        </a>
    </li>
</ul>
```
:warning: Cuando compilas el archivo **.pug**, toda la etiqueta **a** envuelve a el otro **ul**, si eso no es lo que quieres, deberás seguir las reglas normales de identación/tabulación.

archivo.pug
```
ul
    li
      a.link(href="#") Abrir menú
      ul
          li Opción 1
          li Opción 2
          li Opción 3
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<ul>
    <li>
        <a class="link" href="#">Abrir menú</a>
        <ul>
            <li>Opción 1</li>
            <li>Opción 2</li>
            <li>Opción 3</li>
        </ul>
    </li>
</ul>
```

### :zap:  **Escribir con salto de línea**
Algunas veces necesitaras agregar un salto de línea cuando este maquetando con **pug**, para esto se utiliza el **pipeline (|)**

archivo.pug
```
p Este es un párrafo largo y quiero
    |  un link que redirija a 
    a(href="#") Google
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<p>Este es un párrafo laro y quiero un link que redirija a <a href="#">Google</a></p>
```
Así podemos hacer que el código no se vea tan largo y tenga mejor vista.

:warning: Hay que tener cuidado nuevamente, ya que **pug**, su regla es la identación/tabulación, si utilizas el pipeline al mismo nivel que tienes la etiqueta, el texto lo pondrá fuera de la etiqueta.

archivo.pug
```
p Este es un párrafo laro y quiero
|  un link que redirija a 
a(href="#") Google
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<p>Este es un párrafo laro y quiero</p> un link que redirija a <a href="#">Google</a>
```

### :zap:  **Escribir etiquetas dentro de un texto largo**
Para insertar eiquetas dentro de un texto largo **pug** facilita el uso de la interpolación con el uso de **#[etiqueta contenido]**

archivo.pug
```
p Lorem ipsum dolor sit, amet consectetur adipisicing elit. Adipisci laborum ratione sunt cumque repudiandae. #[span Hola Mundo!!] Ea provident atque quis voluptate in #[a(href="#") fugit] corrupti doloribus, impedit incidunt architecto consequuntur earum quae rem.
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Adipisci laborum ratione sunt cumque repudiandae. <span>Hola Mundo!!</span> Ea provident atque quis voluptate in <a href="#">fugit</a> corrupti doloribus, impedit incidunt architecto consequuntur earum quae rem.</p>
```