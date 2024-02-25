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
```xml
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
- __Prólogo__
  
Se trata de la primera línea de código la cual usaremos para definir cierta información sobre el fichero XML (es opcional) como, la versión, el encoding y la validación:
```
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
```

- __Elementos__

Son los bloques fundamentales de un documento XML, forman parte de su cuerpo y dentro de ellos podemos encontrar o información o bien otros elementos. Se estructuran de forma que hay una etiqueta de apertura, contenido y una etiqueta de cierre, aunque también podemos encontrar atributos en ellos:
```
<elemento>Hola</elemento>
```

- __Atributos__
  
Los atributos proporcionan información adicional sobre un elemento. Son completamente opcionales aunque, a veces, nos resulta muy convenientes usarlos. Se colocan dentro de la etiqueta de apertura de un elemento y se forman de esta manera `nombre="valor"`. Aqui dejo un ejemplo
```xml
<elemento atributo="valor">Hola</elemento>
```

- __Comentarios__
  
Son partes del código que son ignoradas por el intérprete de xml. Se usan principalmente para una mejor comprensión del código y hacer ciertas aclaraciones para las personas que lo estén leyendo. Se colocan de manera que inicien con una etiqueta <, una exclamación, dos líneas diagonales, el contenido, dos líneas diagonales, y cierre con una etiqueta >, de la siguiente manera
```xml
<!-- Esto es un comentario en XML -->
```

- __Espacios de nombres__
  
Son un mecanismo de organización y evitan conflictos de nombres de otras fuentes. Se usan para documentos XML más complejos que funcionen con distintos estándares y distintas fuentes. Cuando definimos un espacio de nombres en una etiqueta, sus hijos lo heredarán. También podemos asignarle un prefijo al espacio de nombres Para una mayor organización. Se dfinen con `xmlns` dentro de una etiqueta y en caso de que queramos usar un prefijo lo hariamos poniendo dos puntos y el prefijo: `xmlns:ns`. Aqui dejo un ejemplo de uso de espacios de nombres:
```xml
<root xmlns:ns="http://www.ejemplo.com/namespace">
   <ns:elemento>Contenido del elemento</ns:elemento>
