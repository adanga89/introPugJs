# **Introducción a PugJS**
Introducción a PugJS

***PugJS*** es un **Template Engine** o **Motor de Plantillas**.

### :question: **¿Qué es un Motor de Plantillas o Template Engine?**
Es una tecnología que permite generar toda la estructura HTML para los sitios web, es decir, una forma en la que puedes realizar modificaciones de código HTML más fácil.

Algunos ejemplos de Motor de Plantillas son:

- [Blade](https://laravel.com/docs/8.x/blade/) - Laravel
- [Handlebars](https://handlebarsjs.com/) - NodeJS
- [Moustache](https://mustache.github.io/) - JS, NodeJS, PHP, otros.
- [Twig](https://twig.symfony.com/) - Symfony 
- [Pug](https://pugjs.org/) - NodeJS
- Entre otros.

Lo anterior, no quiere decir que sean específicamente de ese Framework  o lenguaje, sino que son los más utilizados con los mencionados, y tampoco quiere decir que sean los únicos, existen muchos más.

## **Primeros pasos** :walking_man:
### :triangular_flag_on_post: ***¿Cómo instalar PugJS?***

:hammer_and_wrench: **Paso 1: Instalación NodeJS** 

De Primera instancias es necesario tener instalado [NodeJS](https://nodejs.org/), descargas la versión, dependiendo de tu sistema operativo e instalas el paquete.

Para saber si tienes correctamente instalado [NodeJS](https://nodejs.org/), tienes que abrir la **Terminal** de línea de comandos, (CMD, PowerShell, Git Bash) y ejecutas lo siguiente.
```
npm -v
```
o en su caso
```
npm --version
```

Cualquiera de los dos comandos anteriores te ayudara a visualizar la versión de node que tienes instalada.

:construction_worker_man: **Paso 2: Instalación de PugJS**

Para instalar PugJS, debes de ejecutar la siguiente línea de comando en tu terminal:
```
npm i -g pug-cli 
```
o en su caso
```
npm install global pug-cli
```
:office_worker: ***Paso 3: Crear un archivo PUG***

Para crear un archivo Pug, es necesario solo colocar la extensión _**.pug**_,  por ejemplo _**index.pug**_

:memo: ***Paso 4: Escribir el contenido del archivo PUG***

¿Cuál es la sintaxis de los archivos PUG?, bueno, en la página oficial tienen varios casos, su link es el siguiente [PugJS](https://pugjs.org/language/plain-text.html), este link es para visualizar una sintaxis de texto plano.

En la siguientes líneas se muestra como excribir un Hola Mundo en un archivo Pug y como se muestra el archivo después de compilarlo.

index.pug
```    
doctype html
html(lang="en")
head
    meta(charset="UTF-8")
    meta(http-equiv="X-UA-Compatible", content="IE=edge")
    meta(name="viewport", content="width=device-width, initial-scale=1.0")
    title Document
body 
    h1 Hola Mundo!!!
```
index.html (Archivo después de la compilación)
```    
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>Hola Mundo!!!</h1>
</body>
</html>
```
Como te habrás dado cuenta, los archivos _.pug_ son similares a los archivos _HTML_, la diferencia radica en que, los archivos _.pug_ no son etiquetas como tal, mas bien solo son el nombre de la etiqueta HTML, pero al compilar este archivo, este crea un archivo con el lenguaje HTML.

:mechanic: ***Paso 5: Compilar Archivo PUG***

Existen varios compiladores para el Motor de Plantillas PugJS, pero, ¿para qué quiero compilar el archivo PUG?. Recordemos que Pug es un motor de plantillas, no es la plantilla HTML como la conocemos, así que es necesario compilar el archivo Pug para poder visualizar el contenido en un servidor o por lo menos en un archivo HTML.

Para compilar un archivo Pug a HTML existen los siguientes comandos:

Comando para compilar un solo archivo.
```
pug nombreDelArchivo 
Ejemplo:
pug index.pug
``` 
Comando para estar a la escucha de cualquier cambio que tenga el archivo .pug y compilarlo inmediatamente
```    
pug -w nombreDelArchivo
Ejemplo:
pug -w index.pug
```
Comando para compilar todos los archivos .pug de un directorio.
```
pug nombreDelDirectorio
```

# :black_nib: [Sintaxis Básica](Sintaxis/README.md)