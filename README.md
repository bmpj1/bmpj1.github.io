# The Elm Architecture

Aplicaciones Distribuídas en Internet, Universidad de Alicante, curso 2020/21.
- Brais Valencia García 
- Brian Mathias Pesci Juliani

# Índice
<!-- TABLE OF CONTENTS -->
  <ol>
    <li><a href="#introducción">Introducción</a></li>
    <li><a href="#desarrollo">Desarrollo</a>
      <ul><a href="#historia">Historia</a></ul>
      <ul><a href="#elm">Elm como lenguaje de programación</a></ul>
      <ul><a href="#instalación">Instalación y puesta en marcha</a></ul>
      <ul><a href="#código">Código y ejemplos</a></ul>
    </li>
  <li><a href="#conclusión">Conclusión</a></li>
  <li><a href="#bibliografía">Bibliografía</a></li>
  </ol>

# Introducción 
El lenguaje de programación Elm, está orientado a navegadores web y nos permite
crear interfaces gráficas de usuario. Elm es un lenguaje desarrollado con 
énfasis en la usabilidad, el rendimiento y la robustez. Facilita la modularidad, 
la reutilización de código y el testeo.<br>
Además, es un lenguaje funcional puro y fuertemente tipificado. Por tanto, se proclama
como un lenguaje sin fallos en la práctica. <br>

