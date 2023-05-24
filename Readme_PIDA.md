# <h1 align=center> **`PROYECTO INDIVIDUAL Nº2 - Accidentes aéreos`** </h1>

## **Breve descripción**
En este proyecto nos enfrentamos al desafío de analizar y comprender los accidentes aéreos, un evento trágico que involucra aeronaves y puede tener consecuencias devastadoras tanto para las personas como para las aeronaves en sí. A través de la recopilación y el análisis de datos relevantes, nuestro objetivo es obtener información valiosa que contribuya a mejorar la seguridad en la aviación civil. Este proyecto se lleva a cabo en colaboración con la Organización de Aviación Civil Internacional (OACI), una entidad intergubernamental comprometida con la promoción de la seguridad y eficiencia de la aviación a nivel mundial. Mediante el uso de técnicas de análisis de datos y visualización, buscamos identificar patrones, tendencias y factores contribuyentes que nos permitan tomar medidas preventivas y reducir la incidencia de accidentes aéreos.


## **Contexto**

En este proyecto, asumimos el rol de un Data Analyst que trabaja para la Organización de Aviación Civil Internacional (OACI). La OACI nos ha asignado la tarea de realizar un análisis de accidentes aéreos con el objetivo de mejorar la seguridad de la aviación civil. Los accidentes aéreos son eventos indeseados que pueden resultar en pérdidas humanas y daños a las aeronaves. Pueden ser causados por diversos factores, como errores humanos, problemas de equipo, condiciones meteorológicas adversas y fallas en la gestión del tráfico aéreo.

Nuestro trabajo consiste en recopilar y analizar datos históricos de accidentes aéreos, utilizando diversas fuentes de datos, como bases de datos gubernamentales, informes de la industria y medios de comunicación. A través de técnicas de data analytics, buscamos identificar patrones, tendencias y factores contribuyentes que puedan ayudar a mejorar la seguridad en la aviación civil.

Para lograr esto, realizaremos un análisis exploratorio de los datos, donde examinaremos estadísticas descriptivas, realizaremos análisis univariados y bivariados, y buscaremos patrones y anomalías en los datos. Con base en estos hallazgos, crearemos un dashboard interactivo que permita a los usuarios explorar los datos y obtener información sobre accidentes aéreos específicos.

## **Propuesta de trabajo**
Para este proyecto, se realizaron las siguientes actividades:

## **Transformaciones** [link](xxxxxxxxxxxxxxxxxxxxxxx)
Se realizaron las siguientes transformaciones a los datos:
+ Se cambió el tipo de dato de la columna 'fecha' a formato de fecha y hora.
+ Se aplicaron varias funciones para limpiar y formatear la columna 'HORA declarada', eliminando prefijos, sufijos y caracteres no deseados, y convirtiendo los valores a formato de hora.
+ Se etiquetaron los valores '?' en la columna 'Ruta', 'OperadOR', 'flight_no', 'route', 'ac_type', 'registration', 'cn_ln' y 'summary' como 'NaN'.
+ Se cambió el tipo de dato de las columnas 'all_aboard', 'PASAJEROS A BORDO', 'crew_aboard', 'cantidad de fallecidos', 'passenger_fatalities', 'crew_fatalities' y 'ground' a entero, manejando los valores no numéricos.
+ Se exportó el conjunto de datos transformado a un archivo CSV llamado 'accidentes_etl.csv' para su posterior análisis exploratorio de datos (EDA).

Estas transformaciones tienen como objetivo preparar los datos para su análisis, asegurando la consistencia y el formato adecuado de las variables, y facilitando la identificación de patrones y tendencias en el conjunto de datos.

Cabe mencionar que el archivo adjunto en el link proporcionado contiene comentarios que explica cada sección y actividad realizada paso a paso.

## **Análisis exploratorio de los datos** [link](xxxxxxxxxxxxxxxxxxxxxxxx)
Se realizon las siguientes actividades:
+ Importación de librerías: Se importan las librerías necesarias para el análisis de datos, incluyendo pandas, numpy, datetime, missingno, seaborn y matplotlib.pyplot.
+ Carga de datos: Se carga el archivo 'accidentes_etl.csv' en un DataFrame llamado 'df'.
+ Análisis de los datos:
    - a) Diccionario de datos: Se muestra el diccionario de datos que describe el significado de cada columna en el DataFrame.
    - b) Colecta y validación de datos:
        - Tipo de dato de las variables: Se muestra el tipo de dato de cada columna en el DataFrame.
        - Cantidad de variables, según cada tipo de dato: Se cuenta la cantidad de variables por cada tipo de dato.
        - Cantidad de variables y observaciones: Se muestra la cantidad de variables y observaciones en el DataFrame.
        - Cantidad de observaciones con valores nulos por variable: Se calcula la cantidad de valores nulos en cada columna.
        - Cantidad de valores nulos en total: Se calcula la cantidad total de valores nulos en el DataFrame.
        - Proporción de valores nulos por cada variable: Se muestra la proporción de valores nulos en cada columna mediante un histograma.
        - Visualizar los valores nulos en todo el conjunto de datos: Se muestra una matriz de calor que resalta los valores nulos en el DataFrame.
        - Visualizamos la correlación de nulidad entre las variables: Se muestra un mapa de calor que visualiza la correlación de nulidad entre las variables del DataFrame.
        - Eliminamos los valores nulos: Se eliminan las columnas 'Unnamed: 0' y 'flight_no' del DataFrame debido a su alto porcentaje de valores nulos.
        - Cantidad de filas duplicadas: Se cuenta la cantidad de filas duplicadas en el DataFrame.
        - Joineando dataset: Se cargan dos tablas adicionales ('ac_type_clasificacion.csv' y 'Ruta_lon_lat_pais_cont.csv') y se unen con el DataFrame original ('df') utilizando las columnas 'ac_type' y 'Ruta' respectivamente.
    - c) Análisis general:
        - Análisis univariado de variables numéricas: Se muestra un histograma y un diagrama de caja para cada variable numérica en el DataFrame.
        - Análisis univariado de variables categóricas: Se muestra un gráfico de barras para cada variable categórica en el DataFrame.
        - Visualización de palabras clave en la columna 'summary': Se muestra una nube de palabras que representa las palabras más frecuentes en la columna 'summary'.
        - Análisis bivariado: Se muestra una matriz de dispersión para las variables numéricas relevantes y un gráfico de barras comparando la cantidad de fallecidos por ruta (solo para las 10 rutas principales).

