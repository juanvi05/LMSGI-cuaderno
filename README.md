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
