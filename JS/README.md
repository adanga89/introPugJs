# JavaScript en PUG
Existen 2 formas de insertar código JavaScript, **Unbuffered** y **Buffered**.

### ¿Cuál es la diferencia?
 - **Unbuffered**: Contenido JavaScript que no se muestra cuando se compila el archivo **.pug**
 - **Buffered**: Contenido de JavaScript que se muestra cuando se compila el archivo **.pug**

Es decir, nosotros podemos tener datos de JavaScript directamente en un archivo **.pug** y decidir que se uestra o que no, si necesitamos algun resultado, etc.

Para nosotros tener algun dato tenemos que utilizar el guión medio "**-**", así pug identificara que este es un segmento de JavaScript. 

## **Unbuffered**
*Ejemplo:*

archivo.pug
```
//Comentario JS que pug lo va a compilar en comentario HTML
- let nombre = tuNombre;
-
    let miObjeto = {
        correo: "email@correo.com",
        telefono: "1122334455"
    }
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<!--Comentario JS que pug lo va a compilar en comentario HTML-->
```

Como lo habrás notado, al compilar solo se muestra el comentario del archivo **.pug**.

## **Buffered**
Literalmente es cuando queremos que **pug** al compilar muestre la información señalada, para esto se debe poner la etiqueta en donde se quiere asignar el valor, posteriormente el signo de igual y al final el valor.
```
etiqueta= valor
```
*Ejemplo:*
```
//Comentario JS que pug lo va a compilar en comentario HTML
- const language = "JavaScript";
-
    let miObjeto = {
        correo: "email@correo.com",
        telefono: "1122334455"
    }

p= `Hola soy ${language} mi correo es ${miObjeto.correo}`
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<!--Comentario JS que pug lo va a compilar en comentario HTML-->
<p>Hola soy JavaScript mi correo es email@correo.com</p>
```

# Condicionales
### :point_up: Condicinal **if-else**
Para tener un condicional **if-else**, solo lo debemos de indicar, en este caso, no necesitamos ninguna cosa extra, solo indicamos el condicional.
```
if condicion //puede o no llevar parentesis
    resultado
else
    resultado
```

*Ejemplo:*

archivo.pug
```
//Comentario JS que pug lo va a compilar en comentario HTML
- let esDeDia = true;
if esDeDia
    p Es de día
    p Es de día
else
    p Es de noche
    p Es de noche
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<!--Comentario JS que pug lo va a compilar en comentario HTML-->
<p>Es de día</p>
<p>Es de día</p>
```
### :small_red_triangle_down: Condicinal **unless**
Este condicional funciona como un **if** negado (***if !valor = unless***)
*Ejemplo:*

archivo.pug
```
//Comentario JS que pug lo va a compilar en comentario HTML
- let esDeDia = false;
unless esDeDia
    p Es de noche
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<!--Comentario JS que pug lo va a compilar en comentario HTML-->
<p>Es de noche</p>
```

# Ciclos
Se puede utilizar el ciclo de JavaScript como **for**, pero **pug** utiliza **each** para iterar.

Si utilizas **for** es necesario anteponer el guión medio **-**, pero con **each** solo tienes que hacer el llamado y si tu elemento que quieres recorrer no tiene algun valor, puedes agregar un **else** para comunicar a pug que no tienes algun valor.

*Ejemplo:*

archivo.pug
```
- for(let i = 1; i <=5; i++)
    p= i

ul
  each numero in [1,2,3,4,5]
      li= numero
  else
    li No hay valores para mostrar
```
Después de compilar el archivo **.pug**, el resultado será el siguiente.
```
<p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>
<p>5</p>
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
</ul>
```