Cabe mencionar que el archivo adjunto en el link proporcionado contiene comentarios que explica cada sección y actividad realizada paso a paso.

## **Streamlit** [link](hxxxxxxxxxxxxxxxxx)
+ **Visualizaciones:** [link](hxxxxxxxxxxxxxxxxx)
        Los cambios desarrollados son los siguientes:

        - Se importaron las bibliotecas necesarias: pandas, numpy, datetime, missingno, seaborn, matplotlib.pyplot, folium y streamlit_folium.
        - Se cargó el DataFrame desde el archivo "accidentes_data.csv".
        - Se añadió una sección para mostrar los datos del DataFrame. Se implementó una interfaz en Streamlit con botones para mostrar el encabezado, una muestra, la cola y la totalidad de los datos.
        -Se realizó un análisis de la cantidad de accidentes por año. Se convirtió la columna "fecha" al formato de fecha, se crearon las columnas "fecha_año" y "fecha_mes" y se filtraron los datos según el rango de años seleccionado por el usuario. Luego, se mostró un gráfico de línea con la cantidad de accidentes por año, resaltando los tres años con mayor cantidad de accidentes.
        - Se realizó un análisis de la cantidad de accidentes vs. muertos. Se creó una tabla dinámica con los datos filtrados y se mostró un gráfico de líneas con las cantidades de accidentes y muertos por año.
        - Se realizó un análisis de la cantidad de accidentes por mes y tipo de aeronave. Se filtraron los datos por la clasificación de aeronaves y se creó un gráfico de barras apiladas para mostrar la cantidad de accidentes por mes y tipo de aeronave.
        - Se realizó un análisis de la cantidad de accidentes por mes y continente. Se filtraron los datos por continente y se creó un gráfico de barras apiladas para mostrar la cantidad de accidentes por mes y continente.
        - Se implementó una función para mostrar los accidentes registrados en un mapa. Se obtuvo la cantidad de accidentes por país y se creó un mapa de folium con marcadores proporcionales a la cantidad de accidentes por país.

    Estos cambios permiten visualizar y analizar diferentes aspectos de los datos de accidentes de forma interactiva en la aplicación Streamlit.

+ **KPI's:** [link](hxxxxxxxxxxxxxxxxx)
        Se realizaron los siguientes cambios y actividades en el código:

        - Se importó la biblioteca Streamlit para crear una aplicación web interactiva.
        - Se importó la biblioteca pandas para el manejo de datos y matplotlib.pyplot para la generación de gráficos.
        - Se utilizó la función st.markdown() para mostrar encabezados y separadores en formato Markdown.
        - Se cargaron los datos del archivo "accidentes_data.csv" y se convirtió la columna "fecha" al tipo de dato fecha.
        - Se agregó un control deslizante interactivo para seleccionar un rango de años.
        - Se filtró el DataFrame original según el rango de años seleccionado.
        - Se calculó el resumen anual de accidentes, cantidad de fallecidos, tasa de mortalidad, variación de la tasa de mortalidad, índice de supervivencia y promedio de fallecidos por accidente utilizando el DataFrame filtrado.
        - Se crearon gráficos utilizando los datos resumidos para cada KPI (Promedio de Fallecidos, Índice de Supervivencia, Índice de mortalidad total, Reducción porcentual del índice de mortalidad).
        - Se utilizó st.pyplot() para mostrar los gráficos generados en la aplicación web.

    Estos cambios permiten visualizar los KPIs de manera interactiva y presentar los resultados de forma más atractiva.


## **Conclusión**
El motivo de realizar los KPIs (indicadores clave de rendimiento) es analizar y evaluar el desempeño de una determinada métrica o aspecto en un conjunto de datos. Los KPIs proporcionan una medida cuantitativa que permite medir y monitorear el progreso hacia los objetivos establecidos.

En el contexto del código proporcionado, los KPIs se utilizan para analizar el rendimiento de los accidentes aéreos en función de varios indicadores, como el promedio de fallecidos, el índice de supervivencia, el índice de mortalidad total y la reducción porcentual del índice de mortalidad. Estos indicadores brindan información importante sobre la seguridad y las consecuencias de los accidentes aéreos, y permiten evaluar si se están logrando mejoras en la prevención de accidentes y en la seguridad de los vuelos.
