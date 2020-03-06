Creación de mapas en QGIS
=========================

Esta entrada presenta una introducción general de cómo hacer mapas en
QGIS. Pretende servir para incentivar el uso de QGIS en personas ajenas
a los profesionales en Sistemas de Información Geográfica (SIG) y
promover el uso de herramientas gratuitas de análisis de datos
geográficos.

Para el tutorial utilizaremos los datos del [[Sistema Nacional de
Información Territorial (SNIT) de Costa
Rica]{.underline}](http://www.snitcr.go.cr), del [[Índice de Desarrollo
Humano (IDH) Cantonal 2016 de Costa
Rica]{.underline}](http://desarrollohumano.or.cr/) y la versión 3 de
[[QGIS]{.underline}](http://www.qgis.org).

QGIS es un programa de Sistemas de Información Geográfica (SIG) gratuito
y de código abierto con una interfaz gráfica amigable al usuarios
disponible para distintas plataformas. Actualmente es la opción gratuita
más completa y fácil de usar para realizar análisis de datos espaciales.
QGIS se puede descargar desde
[[www.qgis.org]{.underline}](https://www.qgis.org/en/site/forusers/download.html)

### Objetivo del tutorial: 

-   Elaborar un mapa de Costa Rica que resalte con nombre y en un
    > gradiente de color los valores del índice de desarrollo humano de
    > los 10 cantones con los valores menores.

### Notas para tomar en cuenta durante el tutorial:

> El tutorial se realizará utilizando la versión en inglés de **QGIS
> versión 3.2.3**.

Parte 1: Abrir QGIS y cargar los datos de límites cantonales del SNIT
---------------------------------------------------------------------

1\. Dar doble click al ícono de QGIS.

> ![](.//media/image2.png){width="1.0677088801399826in"
> height="1.1000634295713037in"}

2\. Dar click en *Layer - Add Layer - Add WFS Layer\...*

![](.//media/image23.png){width="6.5in" height="4.4375in"}

De esta manera estaremos agregando al QGIS la dirección del
*WebFeatureService (WFS)* del SNIT para los datos oficiales de Costa
Rica escala 1:5,000. Para más información sobre qué es un WFS pueden
acceder la entrada anterior del blog sobre tipos de datos geográficos.

3\. En la ventana que aparece, dar click en el botón de *New* de la
sección *Server connections.*

![](.//media/image24.png){width="6.5in" height="4.916666666666667in"}

4\. Seguidamente escribiremos en el espacio *Name* el nombre que le
queremos dar a este conjunto de datos, por ejemplo:
*CartografiaCR\_1:5000*.

5\. En el espacio URL copiaremos la dirección del servicio del SNIT para
estos datos:

**[<http://geos.snitcr.go.cr/be/IGN_5/wfs>?]{.underline}**

6\. Dar click en *OK* para aceptar y cerrar esa ventana.

![](.//media/image6.png){width="6.5in" height="4.916666666666667in"}

> Vale la pena mencionar que el SNIT es la Infraestructura de Datos
> Espaciales (IDE) oficial de Costa Rica. En esta plataforma se pueden
> encontrar datos geográficos producidos por distintas instituciones
> públicas del país. Estos datos geográficos se sirven tanto en formatos
> OGC (estándares de datos para poderlos desplegarlos en programas de
> SIG sin necesidad de descargar todo el conjunto de datos en la
> computadora) así como también en la herramienta de mapas online con
> que cuenta la plataforma. En nuestro caso usaremos QGIS para trabajar
> los datos porque nos da mayor flexibilidad que la herramienta web.
>
> La lista completa de fuentes de información y conjuntos de datos con
> que cuenta el SNIT se puede acceder
> [[acá]{.underline}](http://www.snitcr.go.cr/servicios_ogc_completo).
>
> Muchos países cuentan desde hace varios años con IDEs donde se pueden
> acceder muchos conjuntos de datos geográficos libremente. Normalmente
> con una búsqueda de Google pueden encontrar el IDE del país o gobierno
> local donde viven.

6\. Dar click en Connect

![](.//media/image14.png){width="6.5in" height="4.902777777777778in"}

Seguidamente aparecerá la lista de *capas* que tiene ese conjunto de
datos. Cada una de estas viene siendo como una tabla - cuadro con
información geográfica. En nuestro caso queremos desplegar la que tiene
la información sobre los límites cantonales del país.

7\. Dar click en *Límite Cantonal 1:5mil* y en *Add* (esquina inferior
derecha de la ventana).

![](.//media/image16.png){width="6.5in" height="4.902777777777778in"}

Luego aparecerá una ventana con el indicador de la descarga de la capa
seleccionada. Al ser una capa con una escala bastante fina (1:5000), el
tamaño de la información es grande, por lo que dependiendo de la
velocidad de conexión podrá tomarse varios segundos en desplegarse.

La capa desplegada muestra un polígono por cada cantón del país. Nótese
que en *Layers* (ventana inferior izquierda) se muestra la capa que
recién agregamos y hay un *checkbox* donde podemos ocultar y volver a
hacer visible la capa.

![](.//media/image22.png){width="6.5in" height="4.875in"}

Parte 2: Cargar tabla con datos del IDH
---------------------------------------

Los datos del Índice de Desarrollo Humano (IDH) que se utilizarán en
este ejercicio son tomados del trabajo del PNUD y la Universidad de
Costa Rica [*[Atlas de Desarrollo Humano Cantonal de Costa Rica
2016]{.underline}*](http://desarrollohumano.or.cr/). En nuestro caso
utilizaremos los datos de los 10 cantones con menor índice de IDH para
el año 2014.

1\. Copiar y guardar la siguiente tabla en un archivo con terminación
***.csv***. Esto puede hacerse copiando y pegando la tabla en una hoja
de Excel y guardándola como archivo .csv (archivo separado por comas).

Nota: Como es necesario mantener las tildes de los nombres de los
cantones, el archivo se debe salvar con el formato de codificación de
caracteres UTF-8. Dependiendo de la versión de Excel que se utilice,
esto está en la lista de tipos de archivos del *guardar como*.

  **Canton**   **2014**
  ------------ ----------
  Los Chiles   0.617
  Talamanca    0.634
  Matina       0.645
  Upala        0.651
  La Cruz      0.651
  Coto Brus    0.669
  Guácimo      0.670
  Guatuso      0.670
  Alajuelita   0.676

2\. En QGIS dar click en *Layer - Add Layer - Add Delimited Text Layer
...* y seleccionar el archivo creado en el paso anterior.

![](.//media/image27.png){width="6.5in" height="4.305555555555555in"}

La ventana deberá tener la información como la que se ve a continuación.

Nótese que el *Encoding* también debe ser UTF-8 y que en el cuadro de
*Geometry definition* indicamos el *No geometry (attribute only table)*.
Esto último significa que la tabla que estamos agregando no tiene
información geográfica.

![](.//media/image18.png){width="6.5in" height="4.916666666666667in"}

3\. Dar click en *Add* para importar la tabla al QGIS y luego *Close*
para cerrar la ventana.

Nótese que ahora en la lista de capas del QGIS nos aparecen las dos que
cargamos anteriormente pero que la última, al no tener información
geográfica (coordenadas), no tiene el *checkbox* desplegarla y
ocultarla. Si queremos ver esta tabla debemos darle click derecho a la
capa y luego click izquierdo en *Open Attribute Table.*

![](.//media/image29.png){width="6.5in" height="4.875in"}

Parte 3: Unión de tablas por atributo común
-------------------------------------------

Como vimos anteriormente tenemos dos \"capas\" cargadas en QGIS, una
tiene información geográfica (polígonos con los cantones de Costa Rica)
y la otra únicamente tiene información tabular (Cantones y valor de
IDH). Lo que debemos hacer ahora es unir estas dos capas por un campo
común.

Para ver la tabla de atributos de la capa del SNIT, le damos también
click derecho y luego click izquierdo en *Open Attribute Table*. En sus
atributos vemos que hay una columna con el nombre de los cantones en un
formato similar a la tabla con IDH (letra inicial en mayúscula y nombres
con tildes), lo que hace que podamos unir ambas tablas usando los
nombres de los cantones.

![](.//media/image26.png){width="6.5in" height="4.097222222222222in"}

1\. Dar click derecho en la capa del SNIT y click izquierdo en
*Properties*.

![](.//media/image17.png){width="6.5in" height="4.875in"}

2\. Damos click en la pestaña de *Join* y damos click en el signo de
**+** de la esquina inferior izquierda. Seguidamente seleccionamos para
*Join layer* la tabla con los valores de IDH, para *Join field* la
columna *Canton* y en *Target field* la columna *nom\_canton* de los
atributos de la capa del SNIT. Luego de esto damos click en *OK*.

![](.//media/image13.png){width="6.5in" height="3.7777777777777777in"}

Si ahora abrimos la tabla de atributos de la capa del SNIT y vemos las
últimas columnas, podemos notar que se agregó una columna nueva con el
nombre de la tabla de IDH. Esta nueva columna tiene valores numéricos
para únicamente los 10 cantones de la tabla, el resto de cantones tienen
valores nulos (*NULL*).

![](.//media/image28.png){width="6.5in" height="4.291666666666667in"}

Parte 4: Elaboración de mapa
----------------------------

1\. Hacemos *zoom* a la parte continental de Costa Rica con el botón de
lupa:

![](.//media/image1.png){width="0.7916666666666666in"
height="0.7916666666666666in"}

2\. Dar doble click en la capa original del SNIT para ver las
propiedades. En la nueva ventana dar click en la pestaña de *Symbology*.

3\. De las opciones de la simbología, en el menú superior seleccionar
*Categorized*, en *Column* la columna que queremos utilizar (la de la
tabla con los valores de IDH), en *Color ramp* alguna paleta de colores
atractiva (en mi caso seleccioné Viridis). Luego dar click en el botón
de *Classify* para ver la clasificación de colores de cada valor de IDH.

![](.//media/image8.png){width="6.447916666666667in"
height="3.7916666666666665in"}

Ya que el color amarillo que se asignaría a los cantones en que el IDH
es nulo es muy llamativo (último valor de la lista de colores), podemos
dar click en él y seleccionar un color más neutro, en mi caso seleccioné
el color blanco.

![](.//media/image7.png){width="3.4791666666666665in"
height="6.21875in"}

Dar click en *OK* para ver las modificaciones que se hicieron.

![](.//media/image15.png){width="6.5in" height="4.708333333333333in"}

4\. Para que el mapa muestre los nombres de los 10 cantones con menores
valores de IDH volvemos a entrar a las propiedades de la capa del SNIT
(doble click o click derecho y luego click izquierdo en
*Properties\...*).

5\. En el menú de las propiedades damos click en la pestaña de *Labels.*
Y ahí en el menú superior damos click en *Rule-based labeling*.

6\. Ahora vamos a crear una regla para que el mapa únicamente muestre
los nombres de los cantones con valores de IDH (10 cantones con menores
IDH). Para esto damos click en el signo de + en la parte inferior
derecha de la ventana y en el campo de *Filter* copiamos la expresión
de:

**\"IDH10cantones\_2014\" IS NOT NULL**

7\. En la misma ventana dar click al cuadro de *Labels* y en el menú de
*Label with* seleccionar la columna con los nombres de los cantones que
queremos utilizar como etiquetas: *nom\_cant*.

Si se explora la parte inferior de la ventana de *Edit Rule* se ven las
opciones para cambiar el tipo de letra, color, tamaño, etc. Ajustarlo al
gusto y dar click en *OK*.

![](.//media/image5.png){width="4.006902887139107in"
height="5.348958880139983in"}

7\. Al regresar a la ventana de propiedades, quitarle el check a la
regla de *(no filter)* (ver la captura de pantalla abajo) y dar click en
*OK*.

![](.//media/image9.png){width="6.5in" height="3.7777777777777777in"}

En caso de querer cambiar los colores, tipo y tamaño de letra se puede
hacer nuevamente desde la ventana de propiedades de la capa, haciendo
click en el ícono de edición:

![](.//media/image12.png){width="0.6718755468066492in"
height="0.2889063867016623in"}

![](.//media/image20.png){width="6.5in" height="4.75in"}

Parte 5: Exportar el mapa
-------------------------

1\. Para darle los toques finales al mapa, agregar simbología, título y
escala utilizamos la herramienta de *layout*. La accedemos en el menú de
*Project - New Print Layout...*

![](.//media/image21.png){width="6.5in" height="3.0555555555555554in"}

2\. En la ventana que aparece damos click en OK

3\. En el menú de la ventana de *Layout* hacemos click en *Add Item -
Add Map* y seguidamente marcamos arrastrando y soltando en la hoja
blanca la extensión que queremos que tenga nuestro mapa.

![](.//media/image3.png){width="6.5in" height="3.4027777777777777in"}

4\. Agregamos la leyenda haciendo click en *Add Item - Add Legend* y
seleccionamos con click de arrastrar y soltar donde queremos la leyenda
en nuestro mapa.

![](.//media/image19.png){width="6.5in" height="3.6527777777777777in"}

![](.//media/image11.png){width="6.5in" height="4.722222222222222in"}

5\. Para corregir los elementos de la leyenda (eliminar el nombre de la
tabla de IDH y corregir el nombre de la capa del SNIT) damos click en la
leyenda. Nos damos cuenta que está seleccionada por los cuadros celestes
que se marcan en sus bordes.

5.1. En el menú de *Item Properties* de la derecha de la ventana hacemos
click para desmarcar el checkbox de *Auto update*.

5.2. En esa misma sección de la ventana damos click en la tabla con
valores de IDH para seleccionarla y luego damos click en el botón de
**-** (color rojo), en la parte inferior de la ventana, para eliminarla
de la leyenda.

![](.//media/image4.png){width="6.5in" height="4.763888888888889in"}

5.3. En esa misma sección de la ventana damos click en la capa del SNIT
y luego en el botón de edición. Cambiamos el nombre que se desplegará en
la leyenda para esa capa.

![](.//media/image25.png){width="6.447916666666667in" height="4.8125in"}

5.4 Damos click en OK para aceptar los cambios.

6\. Agregamos escala del mapa haciendo click en *Add Item - Add Scale
Bar* y marcamos arrastrando y soltando en la hoja blanca la posición y
tamaño que queremos que tenga.

7\. Agregamos el título del mapa haciendo click en *Add Item - Add
Label* y marcamos arrastrando y soltando la posición y tamaño del cuadro
donde queremos que esté el título.

8\. Cambiamos el nombre del título haciendo click en el cuadro del
título y luego en la pestaña de *Item Properties* al lado derecho de la
ventana. En el espacio de *Main properties* escribimos el título y en
las opciones de *Appearance - Font* el tamaño y tipo de letra.

9\. Finalmente exportamos el mapa haciendo click en el menú de *Layout -
Export as Image* y seleccionando el formato y nombre de archivo que se
desee.

![](.//media/image10.png){width="6.5in" height="5.430555555555555in"}
