# HTML


Página de referencia: [MDN de Mozilla](https://developer.mozilla.org/es/)

Guia estilos Google: [HTML/CSS Guide Style](https://google.github.io/styleguide/htmlcssguide.html)

## Tipo archivo
Los archivos HTML deben tener terminación `.html`.


## Formato
Todo archivo HTML debe comenzar con la declaración de tipo de documento (DTD, Document Type Declaration):
```html
<!DOCTYPE html>
```
El nombre de archivo debe tener extensión .html.

## Comentarios 
Los comentarios se hacen con la secuencia:
```html
<!--  (contenido)  -- >
```

!!! tip  "Hint"
    Para comentar o descomentar lineas en VSCode / VSCodium pulsar **'Ctrl' + '/'** (**'Ctrl' +'ç'** en Windows)


## Elemento
Componente básico de un archivo HTML.
Etiquetas (Tag)
Sirven para definir los elementos en el archivo HTML. Son marcadas con paréntesis angulares (**<>**). Normalmente las etiquetas se usan de a pares, una para apertura **(<___>**) y otra para cierre ( **</___>**) la cual incluye una barra. Entre etiquetas se distribuye el contenido.
Ejemplos:

```html 
<html>  ...	</html>
<head>  ...	</head>
<body>  ... </body> 
```

Las etiquetas *'Self Closing Tag'* no requieren cierre. 

Ejemplo:
```html
<img>
```
**Opcional:** añadir la barra al final de la etiqueta. Ejemplo:
```html
<img/>
```
La etiqueta `<html>` representa la raíz del archivo e incluye dos grandes conjuntos: la cabeza (`head`) y el cuerpo (`body`). `body` encapsula el contenido de la página en tanto que `head`  incluye archivos externos ,archivos de configuración etc.


```html title="Organización página HTML"
<!DOCTYPE html>
<html>
	<head>
	<!-- Contenido del encabezamiento -->
	</head>
	<body>
    <!-- Contenido del cuerpo -->
    </body> 
</html>
```
Se recomienda indentar con dos espacios. En VSCode se puede cambiar el indentado presionando **'Ctrl' + '['** ó **'Ctrl' + ']'**.

## Atributos
Son elementos que alteran aspectos de los elementos.

## Idioma
El idioma se asigna mediante el atributo `lang` y va dentro de la etiqueta html. 

Ejemplo:
```html title="Atributo idioma"
<html lang="es">
...
</html>
```
La declaración de idioma afecta a los buscadores pero también a los caracteres no ASCII visualizables en la página.

El orden en que se asignan los atributos a un mismo elemento es irrelevante.

## Encabezamientos (*heading*)
Los encabezamientos permiten indicar títulos para los contenidos. Van dentro del body del archivo html. Hay seis niveles de jerarquía, del 1 (más importante) al 6 (menos importante).
```html title="Encabezamientos"
<body>
    <h1> Titulo </h1>
    <h2> Subtitulo </h2>
    ...
    <h6> ... </h6>
</body>
```

!!! info "Jerarquía y formato"
    Si bien HTML les da a cada nivel de *headings* un tamaño distinto, la elección de etiquetas debe hacerse por **importancia del contenido** y no por formato, el cual puede alterarse mediante CSS. De esta forma los buscadores web pueden clasificar las páginas web (**SEO**) en base a los *headings*.

## Párrafos
Los párrafos se encapsulan con las etiquetas `<p>` y `</p>`. Los párrafos van dentro del body.

```html title="Párrafo"
<p>
<!-- Párrafo -->
</p>
```

**Hint:** Para que un texto se vea repartido en varios renglones del editor de texto pulsar Alt + Z.

## Main

Indica el contenido principal del `body` entre dos etiquetas:
```html title="Contenido principal - main"
<body>
    <main>
        <!-- Contenido principal -->
  </main>
  <!-- ... -->
</body>
```
El contenido `main` **debe ser único** en la página y no descender de elementos como:
```html
<article> 
<aside>
<footer>
<footer>
<header> 
<gav>
```

## Imágenes
Se indican con etiquetas <img> que son autocontenidas.Si la imagen está ubicada en un servidor remoto se indica en el atributo src (source):
```html
<img src="https://direccion_completa.jpg">
```
A las imágenes se les puede asignar una breve descripción para aquellos casos donde la imagen no puede cargarse, esto se hace con el atributo alt:
```html
<img src="https://direccion_completa.jpg" alt="una breve descripción.">
```
Si la imagen está guardada localmente se escribe la ruta relativa al archivo:
```html
<img src="ruta_relativa/archivo.jpg">
```
El directorio de referencia es el que incluye al archivo HTML.

!!! warning "Nombres con caracteres no ASCII"
    Debe evitarse el uso de caracteres no ASCII (ejemplo: la *Ñ*) para nombres de archivo dado que pueden dar lugar a errores imprevistos.

## Enlaces Externos

Los enlaces se indican con las etiquetas <a> y </a> y el atributo href indica la dirección de destino:
```html title="Enlace externo"
<a href="https://sitio_web"> Texto del enlace   </a>
```
Para abrir el enlace en una nueva pestaña se puede añadir el atributo `target` y asignarle el valor “_blank"
```html title="Enlace externo - Abrir en nueva pestaña"
<a href="https://sitio_web" target="_blank"> Texto del enlace   </a>
```
Se recomienda añadir un atributo más para prevenir ataques de tipo *'Tabnapping'*:
```html title="Enlace externo - Prevencion de 'tabnapping'"
<a href="https://sitio_web" target="_blank" rel="noopener noreferrer">Texto del enlace</a>
```

Las opciones agregadas son:

- `noopener` previene el cambio de página donde se hizo click. Por defecto mucos navegadores la agregan automáticamente en cada link;
- `noreferrer`: previene enviar el *header* del remitente a la nueva página para prevenir una posible suplantación de identidad (*spoofing*)


## Enlaces a Secciones Internas

Estos enlaces usan también las etiquetas `<a>` y `</a>` pero con distintos valores de atributos:

```html title="Enlace interno"
<a id="#etiqueta_destino"> texto_enlace <a>
```

Para apuntar a un sector específico se indica el atributo id (indicador único) del elemento precedido por un numeral (**#**). 

!!! example "Ejemplo: enlace a subtitulo"

    ```html title="destino: 'seccion-5'"
    <!-- subtitulo con ID -->
    <h2 id="seccion-5"> Tema 5 </h2>
    ```
    ```html title="enlace a 'seccion-5'"
    <!-- enlace a subtitulo -->
    <a href="#seccion-5"> Ir al Tema 5 </a>
    ```

## Enlaces con Imágenes

Las imágenes se pueden usar como enlace.Para ello se coloca un elemento del tipo imagen dentro de un elemento enlace:
```html title="Enlace con imagenes"
<!-- imagen en red -->
<a href="direccion_enlace"> <img src="https://direccion_imagen"> </a> 
<!-- imagen local-->
<a href="direccion_enlace"> <img src="ruta_imagen"> </a> 
```
Pueden añadirse todos los atributos vistos previamente.

## Enlaces Muertos

Un enlace vacío puede crearse con el numeral , esto es útil en la etapa de diseño:

```html title="Enlaces muertos"
<a href="#"> (Ir a ningún sitio) </a>
```

## Listas no ordenadas

Las listas no ordenadas (*unordered list*) usan la etiqueta `#!html ul` para agrupar los elementos de la lista (*list items*) indicados con la etiqueta `li` : 
```html title="Listas no ordenadas"
<ul>
	<li> ... </li>
	<li> ... </li>
    <!-- ... -->
	<li> ... </li>
</ul>
```

## Listas ordenadas

Las listas ordenadas (*ordered list*) usan la etiqueta `ol` para agrupar los elementos de la lista (*list items*) indicados con la etiqueta `li` : 
```html title="Listas ordenadas"
<ol>
	<li> ... </li>
    <!-- ... -->
	<li> ... </li>
</ol>
```
Los números se asignan automáticamente desde el uno en adelante.

## Negrita y Strong

Los textos más importantes pueden marcarse con la etiqueta ***strong***, esto hace ver los caracteres en negrita:
```html title="Negrita - Strong"
<strong> Texto </strong> 
```
Otra opción es usar la etiqueta `b` (bold), aunque esta se está evitando actualmente.
```html title="Negrita - Bold"
<b> Texto </b>
```
## Cursiva

El texto en cursiva se indica con la etiqueta `em`:
```html title="Cursiva"
<em> Texto en cursiva </em>
```
## Tachado
El tachado de texto se hace con la etiqueta `s` (*strikethrough*)
```html title="Tachado"
<s> Texto tachado </s>
```
## Línea Horizontal
La *horizontal rule*  se indica con la etiqueta `hr`:
```html title="Linea horizontal"
<hr>
```
## Salto de Línea 
Para forzar un salto de línea se usa la etiqueta ***`br`***:
```html title="Salto de línea"
<br>
```
## Formularios

Los formularios usan la etiqueta `form` para agrupar sus elementos. En el ejemplo se crea un espacio para escribir un texto de entrada (`input`) y un botón (`button`) para ordenar el envío. 
```html title="Formulario"
<form action="ruta_destino">
<input type="text" placeholder="indicaciones" required>
<button type="submit"> Enviar <button>  
</form>
```
El atributo `placeholder` indica un texto marcador de posición, que da una pista sobre la entrada esperada en `input`. El destino de la respuesta puedeser una URL o un archivo local que se indica con el atributo `action`. Para impedir el envío de la entrada vacía se agrega el atributo `required`. 

Los distintos elementos se dibujan en pantalla uno al lado del otro. Para colocarlos en vertical usar el salto de línea  (`br`) .

## Botones de Radio 

El botón de opción (o botón de radio) se crea con la etiqueta 
```html title="Botón radio"
<input type="radio"> Texto descripcion
```
Para marcar el botón debe presionarse encima. Para poder presionar tambien sobre el texto de descripción se rodea el botón con la etiqueta `label`:
```html title="Botón radio - con etiqueta"
<label> <input type="radio"> Texto descripcion   </label>
```
La etiqueta `label` puede tener indicado el atributo `for` que la vincula al identificador del botón:
```html 
<label for="identificador">
 <input id="identificador" type="radio"> Texto descripcion   
</label>
```

## Grupo de Botones de Radio

Para que varios botones forman parte de un mismo grupo y sólo uno pueda seleccionarse a la vez debe agregarse el atributo `name` a cada botón y darles el mismo valor. 

Ejemplo:
```html
<input type="radio" id="opcion_1" name="nombre_opciones"> Opción 1
<input type="radio" id="opcion_2" name="nombre_opciones"> Opción 2
```
## Casillas de Verificación
Las checkbox  o casillas de verificación se definen también con la etiqueta *input*:
```html
<input type="checkbox"> Texto descripción
```
Con el atributo checked se puede dejar marcado de forma predeterminada la casilla de verificación:
```html
<input type="checkbox" checked> Texto descripción
```

## Value

El atributo valor (`value`) es el argumento que se enviará al servidor si la casilla ó botón de radio fue seleccionado. 

Ejemplo: casillas verificacion.

```html
<input type="checkbox" value="opcion_1" > Opción 1
<input type="checkbox" value="opcion_2" > Opción 2
```

## Div
La etiqueta `div` sirve para definir “contenedores" de elementos. Se usa para agrupar elementos 
```html
<div>
	<!-- elementos internos -->
</div>
```

## Pie de Página
El pie de página va afuera de `main` (pero dentro del *body*). Utiliza la etiqueta `footer`. 

Ejemplo típico: texto de licencia y enlace al post original:
```html title="Pie de página"
<footer>
	<p> Licencia <a href="direccion_enlace"> Original </a></p>
</footer>
```

## Small
Esta etiqueta hace la letra más pequeña. Es muy habitual en los pies de página. 

Uso:
```html
<small> texto pequeño </small>
```

## Head
*Head* contiene todos los metadatos de la página. Va antes del *body*. Ejemplo sencillo:
```html
<head>
    <title> Mi titulo de pagina </title>	
</head>
```

## Contenido editable
Podemos permitir que el usuario de la página altere el texto de los elementos gracias al atributo *contenteditable*. Ejemplos:
```html
<div contenteditable="true"> Hola soy un div </div>
<label contenteditable="true"> Hola soy un div </label>
```

## Color Picker
Creando un elemento *input* del tipo color podemos crear un botón de color con el cual el usuario puede invocar la paleta de colores e interactuar con ella.
```html
<input type="color" >
```
Para asignar un color por defecto al botón se añade el atributo *value*:
```html 
<input type="color" value="green;">
```

## Marcado texto
Usando la etiqueta *mark* podemos marcar trozos de texto al estilo resaltador.
```html
<p>
	Un parrafo donde uso un poco  <mark style="background-color=yellow">  el marcador </mark>
</p>
```
## Barra de Progreso
Con la etiqueta meter se puede crear fácilmente una barra de progreso. Ejemplo: barra al 50%
```html
<meter min="0" max="100" value="50"> </meter>
```
Otra opción es usar la etiqueta progress:
```html
<progress min="0" max="100" value="50"> 50% </progress>
```
El texto entre etiquetas no se ve en todos los navegadores. 

## Corrector ortográfico
Con habilitar el atributo ***spellcheck*** dentro de los elementos *input* se habilita la corrección ortográfica automática.

## Acordeón (texto desplegable)
Con la etiqueta details se crea un texto desplegable con un clic, cuya parte siempre visible se indica con la etiqueta summary. Útil para dar información extra sobre un elemento.
```html
<details>
    <summary> Texto siempre visible </summary>
    Todo el texto adicional listo para ser visto con un click.
</details>
```

## Diálogos
Un cuadro de diálogo siempre abierto:
```html
<dialog open> Mi texto </dialog>
```
Para que el cuadro de diálogo se abra al presionar un botón y se cierre con otro:
```html
<button onclick="dlg.showModal()">  Abrir </button>
    <dialog id="dlg"> 
    <button onclick="dlg.close()">  X </button>
    Mi texto 
</dialog>	
```

## Relacionar label con input
Algunas formas de poner el foco en el elemento de entrada clickeando sobre la etiqueta de texto relacionada.
Ejemplo texto:
```html
<label for="texto_123" > Poner foco </label>
<input type="text"   id="texto_123" />
```
Ejemplo *checkbox*:
```html    
<label for="check_123" > Chequear </label>
<input type="checkbox"   id="check_123" />
```

## Agrupar opciones
Con el elemento **select** se puede hacer una lista de opciones desplegable. Con la etiqueta option se marca cada opción seleccionable y con la etiqueta optgroup se hacen separadores de texto. Ejemplo:
```html
<select>
	<optgroup label="Grupo 1"> </optgroup>
	    <option> Opcion 1 </option>
        <option> Opcion 2 </option>
    <optgroup label="Grupo 2"> </optgroup>
        <option> Opcion 3 </option>
        <option> Opcion 4 </option>
        <option> Opcion 5 </option>
<select>
```

## Autocompletado
Una entrada de texto puede tener valores opcionales predeterminados. Con la etiqueta datalist se crea una lista de opciones y esta se invoca dentro del elemento input con el atributo list.
```html
<input list="opciones" type="text" placeholder="seleccionar">	
<datalist id="opciones">
	<option> Opcion 1 </option>
    <option> Opcion 2 </option>
    <option> Opcion 3 </option>
</datalist>
```

## Marquesina
Una marquesina es un texto que se desliza solo por la pantalla. Utiliza la etiqueta marquee. 
Ejemplo: un título animado. 
```html
<marquee> <h1> Mi Título Móvil  </h1></marquee>
```

## Patterns para validar expresiones regulares
El atributo pattern es el que permite exigir un formato de entrada al usuario. Asimismo el atributo title da un texto de ayuda y el atributo required obliga al usuario a cumplir para poder enviar. 

Ejemplo: se requiere escribir tres cifras entre el 0 y el 9
```html
<input pattern="[0-9]{3}"
title="Debes poner 3 numeros seguidos para enviar."
type="text" required>
<input type="submit">
```
## Texto alineado a la derecha
Con el atributo dir se puede corregir  la orientación de un texto.
Ejemplo: ***'rtl'*** (*right to left*)
```html
<p dir="rtl"> Texto a la derecha </p>
```
Ejemplo: ***'ltr'*** (*left to right*)
```html
<p dir="ltr"> Texto a la derecha </p>
```


## Teclas de acceso
Con el atributo accesskey especificamos las letras que accionan un elemento. 
Ejemplo: un botón accionado presionando ‘Alt’+’L’ que envía un mensaje a pantalla.
```html
<button accesskey="L" onclick="alert('¡Accionado!')" >
    Me selecciono con la letra L.
</button>
```

## Múltiple
El atributo multiple permite seleccionar varios elementos u opciones juntas. 
Ejemplo: seleccionar uno o varios archivos de imagen jpg
```html
<input type="file" accept=".jpg" multiple>
```
Otro ejemplo: varias opciones seleccionables
```html
<select multiple>
	<option> Opcion 1 </option>
    <option> Opcion 2 </option>
    <!-- ... -->
</select>
```

## Crear atributos libres
Con el atributo **data-** se pueden crear nuevos atributos. Los valores de estos valores se pueden consultar con el método ***dataset***  en base al *id* del elemento de referencia.

Ejemplo: atributos *country* y *style* creados y consultables con un click.
```html
<p data-country="Bélgica" data-style="Strong Ale" id="someP"> 
    <button onclick=alert(someP.dataset.country+`-`+someP.dataset.style)>
        Show 
    </button>
```


## Autofocus
El atributo autofocus permite enfocar automáticamente al elemento que lo incluye. Ejemplo:
```html
<input type="text" value="" autofocus>
```

## Descarga automática
Podemos ordenar la descarga de un elemento al que apunta un enlace añadiendo el atributo ***download*** a la etiqueta del enlace.

Ejemplo: factura en PDF para descargar
```html
<a download href="factura.pdf"> Descargar factura </a>
```

## Orden de formularios
El completado de elementos input se puede ordenar con ayuda del atributo tabindex. Los números se recorren de menor a mayor. Ejemplo: un formulario que se completa de abajo hacia arriba
```html
<input tabindex="4" type="text" > <br> 
<input tabindex="3" type="text" > <br> 
<input tabindex="2" type="text" > <br> 
<input tabindex="1" type="text" > <br> 
```
## Step (salto)
Para controlar el incremento o decremento de un número controlado con el mouse se especifica el atributo step.

Ejemplo 1: un número que puede subir o bajar con el mouse de décima en décima
```html
<input type="number" min="0" max="10" step=0.1
```
Ejemplo 2: una barra deslizante que cambia de a saltos
```html
<input type="range"min="0" step="10" max="100">
```
Ejemplo 3: un reloj que da saltos de 15 minutos (900 segudos)
```html
<input type="time" min="09:00" step="900">
```

## Draggable (Arrastrable)
Usa JavaScript: https://youtu.be/U6W-xE_GzCo?list=TLPQMDgwMzIwMjOAtf43LnsPsw&t=924


