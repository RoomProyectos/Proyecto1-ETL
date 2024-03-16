############################################################################
########             Proyecto ETL - Grupo 1                         ########
########   Participantes: Sara, Gledson, Eva, Rubén, Luis Quezada   ########
########                                                            ########
########                   Temática: Noticias                       ########
############################################################################

## OBJETIVO DEL PROYECTO ##

Realizar un proceso ETL, junto con la realización de visualizaciones sobre los datos y un pequeño storytelling.

## EXTRACCIÓN ##

Hemos elegido utilizar datos recopilados mediante webscrapping desde la página https://old.meneame.net

Obtendremos datos mediante Selenium, ¿del último año? de las categorías X, Y, Z.

La información a extaer de la página será la siguiente:

Titular
Entradilla
Categoría/Comunidad
Dominio al que apunta la noticia
Fechas envío y publicación
Número de meneos (es la suma de los votos positivos y los votos anónimos)
Número de clicks
Votos positivos, anónimos y negativos
Numero comentarios
¿usuario?
¿karma (al momento de la publicación)?
¿Tipo de envío(fotos, vídeo, texto)?

## TRANSFORMACIÓN ##

Se realizará el proceso de transformación con Pandas, donde se corregirán los errores y se añadirá nueva información (tiempo desde envío hasta publicacion, media karma por cada voto, relación positivos y negativos, etc. )

Si una de las categorías es Sucesos, podemos intentar extraer la localización de los meneos para cruzarlo con datos geolocalizados y poder realizar también una visualización de folium.

## CARGA ##

Se realizará la carga de datos mediante la API  de Airtable

## VISUALIZACIÓN DE DATOS ##

Se utilizará nuevamente la API de Airtable para la descarga de los datos y realización de distintas visualizaciones:

- Sobre los periodos del año en los que se publica
- Sobre los momentos del día en los que se publica
- ¿Sobre la distribución de los usuarios que envían?
- ¿Sobre la tipología del meneo?
- Sobre la relación entre meneos (o votos) y clicks
- Sobre el tiempo que le ha tomado en ser publicado
- Sobre el númeo de comentarios
- ¿Sobre la relación del karma con otras variables como comentarios o número de clicks?

## Storytelling (Esta parte no será evaluada) ##

De este mismo documento se puede extraer parte de la información; dejo aquí los puntos que nos sugieren:

Motivaciones del proyecto.
Alcance del proyecto.
Herramientas o tecnologías usadas.
Desafíos en cada parte del proceso.
Resolución de cada desafío o problema.
Un esquema de lo que fue el proyecto.
Visualizaciones y resultados.


###########################################################################################################################################


Datos a extraer

- 
