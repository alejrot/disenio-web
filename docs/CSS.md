
# CSS

Es un lenguaje basado en reglas. Esas reglas determinarán qué estilo darle a cada elemento definido en HTML. 
  
## Tipo archivo
Los archivos CSS deben terminar en **.css**.


## Comentarios en CSS
Los comentarios se realizan entre las secuencias `/*` y `*/` 
```css title="Comentarios en CSS"
/*  Este es mi comentario */
```

## Opciones de uso 
Hay tres opciones:

- Estilos en Linea
- Elemento `<style>`
- Archivo CSS

### Estilos en línea
El estilo se añade adentro de las etiquetas HTML como si de atributos se tratara. 

Ejemplo:
```html title="Estilos en linea"
<!-- archivo HTML -->
<h2 style="color: blue">  Mi Subtítulo </h2>
```

### Elemento `<style>`

Se describe el estilo dentro del encabezamiento (`head`) del archivo HTML. Funciona como una plantilla de estilo contenida dentro del mismo archivo HTML, pudiendo afectar a múltiples tipos de elementos y aplicándoles a todos los elementos de la misma categoría un mismo estilo predeterminado. 

Ejemplo: todos los subtítulos h2  en letra azul: 

```html title="Elemento 'style'"
<!-- archivo HTML -->
<head>
	<style>
    ...
		h2{
			color: blue;
        }
    ...
	</style>
</head>
```
Este método permite aplicar múltiples opciones de estilo a cada categoría de elementos indicada: tamaño fuente, bordes, color de fondo, sombras etc. 

!!! tip "Indentado recomendado" 
	Las guías de estilo de CSS recomiendan indentar con **dos** espacios.

### Archivo CSS
En esta opción se crea la plantilla de estilo dentro de un archivo dedicado terminado en *.css*. Lo habitual es llamar a este archivo *style.css*, pero también puede llamarse *styles.css* o *main.css*.

Para que el archivo HTML pueda invocar la guía de estilos debe pasarse el nombre de archivo CSS, esto se hace con la etiqueta link dentro de la cabeza del archivo HTML, como un metadato más:
```html title="Archivo CSS"
<!-- archivo HTML -->
<head> 
    ...
    <link href="style.css" rel="stylesheet">
<head>
```	
Prestar atención a la definición del atributo `rel` como `stylesheet`, esto define la lectura del archivo CSS como guia de estilos.


## Selectores

### Selector de tipo

Los selectores de tipo apuntan a un tipo de elemento HTML en base a su etiqueta. Por ejemplo p apunta a los párrafos, h1 a los títulos etc. 

Ejemplo uso: párrafos rojos
```css title="selector tipo"
/* archivo CSS */
p{
	color: red;
}
```
Todas las asignaciones de propiedades terminan en punto y coma (**;**).

Varios selectores de tipo pueden compartir estilo. Estos se indican separados por comas: 
```css title="selector tipo - varios tipos"
/* archivo CSS */
p, ul, ol, h3 {
	color: brown;
	font-size: 15px;
}
```

### Selector de clase
Las clases son definidas por el diseñador de la página HTML y pueden agrupar múltiples elementos. A cada elemento se le puede asignar una clase en su definición en la hoja de maquetado:
```html title="elemento HTML con clase"
<!-- archivo HTML -->
<etiqueta class="nombre-clase" ... > ... </etiqueta>
```
Y en la hoja de estilos CSS se apunta a la clase poniendo un punto delante:
```css title="selector clase - asignacion estilo"
/* archivo CSS */
.nombre-clase{
	...
}
```
Un mismo elemento puede formar parte de varias clases al mismo tiempo, cuyos nombres aparecen separados por espacios en la definición y todas entre las mismas comillas:
```html title="elemento HTML - múltiples clases"
<!-- archivo HTML -->   
<etiqueta class="clase-1 clase-2 clase-3" ... > ... </etiqueta>
```

Se acostumbra usar *guiones* en los nombres de las clases, separando las palabras que lo forman.


