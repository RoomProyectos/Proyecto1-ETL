# Proyecto ETL - Grupo 1 #

	- Participantes: Sara, Gledson, Eva, Rubén, Luis Quezada
	- Temática: Noticias


## OBJETIVO DEL PROYECTO ##

Realización de un proceso ETL completo junto con la realización de visualizaciones sobre los datos y un pequeño storytelling.

## EXTRACCIÓN ##

Hemos elegido utilizar datos recopilados mediante webscrapping desde la página https://old.meneame.net

Obtendremos datos mediante Selenium, del año 2023 de la portada general de noticias.

La información a extaer de la página será la siguiente:

- Titular
- Entradilla
- Comunidad
- Dominio al que apunta el meneo
- Fechas envío y publicación
- Número de meneos (es la suma de los votos positivos y los votos anónimos)
- Número de clicks
- Votos positivos, anónimos y negativos
- Numero comentarios
- Usuario
- Karma (al momento de la publicación)

## TRANSFORMACIÓN ##

Se realizará el proceso de transformación con Pandas:
 - Corregir errores (tratamiento de np.nans) y se añadirá nueva información:

 - Columnas para añadir:
    - Hora envío (obtenida de fecha envío) - Tipo de dato: datetime
	- Hora publicación (obtenida de fecha publicación) - Tipo de dato: datetime
	- Delay (diferencia entre fecha envío y fecha publicación) - Tipo de dato: deltatime

    - Media karma (karma / número votos positivos + número votos negativos) - Tipo de dato: float

  	- Mes (en letras) - Tipo de dato: object
	- Trimestre (1er trimestre) - Tipo de dato: object
	
	- Día de la semana (en letras) - Tipo de dato: object
	- Franja horaria: mañana (>= 06 & < 12), mediodía (>=12 & <16), tarde (>=16 < 21), noche (>= 21 < 00), madrugada (>=00 &  < 06) - Tipo de dato: object

	- Municipio y provincia, donde haya esa información. Se proceserá el texto de titular y entradilla para obtener la ubicación desde una tabla auxiliar - Tipo de dato: object
	- Latitud - Tipo de dato: float
	- Longitud - Tipo de dato: float
	
## CARGA ##

Se realizará la carga de datos mediante la API de Airtable. La tabla a subir constará de los siguientes campos:

- Titular (string)
- Entradilla  (string)
- Comunidad  (category)
- Medio  (string)
- Fechas envío (datetime64)
- Fecha publicación  (datetime64)
- Número de meneos (int8)
- Número de clicks  (int8)
- Votos positivos (int8)
- Votos anónimos (int8)
- Votos negativos  (int8)
- Numero comentarios  (int8)
- Usuario  (string)
- karma (int8)
- Hora envío (datetime64)
- Hora publicación (datetime64)
- Delay (interval)
- Media karma (float)
- Mes (string)
- Trimestre (category)
- Día de la semana (category)
- Franja horaria (category)
- Municipio (string)
- Provincia (string)
- Latitud (float)
- Longitud (float)

## VISUALIZACIÓN DE DATOS ##

Se utilizará nuevamente la API de Airtable para la descarga de los datos y se realizarán distintas visualizaciones mediante Plotly y Folium.

General de todas las noticias en 3D (información contextual)
 - Fecha publicación
 - Comunidad 
 - Karma

Sobre los periodos en los que se publica
- Publicaciones por franja horaria
- Publicaciones por día de la semana
- Publicaciones por mes
- Publicaciones por trimestre

Sobre la distribución de los usuarios que envían
 - Treemap medio/usuario
 - Treemap comunidad/usuario

Sobre las comunidades y los medios

Sobre la relación entre meneos y clicks

Sobre el tiempo que le ha tomado en ser publicado
 - Delay
 - Día de la semana
 - Franja horaria

Sobre la interactividad 
 - Número de comentarios
 - Clicks
 - Votos
 - Karma
 - Por Comunidad

Nubes de palabras
 - Por medios más publicados 

Nube de palabras con los usuarios sobre el logo de meneame

Mapas con las localizaciones de los meneos

## Storytelling (Esta parte no será evaluada) ##

### Motivaciones del proyecto ###

Este proyecto surge del interés sociológico sobre las interacciones de usuarios en comunidades de internet. Para evaluarlo, hemos tomado como fuente de datos al agregador de noticias Menéame.

Se trata de un sitio web social en el que los usuarios realizan envíos (llamados meneos), pudiendo elegir tanto la categoría o comunidad (por ejemplo actualidad, política o ciencia, etc.), como el titular y la descripción del envío, además del enlace al que apunta la noticia, habitualmente de un periódico o medio, pero siendo posible también el envío de contenido escrito por el propio usuario o meneante que realiza el envío.

El resto de usuarios tiene la posibilidad de "menear" o votar positivamente la noticia, votarla negativamente y realizar comentarios. Los votos aumentan o disminuyen el llamado "karma" del meneo y, una vez alcanzada cierta cantidad y a través de unas fórmulas disponibles públicamente, éste es publicado en la portada de la comunidad a la que fue enviado o, si acumula suficiente karma, también en la portada principal de la página.

Nuestros objetivos generales son analizar las publicaciones, el tipo de contenido publicado, el nivel de interactividad de las publicaciones y conocer qué tipo de contenidos tienen más aceptación por parte de los usuarios.

### Alcance del proyecto ###

Analizaremos los datos de todos los meneos que han conseguido ser publicados en la página principal en el año 2023, con aproximadamente 15.000 registros. 

### Herramientas o tecnologías usadas. ### 

- Extracción por Webscrapping con Selenium y tratamiento con BeautifulSoup
- Transformación con Pandas
- Carga y descarga de datos mediante API de Airtable
- Visualizaciones con Plotly y Folium

### Un esquema de lo que fue el proyecto. ### 

### Resolución de cada desafío o problema. ### 

### Visualizaciones y resultados. ### 

### Desafíos en cada parte del proceso. ### 

###########################################################################
 # IDEAS #

 ¿Obtener amigos de los usuarios que más publican?
¿Antiguedad de los usuarios?

IDEA DE ESTADISTICA
Teorema de Bayes con noticias de diferentes categorías.