# Desarrollo 
## Historia 
Evan Czaplicki diseñó en 2012 la versión inicial de Elm como resultado
de su tesis. Poco después aparecería la primera versión pública,
dotada de ejemplos abundantes y un editor en línea.<br>
En 2013, Evan Czaplicki se unió a la empresa Prezi con la idea de 
seguir desarrollando el lenguaje de programación Elm.<br>
En 2016, NoRedInk incorporo en sus filas a Evan como Ingeniero de 
Software para trabajar con código libre, seguir con el proyecto Elm y la creación 
de la [Elm Software Foundation](https://elm-lang.org/news/new-adventures-for-elm).<br>

## Elm como lenguaje de programación 
La implementación inicial del compilador producía HTML, CSS, y Javascript. El conjunto 
de herramientas del lenguaje continuó expandiéndose, ahora incluyendo un REPL, 
gestor de paquetes, depurador con viaje en el tiempo, e instaladores para Linux, Mac y Windows.
Elm también tiene un ecosistema de librerías creadas por la comunidad y un editor en 
línea avanzado que permite incluir dichas librerías y guardar el código para compartirlo.<br>
       
CARACTERISTICAS:Elm tiene un pequeño pero expresivo conjunto de funcionalidades en el lenguaje, 
incluyendo expresiones if, creación de variables locales, y expresiones case para 
la búsqueda de patrones. Como lenguaje funcional, tiene funciones anónimas, funciones como 
argumentos, y aplicación parcial (currificación) por defecto. Su semántica incluye valores inmutables, 
funciones puras, y tipado estático con inferencia de tipos. Los programas de Elm producen HTML a 
través de un sistema de DOM virtual, y pueden interoperar con otro código Javascript.<br>

Inmutabilidad	Editar
Todos los valores en Elm son inmutables, un valor no puede ser modificado después de ser creado. 
Elm utiliza estructuras de datos persistentes para implementar sus librerías Array, Dict, y Set.<br>

Tipos estáticos	Editar
Elm usa un sistema de tipado estático. Las anotaciones de tipos son opcionales, debido a 
la inferencia de tipos, pero recomendadas. Las anotaciones se ponen en la línea de arriba de 
la definición (no como en los lenguajes de la familia de C, donde los tipos y los nombres de 
las variables/parámetros están mezclados). Elm usa un solo carácter : para significar 
la definición de tipos.<br>

Los tipos incluyen primitivas como números enteros y cadenas de texto, y estructuras de 
datos básicas como listas (List ), tuplas (Tuple) y records (objetos). Las funciones se escriben 
con flechas, por ejemplo round : Float -> Int. Union types (tipos de unión) permiten al programador 
crear tipos personalizados para representar datos de manera apropiada al dominio del problema.<br>

Los tipos pueden referenciar otros tipos, por ejemplo, una lista de números enteros es List Int. 
Los tipos siempre empiezan con letra en mayúscula, las variables empiezan con letra en minúscula. 
Por ejemplo, una List a es una lista de valores de tipo desconocido. Hay unos cuantos tipos 
especiales que los programadores crean para interactionar con el sistema de ejecución de Elm. 
Por ejemplo, Html Msg representa un árbol del DOM (virtual) cuyos manejadores de eventos producen 
mensajes de tipo Msg.<br>

En vez de permitir que cualquier valor sea null implícitamente (como undefined o null en JavaScript), 
la librería estándar de Elm define un tipo Maybe a . El código que produce o maneja valores 
opcionales lo hace utilizando explícitamente este tipo, y todo el código tiene garantías de 
que el valor que dice ser de un cierto tipo esta garantizado tener un valor de ese tipo presente.<br>

Sistema de módulos	Editar
Elm tiene un sistema de módulos que permite a los usuarios dividir el código en partes 
más pequeñas llamadas módulos. Los módulos pueden esconder detalles de implementación, 
tales como funciones auxiliares, y agrupar código relacionado. Los módulos sirven como espacio 
de nombres a la hora de importar código, como por ejemplo Tuple.first. Las librerías o paquetes 
de terceros consisten en uno o más módulos, y están disponibles en la librería de paquetes de Elm.<br>
Todos los paquetes y librerías se versionan utilizando versionado semántico, que es 
verificado y hecho cumplir por el compilador y otras herramientas. Esto significa, que quitar 
una función, o cambiar su tipo, puede ser hecho solo incrementando la versión mayor.<br>

Interoperabilidad con HTML, CSS y JavaScript	Editar
Elm utiliza una abstracción llamada ports (puertos) para comunicarse con JavaScript. Permite que los 
valores fluyan hacia dentro y fuera de los programas Elm, haciendo posible la comunicación 
entre Elm y JavaScript.<br>

Elm tiene una librería llamada elm-html que un programador puede utilizar para escribir HTML y CSS en Elm.
Utiliza un sistema de DOM virtual para hacer las actualizaciones en la página más eficientes.<br>

## Instalación y puesta en marcha
* Instalar ELM con instalador en windows: https://github.com/elm/compiler/releases/download/0.19.1/installer-for-windows.exe
* Instalar ELM con instalador en Mac: https://github.com/elm/compiler/releases/download/0.19.1/installer-for-mac.pkg
* Instalar ELM en Linux: https://github.com/elm/compiler/blob/master/installers/linux/README.md
```shell
$ cd ~/Desktop/
$ curl -L -o elm.gz https://github.com/elm/compiler/releases/download/0.19.1/binary-for-linux-64-bit.gz
$ gunzip elm.gz
$ chmod +x elm
$ sudo mv elm /usr/local/bin/
$ elm --help
```
**Iniciar un proyecto ELM:**
```shell
$ elm init
```
Este comando crea un elm.json y el directorio src/ donde:
  * **elm.json** describe tu proyecto
  * **src/** contiene todos tus archivos .elm
<br>
<p>Una vez creado el proyecto podemos proceder a crear nuestro primer archivo Hello.elm y agregar el siguiente código de ejemplo:</p>

```elm
import Html exposing (text)

main =
  text "Hello!"
```
<p>Una vez creado el archivo, podemos proceder a compilarlo y generar un .html o .js con los siguientes comandos:</p>

```shell
# Create an index.html file that you can open in your browser.
$ elm make src/Main.elm

# Create an optimized JS file to embed in a custom HTML document.
$ elm make src/Main.elm --optimize --output=elm.js
```
<p>Esta es la manera más general de compilar código .elm. Es extremadamente útil una vez que tu proyecto se vuelve muy avanzado.</p>
<p>Una vez compilado, podemos instalar los paquetes, los cuales se registran en "package.elm-lang.org". Para ello, ejecutamos los siguientes comandos (en función de que necesitemos realizar peticiones http o json):</p>
  
 ```shell
 $ elm install elm/http
 $ elm install elm/json
 ```
 <p>Al hacer esto, estamos agregando las dependencias en tu archivo "elm.json", haciendo que estos paquetes estén disponibles en tu proyecto. Esto te permitirá escribir "import Http..." y usar funciones como Http.get en tus programas.</p>
 
  
## Código y ejemplos

# Conclusión 
Breve resumen de lo explicado antes y conclusión.

# Bibliografía
Como instalarlo: https://guide.elm-lang.org/architecture/
Documentación: https://guide.elm-lang.org/install/elm.html