### Selector de ID
Para asignarle estilo a los elementos en base a su identificador se los llama con un numeral (**#**): 
```css title="ID"
#mi_identificador{
	...
}
```

### Selectores de atributo
A los elementos de un mismo tipo se los puede diferenciar en base a sus atributos. Estos se indican entre corchetes ( `[]` ). 

Ejemplo: enlaces a un sitio específico, en negrita y sin subrayado.
```css
a[href="sitio_X"]{
	text_decoration: none;
	font-weight: bold;
}
```



### Priorizar estilos
Si se intenta asignar varios estilos a un mismo elemento, se da prioridad de aplicación a los estilos más específicos frente a los más generales.Por ejemplo, dentro del archivo CSS la jerarquía se ordena de mayor a menor así:

- identificador;
- clase;
- tipo de elemento.

Si se realizan dos modificaciones de estilo con igual jerarquía el resultado será la aplicación del último estilo indicado. Si en cambio las modificaciones se realizan en distintos lugares la jerarquía queda así:

- Estilo en línea;
- Elemento `<style> `;
- Archivo CSS.

Las modificaciones en línea tienen la mayor prioridad por ser las más específicas. Para incrementar la prioridad de un estilo de manera artificial a cada propiedad se le asigna la etiqueta `!important`. Ejemplo:
```css
color: blue !important;
```

### Aplicar estilos al `body`
Modificar las propiedades del body permite dar un estilo predeterminado a todos los elementos visibles, el cual podrá ser reemplazado por los estilos asignados  posteriormente a los elementos particulares.
## Propiedades de CSS


### Color de fuente
El color de un texto se indica con la propiedad `color`:
```css
color: black; 
```
Los colores requeridos pueden especificarse en RGB (rojo-verde-azul) ó en HSV. Los editores de código suelen traer integrada una paleta para tal fin.

### Tamaño de fuente
El tamaño de fuente se controla con el atributo `font-size`:
```css
font-size: 30px;
```
Hay varias unidades de medida para especificar tamaño. Por ejemplo **`px`** permite indicar el tamaño en pixeles.

### Tipo de fuente
El tipo de caligrafía (*nombre de familia*) se asigna con el atributo `font-family`:
```css
font-family: Verdana;
```
Se pueden asignar varios tipos distintos de fuentes separados por comas, donde los primeros tendrán prioridad para ser asignados. 

!!! info "Nombres de Familias"
	Si los nombres de familia de fuentes tienen espacios en blanco estos nombres se indican entre comillas. En cambio los nombres genéricos (nombres escritos con minúsculas y guiones) **nunca** van entre comillas.

!!! tip "Google Fonts"
	En el sitio de Google Fonts: [fonts.google.com](http://fonts.google.com) hay reservada una colección de fuentes para usar. Se elige la fuente que se quiere usar y se copia el código indicado en `<link>` al *head* de HTML para que esté disponible. Luego para asignar esa fuente elegida a un elemento se hace la asignación mediante el atributo *font-family*.

### Tamaño de Imágenes
El ancho de las imágenes puede especificarse con la propiedad `width`, en tanto que la altura se especifica con la propiedad `height`
```css	title="Dimensiones absolutas"
img{
	width: 400px;
	height: 400px;
}
```
Indicando ambas propiedades se obliga al navegador a ajustar la imagen al tamaño especificado. Se puede indicar sólo una de estas propiedades, entonces el navegador intentará ajustar la imagen manteniendo la proporción de dimensiones original.

El tamaño puede ajustarse a un porcentaje de la ventana del navegador. Ejemplo:
```css title="ancho relativo a la ventana"
width: 30%;
```
### Bordes 
Se puede marcar un borde recuadrando el elemento que elijamos. Para ello se indican algunas propiedades necesarias:
```css title="Estilos de borde"
border-width: 5px;		/* espesor */
border-color: blue;		/* color */
border-style: solid;	/* estilo de linea*/
```

Para redondear los bordes hay una propiedad dedicada llamada `border-radius`:
```css title="Redondeo de borde"
border-radius: 5px;
```
Esta propiedad puede afectar también a las imágenes que sean bordeadas, dando lugar a imágenes circulares u ovaladas. 


El estilo del borde creado se indica con la propiedad `border-style`. Algunas opciones para el estilo de borde:

| **opción** | **estilo borde** |
|:---:|:---|
| none 	  | ninguno  |
| solid   | color sólido  |
| dotted  | punteado  |
| dashed  | líneas entrecortadas  |
| double  | doble línea   |        
| groove  |  |
| ridge  |  |
| inset  |   |
| outset  |   |

No es necesario que todos los bordes tengan el mismo estilo. Se puede asignar estilo por pares de valores:

```css title="Órdenes de asignación de bordes"
border-style: <todos>
border-style: <arriba-abajo> <izquierda-derecha>
border-style: <arriba> <izquierda-derecha> <abajo>
border-style: <arriba> <derecha> <abajo> <izquierda>
```


!!! tip "**Nemotécnico:**"
	Los estilos se asignan en *sentido horario*, empezando desde arriba.


### Color de fondo
Para asignar un color de fondo para un elemento existe la propiedad ***background-color***:
```css title="color de fondo"
background-color: silver;
```
Esta propiedad es muy útil usada en conjunto con los objetos *div* permitiendo crear objetos con un color de fondo predeterminado. Pueden especificarse valores en RGB y HSV.


### Padding
Es el **espacio vacío entre el elemento y sus bordes**, formando un margen interno. Se controla con la propiedad *padding*:
```css title="padding"
padding:15px;
```
Los paddings pueden ser distintos en distintos sentidos. Una forma de indicar el tamaño es mediante las etiquetas:
```css title="padding según ubicación - una linea"
padding-top: 20px;
padding-right: 15px;
padding-left: 10px;
padding-bottom: 5px;
```
Lo mismo puede hacerse en una sola línea:
```css title="padding segun ubicación"
padding: 20px 15px 10px 5px;
```
El color de fondo se controla con la propiedad background-color.

### Margen
El margen es el **espacio que está afuera del borde**.Se controla con la etiqueta *margin*:
```css title="margen"
margin: 20px;
```
Los márgenes pueden hacerse asimétricos igual que con el padding y los bordes.



## Unidades de longitud
Referencia: [Valores y unidades CSS](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Values_and_units)

### Unidades de longitud absolutas
Estas son muy usadas en el formato impreso pero no en pantalla. La excepción es la unidad píxel, que sí se usa habitualmente en pantalla. 

| **Etiqueta** | **Unidad** | 
|---|---|
| px | pixels  |
| pt | puntos  |
| pc | picas  |
| in | pulgadas  |
| mm | milimetros  |
| cm | centímetros  |
| Q  | cuartos de milimetros  |

### Unidades de longitud relativas
Las unidades de longitud relativa son relativas a un parámetro adicional. Estas unidades permiten que los elementos de la pagina escalen de forma proporcionada en base al espacio disponible. 

| **Etiqueta** | **Unidad** | 
|---|---|
| em | Tamaño de letra del elemento padre   |
| rem | Tamaño de letra del elemento raíz  |
| ex | altura x de la fuente del elemento  |
| vw | 1% del ancho de ventana gráfica  |
| vmin | 1% de dimensión mas pequeña de ventana gráfica  |
| vmax | 1% de dimensión más grande de ventana gráfica  |

Las unidades relativas dan pie al *'responsive design'*, esto es la adaptación de la página a la ventana o la pantalla disponible.


## Colores en CSS

### Códigos hexadecimales para colores
Los códigos hexadecimales van precedidos de un numeral y tienen seis dígitos desde el 0 hasta la letra F. Las dos primeras cifras indican el valor de luz roja, las dos segundas el valor de luz verde y las dos últimas la intensidad de luz azul. 

Ejemplos:

| **Color** | **Numero** |
|---|---|
| Rojo | #FF0000     |
| Verde | #00FF00     |
| Azul | #0000FF     |
| Negro | #000000     |
| Blanco | # FFFFFF     |

Las letras se pueden escribir tanto en minúsculas como en mayusculas pero debe mantenerse la consistencia en el archivo. Si los dígitos de cada color están repetidos se pueden abreviar con un solo carácter, tal como recomienda la guía de estilos de Google. 

Ejemplos:

| **Color** | **Numero** |
|---|---|
| Rojo | #F00     |
| Verde | #0F0     |
| Azul | #00F     |
| Negro | #000     |
| Blanco | # FFF     |

### Valores RGB para colores
Los colores se pueden representar también con los valores RGB, que son 3 números que pueden ir desde el cero hasta el 255. Sintaxis:
```css
rgb(<rojo>,<verde>,<azul>)
```

Ejemplos:

| **Color** | **Numero** |
|---|---|
| Rojo | rgb(255, 0, 0 )     |
| Verde | rgb(0, 255, 0 )     |
| Azul | rgb(0, 0, 255 )     |
| Negro | rgb(0, 0, 0 )     |
| Blanco | rgb(255, 255, 255 )     |

Hay un cuarto parámetro opcional: la opacidad. Este valor va de cero (transparente) a uno (máxima opacidad). Sintaxis:
```css
rgba(<rojo>, <verde>, <azul>, <alpha>)
```

## Variables CSS
Las variables en CSS se marcan con dos guiones al comienzo del nombre:
```css title="Variable CSS"
--nombre-variable: <valor>
```
Usar variables facilita hacer modificaciones sobre múltiples elementos de la página.
Para asignar esa variable a una propiedad se usa `var()`:
```css title="Variable CSS - Asignación"
<propiedad>: var(--nombre-variable);
```
Es prudente asignar también un valor de respaldo para evitar problemas cuando hay algún error con la asignación de valor a las variables. De este modo el valor de respaldo será el predeterminado en caso de error con la variable:
```css title="Variable CSS - Asignación con valor respaldo"
<propiedad>: var(--nombre-variable, <valor-respaldo>);
```

!!! warning "Compatibilidad con navegadores"
	no todos los navegadores reconocen las variables CSS. Por ejemplo: Internet Explorer no soporta las variables CSS. Para prevenir problemas es conveniente hacer una asignación de respaldo anterior a la asignación de la variable:
	```css title="Asignación de respaldo"
	<propiedad>: <valor-respaldo>;
	<propiedad>: var(--nombre-variable, <valor-respaldo>);
	```

### Heredar variables CSS
Las variables CSS se definen dentro de las clases y están disponibles para las clases descendientes. Para que una variable sea disponible globalmente se debe definir dentro del elemento `root`:
```css title="Variables CSS globales"
:root {
	--variable-global: <valor>
}
```
Si a una variable global se le intenta asignar valor desde dentro de una clase entonces lo que se creará es una variable local con igual nombre, la cual estará disponible para la clase y sus descendientes.


