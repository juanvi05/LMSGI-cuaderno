# Cuaderno lenguaje de marcas
# Tabla de contenidos
## Enlaces de interés
* [W3](https://www.w3.org/)

## Qué es un Lenguaje de marcas
Es un lenguaje escrito usando caracteres especiales y texto legible para los humanos. El texto es interpretado por un software especifico (normalmente un navegador web) para luego mostrarlo en un formato específico el cual es dado por cómo se ha escrito el texto usando el lenguaje de marcas, por ejemplo, ahora que estoy usando Markdown, si escribo una palabra entre dos asteriscos (** xxxxx **) a cada lado se verá en negrita: **prueba**
## Evolución de los lenguajes de marcas
- SGML
Se trata de un metalenguaje, se usa como base para la creación de otros lenguajes de marcado como HTML y XML.

- GML
Es un lenguaje creado con el propósito de mostrar información cartográfica en aplicaciones especificas sobre la geografía

## Características de los lenguajes de marcas
**No son lenguajes de programación**, se tratan de lenguajes para la visualización de contenido. La escritura de estos lenguajes es legible para los humanos ya que se usan palabras, pero cada lenguaje de marcas tiene su sintáxis específica además de una estructura jerárquica para organizar el contenido. Estos lenguajes son usados en la gran mayoría de aplicaciones gracias a su flexibilidad y adaptabilidad a cada situación en especifico.

## Características y ejemplos de los siguientes lenguajes de marcas
- XML
  
Se trata de un lenguaje de marcas usado para almacenar y mostrar información de manera legible tanto para un ordenador como para un ser humano. Cuenta con las bases de un lenguaje de marcado (como la estructura jerárquica, el uso de marcas para el contenido o los atributos) y con características diferenciadoras como lo es el esquema XML que nos permite especificar las reglas y la estructura válida en nuestro documento. Un ejemplo de este tipo de lenguaje de marcas sería el siguiente:

```
<?xml version="1.0" encoding="UTF-8"?>
<coche marca="Toyota" modelo="Corolla">
    <descripcion>
        <color>Rojo</color>
        <año>2022</año>
        <precio moneda="USD">20000</precio>
    </descripcion>
    <caracteristicas>
        <motor tipo="Gasolina">1.8L</motor>
        <transmision>Automática</transmision>
</coche>

```

- HTML
  
Un lenguaje enfocado a la web y a la presentación de contenido. Con él podremos añadir enlaces, multimedia, formularios y una infinidad de posibilidades con sus atributos. También podremos darle formato al texto sin necesidad de usar CSS ya que tambien tiene atributos dedicados a esto, como `style`. He aquí un ejemplo de un código HTML:

```
<!DOCTYPE html>
<html>
<head>
    <title>Ejemplo HTML</title>
</head>
<body>
    <h1>¡Hola, mundo!</h1>
    <p>Esto es un HTML de ejemplo.</p>
</body>
</html>

```

- JSON
  
Está destinado al intercambio de datos entre una aplicación y un servicio web. Utiliza una sintáxis simple basada en "clave-valor" cada línea separada por comas y resulta legible para el ojo humano. Tiene una estructura anidada y jerárquica, lo que significa que un objeto JSON puede contener otros objetos JSON y cada clave puede contener más de un valor:

```
{
    "libros": [
        {
            "titulo": "El Gran Gatsby",
            "autor": "F. Scott Fitzgerald",
            "publicacion": 1925,
            "genero": "Novela"
        },
        {
            "titulo": "Cien años de soledad",
            "autor": "Gabriel García Márquez",
            "publicacion": 1967,
            "genero": "Novela"
        },
    ]
}

```

- YAML
  
Un lenguaje destinado especialmente a archivos de configuración escritos de manera sencilla y entendible. Se suelen hacer anotaciones dentro del archivo y se caracteriza tambien por las referecias, lo que nos permite la reutilización de un dato sin tener que escribirlo, evitando así la duplicación de este. Aqui dejo un ejemplo de YAML:

```
#Let NetworkManager manage all devices on this system
network:
  version: 2
  renderer: NetworkManager
  ethernets:
   enp0s3:
    dhcp4: no
    addresses
    - 192.168.0.80/24
    gateway4: 192.168.0.1
    nameserver:
     addresses: [192.168.0.20]

```
  
## XML: definición y características del metalenguaje
- Prologo

Se trata de una línea opcional al inicio del archivo XML, la cual indica ciertos parámetros sobre el archivo. El prólogo, por lo general, incluye lo siguiente:

```
<?xml version="1.0" encoding="utf-8" standalone="no"?>

```
Comienza con `<?xml version=""` que indica la versión que se está usando, luego `encoding=""` que nos indica que codificación de caracteres se está usando (lo más usual es UTF-8 ya que admite todos los caracteres alfanuméricos) y por último `standalone="">` lo cual se usa para la validación del documento.

- Contenido

El contenido está comprendido entre una etiqueta raíz la cual marcará el inicio y el fin de este. El contenido debre estar marcado por etiquetas y sus atributos si se precisa de ellos de manera que el cuerpo del archivo quedaría tal que así:
```
<raiz>
  <colores>
    <color>Rojo</color>
    <color>Verde</color>
    <color>Azul</color>
  </colores>
</raiz>

```
- Atributos

Los atributos son valores que se encuentran dentro de las etiquetas. Se usan para añadir información a el valor y optimizar el espacio en el documento. Muchas veces también nos resulta más facil la lectura si los valores del objeto los dividimos entre atributos y el cuerpo del objeto. Se ven tal que así:

```ruby
<persona nombre="Juan" edad="30" genero="Masculino" />

```
- Ejemplos en XML

Por lo tanto, un archivo XML completo quedaría tal que así:
```ruby
<?xml version="1.0" encoding="UTF-8"?>
<root>
    <cancion id="1" genero="alternativo">
        <titulo>Video Games</titulo>
        <album>Born to Die</album>
        <año>2011</año>
    </cancion>
    <cancion id="2" genero="alternativo">
        <titulo>Religion</titulo>
        <album>Honeymoon</album>
        <año>2015</año>
    </cancion>
    <cancion id="3" genero="blues rock">
        <titulo>Shades of Cool</titulo>
        <album>Ultraviolence</album>
        <año>2014</año>
    </cancion>
</root>
```
## Documentos XML, estructura
- Prólogo
Se trata de la primera línea de código la cual usaremos para definir cierta información sobre el fichero XML (es opcional) como, la versión, el encoding y la validación:
```
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
```

- Elementos
Son los bloques fundamentales de un documento XML, forman parte de su cuerpo y dentro de ellos podemos encontrar o información o bien otros elementos. Se estructuran de forma que hay una etiqueta de apertura, contenido y una etiqueta de cierre, aunque también podemos encontrar atributos en ellos:
```
<elemento>Hola</elemento>
```

- Atributos
Los atributos proporcionan información adicional sobre un elemento. Son completamente opcionales aunque, a veces, nos resulta muy convenientes usarlos. Se colocan dentro de la etiqueta de apertura de un elemento y se forman de esta manera `nombre="valor"`. Aqui dejo un ejemplo
```xml
<elemento atributo="valor">Hola</elemento>
```

- Comentarios
Son partes del código que son ignoradas por el intérprete de xml. Se usan principalmente para una mejor comprensión del código y hacer ciertas aclaraciones para las personas que lo estén leyendo. Se colocan de manera que inicien con una etiqueta <, una exclamación, dos líneas diagonales, el contenido, dos líneas diagonales, y cierre con una etiqueta >, de la siguiente manera
```xml
<!-- Esto es un comentario en XML -->
```

- Espacios de nombres
Son un mecanismo de organización y evitan conflictos de nombres de otras fuentes. Se usan para documentos XML más complejos que funcionen con distintos estándares y distintas fuentes. Cuando definimos un espacio de nombres en una etiqueta, sus hijos lo heredarán. También podemos asignarle un prefijo al espacio de nombres Para una mayor organización. Se dfinen con `xmlns` dentro de una etiqueta y en caso de que queramos usar un prefijo lo hariamos poniendo dos puntos y el prefijo: `xmlns:ns`. Aqui dejo un ejemplo de uso de espacios de nombres:
```xml
<root xmlns:ns="http://www.ejemplo.com/namespace">
   <ns:elemento>Contenido del elemento</ns:elemento>
</root>
```

- Entidades
Al usar ciertos caracteres especiales, podemos crear conflictos en XML ya que estas pueden ser interpretadas como parte del código, para ello usaremos las entidades, que son una manera de representar estos caracteres para que sean representados como lo que son, en texto. Unos ejemplos son:
```
&lt;: Representa el carácter <.
&gt;: Representa el carácter >.
&amp;: Representa el carácter &.
&quot;: Representa el carácter ".
&apos;: Representa el carácter '.
```

- CDATA
En un espacio CDATA, todo lo que esté dentro de este será interpretado como texto plano, es decir, no entrará dentro de las reglas de XML:
```xml
<![CDATA[
   Contenido de la sección CDATA, que puede incluir <caracteres especiales> y etiquetas XML sin problemas.
]]>
```

## Validacióin de documentos
### DTD
- Entidades
Puede que a lo largo de la creación del documento tengamos que repetir las mismas palabras y expresiones y para ello haremos uso de las entidades en DTD, en las cuales asociaremos frases o palabras a ciertas expresiones, de esta manera ahorraremos tiempo y espacio:
```xml
<!ENTITY saludo "¡Hola, mundo!">
```
Lo usamos:
```xml
<texto>&saludo;</texto>
```
Y mostrará esto:
```xml
<texto>¡Hola, mundo!</texto>
```

- Anotaciones
Son comentarios. Los usaremos para organizar y aclarar el contenido en el DTD:
```xml
<!-- Definición del DTD para un libro -->

<!ELEMENT libro (titulo, autor, editorial, año)>
<!ELEMENT titulo (#PCDATA)>
<!ELEMENT autor (#PCDATA)>
<!ELEMENT editorial (#PCDATA)>
<!ELEMENT año (#PCDATA)>

<!-- Atributos adicionales para el elemento libro -->
<!ATTLIST libro idioma CDATA #IMPLIED>
```

- Elementos
En DTD definiremos los elementos que habrán en el XML, lo que contendrán y el tipo de dato que almacenarán. Lo haremos con la etiqueta `<!ELEMENT>` seguido del nombre del elemento y, dependiendo de si tiene información, que la pondremos con `(#PCDATA)`, o si tiene elementos, que pondremos los elementos que tiene entre paréntesis:
```xml
<!ELEMENT sitio (latitud,longitud,nombre,descripcion,localidad)>
<!ELEMENT latitud (#PCDATA)>
```

- Atributos
Definiremos los atributos con una etiqueta `<!ATTLIST>` seguido del nombre del elemento, después el nobre del atributo y luego el tipo de datos. En el tipo de datos podemos restringirlo a ciertos valores:
```xml
 <!ATTLIST persona genero (masculino|femenino)>
 <!ATTLIST libro idioma CDATA>
```