</root>
```

- __Entidades__
  
Al usar ciertos caracteres especiales, podemos crear conflictos en XML ya que estas pueden ser interpretadas como parte del código, para ello usaremos las entidades, que son una manera de representar estos caracteres para que sean representados como lo que son, en texto. Unos ejemplos son:
```
&lt;: Representa el carácter <.
&gt;: Representa el carácter >.
&amp;: Representa el carácter &.
&quot;: Representa el carácter ".
&apos;: Representa el carácter '.
```

- __CDATA__
  
En un espacio CDATA, todo lo que esté dentro de este será interpretado como texto plano, es decir, no entrará dentro de las reglas de XML:
```xml
<![CDATA[
   Contenido de la sección CDATA, que puede incluir <caracteres especiales> y etiquetas XML sin problemas.
]]>
```

## Validacióin de documentos
### DTD
- __Entidades__
  
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

- __Anotaciones__
  
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

- __Elementos__
  
En DTD definiremos los elementos que habrán en el XML, lo que contendrán y el tipo de dato que almacenarán. Lo haremos con la etiqueta `<!ELEMENT>` seguido del nombre del elemento y, dependiendo de si tiene información, que la pondremos con `(#PCDATA)`, o si tiene elementos, que pondremos los elementos que tiene entre paréntesis:
```xml
<!ELEMENT sitio (latitud,longitud,nombre,descripcion,localidad)>
<!ELEMENT latitud (#PCDATA)>
```

- __Atributos__
  
Definiremos los atributos con una etiqueta `<!ATTLIST>` seguido del nombre del elemento, después el nobre del atributo y luego el tipo de datos. En el tipo de datos podemos restringirlo a ciertos valores:
```xml
 <!ATTLIST persona genero (masculino|femenino)>
 <!ATTLIST libro idioma CDATA>
```

### XMLSchema
- __Definición__
  
Es un lenguaje de validación de XML más flexible que DTD. Con él tendremos más control sobre el tipo de datos pudiendo ser más precisos a la hora de definirlos, pero a cambio es más complicado de leer, entender y escribir. Un pequeño ejemplo sería esto:
```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:element name="libro">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="titulo" type="xs:string"/>
        <xs:element name="autor" type="xs:string"/>
        <xs:element name="año" type="xs:integer"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>

</xs:schema>
```

- __Estructura básica__
  
Debemos tener un espacio de nombres, como `xmlns:xs="http://www.w3.org/2001/XMLSchema` y los elementos. Dentro de los elementos tendremos información u otros elementos, y aparte los atributos (van dentro de la etiqueta del elemento). También podemos crear restricciones:
```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="libro">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="titulo" type="xs:string"/>
        <xs:element name="autor" type="xs:string"/>
        <xs:element name="año" type="xs:integer"/>
      </xs:sequence>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

- __Elementos Locales y Globales__
  
Los elementos locales se tratan de elementos que están encapsulados dentro de otros, es recomendable usarlos cuando no se van a referenciar mucho en el XML ya que no se pueden usar fuera del contexto en el que está en el esquema:
```xml
<xs:element name="persona">
  <xs:complexType>
    <xs:sequence>
      <!-- Elemento local 'nombre' -->
      <xs:element name="nombre" type="xs:string"/>
      <!-- Elemento local 'edad' -->
      <xs:element name="edad" type="xs:integer"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```
Los globales son representados fuera de otro elemento y podrán ser referenciados en cualquier momento en el documento XML, dando igual el contexto
```xml
<xs:element name="nombre" type="xs:string"/>
<xs:element name="edad" type="xs:integer"/>
```

- __Elementos simples__
  
Un elemento simple puede contener contenido directamente, en este podremos hacer restricciones de contenido pero no podremos meter más elementos o atributos, para ello usaremos un elemento complejo:
```xml
<xs:element name="puntuacion">
  <xs:simpleType>
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="0"/>
      <xs:maxInclusive value="100"/>
    </xs:restriction>
  </xs:simpleType>
</xs:element>
```

- __Elementos complejos y subelementos__
  
No pueden contener información directamente, si no que contendrán más elementos. Aquí podremos definir atributos. Se usan para anidar otros elementos que pueden ser simples o también otros complejos, estos son los subelementos. Se tratan de los elementos dentro de los complejos. Dentro de un elemento complejo podemos tener varios subelementos:
```xml
<xs:element name="biblioteca">
  <xs:complexType>
    <xs:sequence>
      <!-- Subelemento 1 -->
      <xs:element name="libro">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="titulo" type="xs:string"/>
            <xs:element name="autor" type="xs:string"/>
          </xs:sequence>
        </xs:complexType>
      </xs:element>
      <!-- Subelemento 2 -->
      <xs:element name="revista">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="titulo" type="xs:string"/>
            <xs:element name="editor" type="xs:string"/>
          </xs:sequence>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

- __Atributos__
  
Se deben introducir dentro de los elementos complejos. Los atributos tienen nombre y pueden tener otros valores dentro de la etiqueta, como un valor por defecto, su obligatoriedad o tipo de dato. A parte, podemos crear restricciones como en los elementos:
```xml
<xs:element name="coche">
  <xs:complexType>
    <xs:attribute name="color">
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value="rojo" />
          <xs:enumeration value="verde" />
          <xs:enumeration value="azul" />
        </xs:restriction>
      </xs:simpleType>
    </xs:attribute>
  </xs:complexType>
</xs:element>
```

- __Restricciones__
  
Hemos hablado mucho sobre las restricciones, y bien, no creo que haga muchafalta explicar lo que son. Las usaremos para definir las reglas que seguirá el contenido que vamos a escribir en el XML. Hay muchos tipos de restricciones algunas de ellas son:

* Restricción de Tipo (xs:simpleType)
* Restricción de Longitud (xs:length, xs:minLength, xs:maxLength)
* Restricción de Patrón (xs:pattern)
* Restricción de Valor Mínimo y Máximo (xs:minInclusive, xs:maxInclusive, xs:minExclusive, xs:maxExclusive)
* Restricción de Enumeración (xs:enumeration)
* Restricción de Fracción de Dígitos (xs:fractionDigits, xs:totalDigits)
* Restricción de Elección (xs:choice)
* Restricción de Secuencia (xs:sequence)

Las podemos aplicar tanto a atributos como a elementos simples y podemos poner varias restricciones dentro de una etiqueta de restricción. Un ejemplo de su uso sería el siguiente:
```xml
 <xs:simpleType name="CodigoProducto">
    <xs:restriction base="xs:string">
      <xs:pattern value="[A-Z]{3}[0-9]{2}"/>
      <xs:minLength value="5"/>
      <xs:maxLength value="5"/>
    </xs:restriction>
  </xs:simpleType>
```

- __Tipos de datos__
  
Con XMLSchema podemos ser muy precisos a la hora de indicar un tipo de dato. Lo haremos poniento `type=""` dentro de la etiqueta del elemento o bien poniendo `base=""` en la etiqueta de restricción. Alguno de estos tipos de datos (los más comunes) son:
* xs:string --> cadena de caracteres
* xs:integer --> Números enteros.
* xs:decimal --> Números decimales; usando “.” como separador.
* xs:boolean --> Booleano. “true” para verdadero y “false” para lo contrario.
* xs:date --> fecha con formato AAAA-MM-DD
* xs:time --> hora con formato hh:mm:ss
* xs:duration --> duración de tiempo en formato “PnYnMnDTnHnMnS”.

- __Comentarios__
  
En XML Schema, podemos incluir comentarios mediante el uso de la anotación `xs:annotation`. La anotación permite agregar información adicional y comentarios al esquema sin afectar su interpretación. Podemos utilizar `xs:documentation` dentro de `xs:annotation` para agregar comentarios descriptivos. Aquí hay un ejemplo:
```xml
 <xs:simpleType name="CodigoProducto">
    <xs:annotation>
      <xs:documentation>
        El tipo de dato CodigoProducto representa un código compuesto por tres letras mayúsculas
        seguidas de dos dígitos. La longitud total del código debe ser exactamente cinco caracteres.
      </xs:documentation>
    </xs:annotation>
    <xs:restriction base="xs:string">
      <xs:pattern value="[A-Z]{3}[0-9]{2}"/>
      <xs:minLength value="5"/>
      <xs:maxLength value="5"/>
    </xs:restriction>
  </xs:simpleType>
```
## Sistemas de Gestión de Información
- __Características__

Los sistemas de gestión de la información son programas destinados a facilitar los procesos de una empresa y su gestión ya que nos ofrecen un gran abanico de funcionalidades, por ejemplo, podremos gestionar Recursos Humanos con un ERP. Se caracterizan por ser flexibles y adaptarse a los distintos tipos de empresa, aunque nos podemos encontrar algunos especializados en cierto tipo de actividades o departamentos.

- __Tipos__

Podemos encontrar distintos tipos de sistemas de gestión de información, como los ERPs CRMs o el uso de Business Intelligence (BI)

## ERP
- __Características y beneficios__

Los ERPs integran los diferentes procesos internos de las empresas haciendo posible una mejor gestión y surpervisión de estos. Un ERP debe tener una amplia funcionalidad, es decir, que pueda brindar soluciones a todos o a la mayoría de los procesos de una empresa. Cuentan con módulos, los cuales son opcionales e independientes, para que el producto se pueda adaptar a nuestras necesidades, además su base de datos debe estar centralizada y tiene que incorporar mecanismos de seguridad para garantizar fiabilidad e integridad en los datos. Hay que resaltar también que un ERP tiene que poder mantenerse mejorarse y ampliarse dependiendo de las necesidades de nuestra empresa ya que esto permitirá la escalabilidad en un futuro. Todo esto hace que nuestra productividad suba y podamos optimizar los procesos a parte de abaratar los costes de la gestión de información.

- __ERP más conocidos__

Podemos destacar entre los ERPs más reconocido Odoo, SageX3, SAP o Apache OfBiz.

## CRM
- __Características y beneficios__

Se trata de una herramienta orientada todo lo relacionado con los clientes. Con los CRMs gestionaremos las interacciones con los clientes y podremos segmentarlos para mejorar las campañas de marketing y clasificarlos según ciertos criterios. Unificaremos los canales de comunicación y podremos supervisar y gestionar las acciones realizadas con el cliente además podremos gestionar las redes sociales. Todo esto mejorará nuestra relación con los clientes pudiendo realizar campañas de marketing más efectivas y aumentando las posibilidades y oportunidades de venta además de facilitar la toma de decisiones.

- __CRM más conocidos__

Algunos de los más conocidos son Salesforce, Zoho u Oracle Customer Experience.

## BI
- __Definición y componentes__

Es el conjunto de tecnologías que tienen como objetivo ayudar y facilitar la dirección de una empresa, y se componen de:

* ETL (Proceso de extracción de procesos)
* Data Warehouse (Almacén de datos procesados)
* OLAP (Procesamiento analítico en línea)
* Data mining (Minería de datos
* DashBoard

### ETL
En este proceso se obtiene información acerca de las operaciones realizadas por la empresa diariamente. Se procesan y se guardan en un almacén de datos. Se subdivide en 3 procesos según sus siglas:
* Extraer (Extract) - Extraer los datos
* Transformar (Transform) - Transformarlos, clasificarlos y estructurarlos
* Cargar (Load) -  Cargar los datos al almacén

### Data Warehouse
Se trata del almacén de datos. Aquí se guardan los datos de una empresa para una correcta toma de decisiones, incluyendo los extraidos por el ETL

### OLAP
Online Analytical Processing. Nos facilita el acceso a los datos almacenados en el Data Warehouse y así alimentar el siguiente proceso:

### Data Mining
Es un proceso mediante el cual se buscan patrones entre un gran volumen de datos

### DashBoard
Este nos mostrará de forma visual los datos que se obtienen de los procesos anteriores y así podremos analizarlos y realizar una mejor toma de decisiones y realizar acciones que creamos pertinentes

## HTML
### Historia
|Año|Versión|
|---|-------|
|1991|Diseño Inicial|
|1992|1.1|
|1995|2.0|
|1997|3.2|
|1997|4.0|
|1999|4.1|
|2000|XHTML|
|2014|5.0|
|2016|5.1|
|2017|5.2|

### XHTML diferencias, ventajas y desventajas con respecto a HTML
Se trata de un lenguaje busca ampliar las capacidades de HTML agregándole las normas de XML siguiendo sus reglas a diferencia de HTML. Como es de esperar, guarda ciertas similitudes con HTML pero también cuenta con ciertas diferencias:

* Las etiquetas deben estar anidadad
* Todas las eetiquetas tienen que estar cerradas
* No puede haber texto fuera de las etiquetas
* Las etiquetas y sus atributos deben ir en minúscula
* Todos los atributos deben tener valor e ir entre comillas
* No se deben insertar elementos de bloque en elementos en línea
* Scripts y estilos deben ir en un CDATA

### Estructura de un documento HTML
Un documento HTML está formado por:

#### Cabecera
* Title
En esta etiqueta se guarda el título de la página. Esto ayudará al usuario a ser consciente de qué página está visuaizando. Esto se verá en el navegador pero no en la página en si. Esta etiqueta es opcional

```html
<html>
 <head>
 <title> Mi Página </title>
</head>
```

* Meta

Guarda metadatos de la página. Esto informa al navegador de cómo van a ser los datos a representar:
__charset__: Codificación de los caracteres, usualmente UTF-8
__name__: nombre del metadato
__content__: valor asociado a atributos
__http-equiv__: Especifica una directiva. Aqui hay algunos ejemplos:
 - Content type: indica el tipo de contenido usando los tipos MIME y la codificación de caracteres
 - cache-control: define como debe gestionar el navegador la caché referente a la web
 - refresh: le dice al navegador que tras un tiempo debe refrescar la página
 - robots:  Indica a los motores de búsqueda (Como google) donde se encuentra el fichero robots.txt o que páginas no deben ser indexada
 - keywords: palabras clave. Indica a los motores de búsqueda las palabras clave asociadas a la página, interesante para el posicionamiento SEO
 - author: indica el autor de la página
 - copyright: aquí se define el propietario de los derechos de autor
 - viewport indica el ancho de la zona a representar la página. Esto es interesante ya que nunca sabremos en que dispositivo se va a visualizar el contenido y esto hará que la página se adapte a la pantalla del usuario

*  Style

Aquí se establece el estilo mediante el uso del lenguaje CSS

* Link

Esta etiqueta establece una relación con un recurso externo, como puede ser una hoja de estilos:
```html
<html>
 <head>
 <link href="style.css" rel="stylesheet" />
 </head>
 ```
 `href` indica dónde se encuentra el recurso y `rel` indica que recurso es. Por ejemplo stylesheet nos dice que es una hoja de estilos

* Script

Permite añadir un script de código ejecutable como JavaScript, el cual puede estar dentro de la etiqueta o como recurso externo
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <script>
        // Definir una variable global
        var miVariableGlobal = "hola ;)";
    </script>
```

#### Cuerpo HTML
Existen distintos tipos de elementos dentro de `<body>`:

- Elemetos de bloque
Ocupan todo el espacio del elemento contenedor y que normalente permiten contener otros elementos. Aquí nos encontramos con:

__Header__: Se trata del encabezado de la web. Suele incluir el título de la web y un logo
```html
  <header>
        <h1>pagina chulisima</h1>
    </header>
```
__Nav___: Suele albergar enlaces de navegación, tanto a elementos internos como externos
```html
<nav>
            <ul>
                <li><a href="#">Inicio</a></li>
                <li><a href="#">Acerca de</a></li>
                <li><a href="#">Servicios</a></li>
                <li><a href="#">Contacto</a></li>
            </ul>
        </nav>
```
__Main__: la etiqueta main alberga el contenido principal de la página web y dentro de él nos podemos encontrar secciones y artículos (section y article). Solo debe haber una únua etiqueta main y que esta esté bien estructurada

__Aside__: se utiliza para definir contenido auxiliar al del main. La idea es que sea contenido fijo en forma de menú con información de interés en relación a la página colocado en un lado

__Section__: se usa para delimitar las secciones en una página y que esté mejorn organizada
```html
<article>
            <h2>Título del artículo 1</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed et magna vitae eros maximus condimentum sit amet sit amet leo.</p>
        </article>
```
__Footer__: define el pie de página conteniendo enlaces genrales de la página o información de la misma o de la persona que la crea como contactos o redes sociales
```html
<footer>
        <p>Derechos de autor &copy; 2024 Mi Sitio Web</p>
    </footer>
```
__Div__: permite almacenar un contenedor con contenido personalizado
```html
 <div id="contenido1">
            <h2>Sección 1</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed et magna vitae eros maximus condimentum sit amet sit amet leo.</p>
        </div>
```
Podemos encontrar otras etiquetas como details, que al desplegar muestra contenido textual junto con la etiqueta summary, summary que almacena una dirección, dialog que muestra un diálogo al usuario (solo será visible si tene el atributo open), figure que nos permite mostrar una imagen con leyenda, la cual se añade con la etiqueta figcaption, la etiqueta hr establece un delimitador de secciones en forma de línea horizontal, o pre que puestra el texto tal cual como se encuentra en el documento html

- Elementos de línea
Se tratan de los elementos que ocupan solamente el espacio del contenido independientemente del contenedor. Nos encontramos:
__Abbr__: indica que un texto es una abreviatura o acrónimo/siglas y mostrar que significa y aparecerá subrayado
```html
<abbr title=”Hypertext Markup Language”>HTML</abbr>
```
__Bdi y bdo__: Las etiquetas bdi y bdo, permiten establecer la dirección del texto, o anular el mismo esto permitirá establecer el valor de la dirección del texto utilizando el atributo dir (con los valores rtl lrt)
```html
<p>La siguiente palabra está en árabe: <bdi dir="rtl">مرحبا بك</bdi>.</p>
<p>La siguiente palabra está en árabe, pero se ha forzado a que sea leída de izquierda a derecha: <bdo dir="ltr">مرحبا بك</bdo>.</p>
```
__Cite__: se trata de una cita. Indica que el texto que contiene referencia una fuente externa (autor, artículo, persona...)
```html
<cite>Lana del Rey</cite> dijo una vez: "We had nothing to lose, nothing to gain, nothing we desired anymore, except to make our life into a work of art.".</p>
```
__Code__: muestra un código fuente en otro lenguaje de programación como java, python, etc.
```html
<code>
            <pre>
                <span style="color: blue;">print</span>(<span style="color: green;">"Hola, mundo"</span>)
            </pre>
        </code>
```
__Data__: permite asignar valores a elementos para que sean procesados por una máquina
```html
<data value=”10500300”>10500300</data>
```
__Del__: muestra un elemento tachado e información de por qué lo está
```html
<p> La mejor cantante es<del
datetime=”2020-03-04 0:00:00” cite="razonesporlasquetaylorswiftesmalisima.html>Taylor Swift</del>Lana del Rey</p>
```
__Dfn__: se usa para definir un término, el cual aparecerá en cursiva y seguido de su definición
```html
<p><dfn>Spotify</dfn> es una plataforma de música en streaming que ofrece acceso a una amplia variedad de canciones, álbumes y playlists a través de internet. Los usuarios pueden escuchar música bajo demanda, crear listas de reproducción personalizadas y descubrir nuevos artistas y géneros musicales. Además, Spotify ofrece servicios gratuitos con anuncios y suscripciones premium sin publicidad para una experiencia de escucha sin interrupciones.</p>
```
__Ins__: agregan trazabilidad en el documento, es decir, permiten identificar elementos que se han añadido recientemente al documento. Cuenta con los atributos `cite`, que contiene la URL con la explicación del cambio y `datetime` que contiene la fecha o la hora en la que se ha realizado el cambio
```html
 <p>Xiaomi cuenta con la serie Xiaomi, Redmi y <ins>Poco</ins></p>
```
__Kbd__: permite definir atajos de teclado para mejorar la comprensión y usabilidad de la web:
```html
 <p> Para arrancar el servidor podemos usar
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>p</kbd> y pulsar la
opción <em>Live Server: Open With Live Server</em></p>
```
__Mark__: resalta el texto con un color, por defecto en amarillo:
```html
<p>El siguiente texto tiene una pedazo de<mark>palabra destacada guapísima</mark>.</p>
```
__q__: se utiliza para representar un texto citado, que puede ir acompañado de `cite`
```html
<p>Le dijeron: <q>si te juntas con ellos acabarás siendo igual</q>.</p>
```
__Samp__: indica que el texto ha sido proporcionado por el ordenador y lo diferencia del resto:
```html
<p><samp>Presione F5 para continuar </samp></p>
```
__Slot y small__: `Slot`permite definir componentes reutilizables y `small hace que un texto tenga una fuente más pequeña:
```html
<p>Este es un ejemplo de uso de <small><slot>lorem ipsum</slot></small>
```
__Span__: nos permite delimitar una porción del texto para que pueda ser personalizada en CSS de manera independiente al párrafo:
```html
<p>Texto normal o <span class"clase1">especial</span></p>
```
__Sub y sup__: se utilizan para crear subindices y superindices respectivamente:
```html
<p>0=ax<sup>2</sup>+bx+c</p>
```
__Template y time__: con `template` podemos crear fragmentos de documento mediante javascript y `time` permite establecer de manera semántica un tiempo. Tiene el atributo `datetime` que es información que va a ser leída por la máquina:
```html
<p>La fecha y hora actual es: <time datetime="2024-02-23T12:00">23 de febrero de 2024, 12:00 PM</time>.</p>
```
__Var y wbr__: con `var` podemos indicar que una palabra es una variable, la cual se mostrará en cursiva por defecto, y `wbr` indicará dónde se puede hacer un salto de línea en caso de que el texto sobrepase el espacio asignado:
```html
 <p>El valor de <var>x</var> es igual a 10<wbr>+<wbr>5<wbr>
```
- Listas, tablas y formularios

__Listas__: son elementos que nos proporcionaran una manera de organizar la información del documento de una manera más visual y diferenciar los elementos nos podemos encontrar:
Listas desordenadas: se crean con el elemento `ul` y muestran la información en viñetas:
```html
<ul>
 <li>Elemento 1</li>
 <li>Elemento 2</li>
 <li>Elemento 3</li>
</ul>
```
Listas ordenadas: con el elemento `ol`. Cuentan con una numeración en un orden concreto. Esto  puede ser modificado con los atributos `start`(para indicar el inicio de la lista), `reversed` (ascendente con false y descendente con true) y `type` (indica el tipo de lista, por ejemplo si queremos que se haga por numeros romanos o por letras)
```html
<ol type=”i”> <!--En números romanos en minúscula-->
 <li>Elemento i</li>
 <li>Elemento ii</li>
 <li>Elemento iii</li>
</ol>
```
Listas de definición: con el elemento `dl`. Permiten mostrar términos con sus definiciones. El término a definir se muestra con `dt`, y su definición con `dd`
```html
<dl>
 <dt>Microsoft</dt>
 <dd>Microsoft es una empresa dedicada a…</dd>
</dl>
```
__Tablas__: es un contenedor de elementos que permite organizarlos en filas y columnas. Una tabla se define con el elemento `table`, y dentro de él nos podemos encontrar los siguientes elementos:
Thead: indica el encabezado de una tabla, las columnas del encabezado se definen con `th` 
Thbody: indica el cuerpo de la tabla, con `tr` definiremos las filas y con `td` las columnas de cada fila. Para combinar celdas usaremos, dentro de  `td`, `colspan` para indicar las columnas que forman la celda combinada y `rowspan` para indicar las filas que la forman
Tfoot: indica el pie de la tabla
Caption: indica el título de la tabla
```html
<table>
  <thead>
    <th>Cabecera1</th>
    <th>Cabecera2</th>
  </thead>
<tbody>
   <tr>
     <td>Elemento 1</td>
     <td>Elemento 2</td>
   </tr>
</tbody>
</table>
```
__Formularios__: se trata de un elemento que permite que el usuario envíe información por la web gracias a sus elementos interactivos. Se inicia con `form` y tiene los siguientes atributos
Action: definimos la URL de destino
Method: el método para enviar la petición HTTP que normalmente va a ser GET o POST
Target: indica donde se va a abrir el contenido (_self o _blank)
Autocomplete: indica si el formulario va a permmitir el auto relleno o no

Los elementos de entrada de un formulario se definen con la etiqueta `input`, esta puede ser de varios tipos:
Button: es un botón
checkbox: es una casilla marcable
color: se puede seleccionar un color RGB
date: una fecha
datetime-local: fecha y hora
email: correo electrónico
file: un archivo
hidden: elemento 
image: un botón para enviar el formulario pero con una imágen
month: mes y año
number: valor numérico
password: una contraseña (no se verá en pantalla)
radio: selección de un único elemento
range: selección de un elemento mediante un rango
reset: resetear formulario
search: búsqueda
submit: enviar formulario
tel: un teléfono
text: texto libre
time: hora
url
week: alo y ordinal de la semana

Input cuenta con varios atributos:
autocomplete: Indica si un elemento se puede autocompletar o no
autofocus: indica si este elemento tendrá el foco cuando cargue la página
disabled: desactiva el componente
form: Referencia al id del formulario
list: asocia el componente con una lista de opciones
name: nombre del elemento que se enviará en la información del formulario
placeholder: indica un valor que aparecerá para indicar información extra
readonly: solo lectura
required: elemento obligatorio
type: tipo de elemento
value: valor por defecto
maxlength y minlength: longitud máxima o mínima de caracteres
min y max: valor mínimo y máximo numérico
pattern: expresiones regulares

Existe otro elemento, `select` que nos permite seleccionar elementos de entre una lista de opciones. Las opciones se definen en la etiqueta `option` dentro de `select`.
Podemos agrupar campos con `fieldset` y con `label` podemos asignarle una etiqueta a un campo mediante su id con el atributo `for`

- Elementos Multimedia

Podemos agregar a nuestra página contenido multimedia, como audio, vídeo o imágenes:
__Audio__: lo agregamos con la etiqueta `audio` que cuenta con los siguientes atributos:
src: la direcció del recurso, puede ser una ruta local o una URL
preload: define cómo se realizará la precarga con none (sin precarga), metadata (se precargará los metadatos) y auto (a criterio del navegador)
autoplay: reproducción automática
loop: en bucle
muted: silencia el audio
controls: interfaz de controles multimedia

__Video__: lo insertamos con la etiqueta `video` y tiene los siguientes elementos:
src: ruta o URL del recurso
poster: muestra una imágen mientras se carga el vídeo
playsinline: reproduce el vídeo dentro de su área y no a pantalla completa
width y height: ancho y alto del vídeo

__Track__: puede usarse junto a `audio` y `video` y permite añadir información a estos elementos:
default: elemento track a usar por defecto
kind: tipo de pista, subtitles (subtítulos), captions (transcripciones) descriptions (descripciones), chapters (capítulos) y metadata
label: título de la pista
srclang: idioma del elemento

__Imágenes__: se insertan con `img` y tiene los siguientes atributos:
alt: descripción de la imágen de forma altenrativa (accesibilidad)
src: dónde se encuentra la imágen (ruta, URL...)
srcset y sizes: permite asignar diferentes recursos para que el navegador cargue la versión más adecuada
usemap: referencia a un mapa en la etiqueta `map`
ismap: indica que es parte de un mapa del lado del servidor
width y height: ancho y alto
decoding: indica cómo se debe decodificar la imágen; async (asíncrono), sync (síncrono) y auto (decide el navegador)
loading: indica como se cargará la imágen; eager (inmediatamente) o lazy (a posteriory)

__Mapas__: se insertan con la etiqueta `map` y estos son imágenes interactivas. Cuenta con el elemento `area`, el cual es el que nos va a permitir definir qué partes del mapa serán las interactivas y qué haran cuando interactuemos con ellas. Cuente con los siguientes atributos:
alt: versión en texto del área
shape: tipo de figura con la cual se va a representar el área interactuable; circle (círculo), rect (rectangular), poly (polígono) o default (todo el área)
coords: coordenadas de la figura (depende de la forma)
href: ruta a la que apunta, puede ser una URL o en local
target: dónde se cargará el elemento al pulsar sobre él
download, ping y rel: igual que para los enlaces

__Imágenes vectoriales__: se tratan de imágenes que no se deformarán o se emborronarán si se reescalan y gracias al elemento `svg` podremos crearlas
```html
<svg xmlns=”http://w3.org/2000/svg/” width=”150”
height=”100”>
<rect width=”4” height=”1” y=”0” fill=”#00ab39” />
</svg>
```

__Canvas__: nos brinda un lienzo sobre el que mostrar gráficos, usando normalmente lenguajes de script como puede ser JavaScript y cuenta con los atributos `width` y `heigth`

__Contenido Incrustado__: se trata de contenido que está alojado fuera de nuestra web pero que podrá ser usado dentro de esta. Podemos distinguir 3 etiquetas:
  Embed: contenido incrustado por un plugin o elemento externo y dependiendo del contenido, puede que sea más o menos soportado por el navegador. Tiene los atributos `src` (fuente del recurso), `type` (tipo MIME), `width` y `heigth`


  iframe: es un documento HTML externo incrustado, y cuenta con los siguientes atributos
  
src

srcdoc: contiene el código HTML a mostrar

sandbox: restricciones al documento incrustado

allow: directivas referentes a permisos

allowfullscreen: permitie el tamaño a pantalla completa

width y heigth

loading (lazy o eager)


  Object: permite incrustar cualquier otro elemento que esté dentro de los tipos MIME y cuenta con los siguientes elementos

data: conteine el recurso que se va a mostrar

type: tipo MIME

name: nombre que puede ser usado para hacer referencia a este recurso

usemap: referencia a un mapa

form: referencia al id de un formulario

width y heigth


- Herramientas de edición y desarrollo web

