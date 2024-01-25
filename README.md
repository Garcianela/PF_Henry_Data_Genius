<h1 align="center">Proyecto Final</h1>

<h2 align="center">Data Science</h2>

<p align="center">
  <img src="src/data.jpg" alt="logo" width="200">
</p>

## YELP & GOOGLE MAPS - REVIEWS AND RECOMMENDATIONS

  Somos una empresa especializada en análisis de datos, con un equipo altamente calificado que abarca desde Data Analysts hasta Machine Learning Engineers. Nuestra misión es desentrañar la valiosa información contenida en los comentarios de plataformas como Yelp y Google, para brindar a las empresas de construcción una visión profunda de su desempeño y las oportunidades de expansión que pueden aprovechar. Nuestro compromiso es proporcionar a nuestros clientes las herramientas necesarias para tomar decisiones fundamentadas y mejorar sus operaciones en un mercado altamente competitivo.

## Índice

1. [Introducción](#introducción)
2. [Contexto & Problemática](#contexto--problemática)
3. [Objetivos](#objetivos)
4. [Indicadores de Gestión (KPIs)](#indicadores-de-gestión-kpis)
5. [Data](#data)
6. [ETL (Extract, Transform, Load)](#etl-extract-transform-load)
7. [EDA (Exploratory Data Analysis)](#eda-exploratory-data-analysis)
8. [Dashboard](#dashboard)
9. [Sistema de Recomendación](#sistema-recomendación)
10. [Stack Tecnológico & Flujo de Trabajo](#stack-tecnológico--flujo-de-trabajo)
11. [Diccionario de Datos](#diccionario-de-datos)
12. [Metodología SCRUM](#metodología-scrum)
13. [Conclusiones](#conclusiones)
14. [Miembros](#miembros)

## Introducción

<p align="justify">

  La arquitectura en Estados Unidos no solo refleja la evolución de la sociedad y los valores nacionales, sino que desempeña un papel fundamental en la economía del país. Las empresas constructoras en Estados Unidos son piezas clave en la creación y preservación del patrimonio arquitectónico de la nación, aportando de manera significativa al desarrollo y la modernización del país.

  En Estados Unidos subrayan la importancia esencial de las empresas constructoras en la materialización de una amplia gama de proyectos, desde la restauración de edificios históricos hasta la construcción de rascacielos contemporáneos. Este papel fundamental de las contratistas no solo incide en la construcción, sino también en la configuración del carácter distintivo de Estados Unidos.

  En este proyecto, exploraremos este emocionante viaje donde la opinión de los usuarios se convierte en un recurso inestimable para las empresas. Nos enfocaremos en la importancia de una gestión efectiva de reseñas en plataformas como Yelp y Google, especialmente en el contexto de una empresa como Construction Valdes, que enfrenta desafíos notables en su desempeño comercial. Analizaremos cómo estas reseñas pueden ser un componente clave en la resolución de los desafíos actuales de la empresa.

  Finalmente, hemos optado por utilizar Google Cloud y BigQuery debido a su capacidad de escalabilidad flexible, lo que se adapta a las necesidades, independientemente del tamaño de los conjuntos de datos que se manejen. Esta flexibilidad para ajustar los recursos no solo mejora la eficiencia, sino que también permite un crecimiento sin complicaciones. Ambas plataformas ofrecen un equilibrio excepcional entre rendimiento, escalabilidad, seguridad y facilidad de uso, lo que las hace sumamente valiosas para una amplia variedad de aplicaciones empresariales y proyectos de análisis de datos.
</p>


## Contexto & Problemática

<p align="justify">
  En la era digital actual, las opiniones de usuarios en plataformas como Yelp y Google son cruciales para las empresas. Estas reseñas influyen en las decisiones de compra y estrategias comerciales. Sin embargo, gestionar y analizar esta información valiosa puede ser un desafío, pero es esencial para comprender la percepción de los clientes y mejorar el rendimiento empresarial.

  En el caso específico de Construction Valdes, la situación se complica aún más. La empresa ha experimentado una disminución significativa en las ventas, lo que sugiere que hay problemas más profundos en su desempeño comercial. Este declive en los resultados económicos es una preocupación importante y podría estar relacionado con la percepción negativa de los clientes, lo que hace que la gestión efectiva de las reseñas y la mejora de la imagen de la empresa sean aún más cruciales.

<p align="center">
  <img src="src/cambio.jpg" width="300" height="200">
  <img src="src/pronostico.jpg" width="300" height="200">
  <img src="src/pronostico_futuro.jpg" width="300" height="200">
</p>

  En resumen, la gestión de las reseñas de los usuarios en plataformas como Yelp y Google se ha vuelto vital para las empresas en la actualidad, y Construction Valdes enfrenta desafíos adicionales en su intento de revertir la disminución de ventas y contrataciones. El análisis de estas opiniones y su aplicación efectiva en la toma de decisiones comerciales se presenta como un componente clave en la resolución de la problemática actual de la empresa.
</p>

## Objetivos de Proyecto

### Objetivo General:

- Realizar una evaluación exhaustiva del sector de contratistas en todo Estados Unidos con el propósito de identificar oportunidades de mejora para el negocio Construction Valdes y analizar posibles estrategias de expansión a largo plazo.

### Objetivo Específicos: 

- Objetivo 1: 
     
    Llevar a cabo un análisis de mercado en beneficio de Construction Valdes, con el fin de identificar tendencias o patrones significativos.

- Objetivo 2: 

    Analizar el rendimiento actual de Construction Valdes y desarrollar estrategias destinadas a mejorar la interacción y desempeño con los clientes.

## KPIs

- **Satisfacción al Cliente:**
  - *Métrica:* Cantidad de reseñas positivas
  - *Meta:* Aumentar el 10% de reseñas positivas en el 2023.

- **Gestión de Construcciones Valdez a nivel estatal:**
  - *Métrica:* Cantidad anual de reseñas positivas de Construction Valdez / Cantidad anual de reseñas totales del mercado Estatal
  - *Meta:* Aumento de 10% anual en comparación con la actividad estatal.

- **Gestión de Construcciones Valdez a nivel nacional:**
  - *Métrica:* Cantidad anual de reseñas positivas de Construction Valdez / Cantidad anual de reseñas totales del mercado Nacional
  - *Meta:* Aumento del 10% en comparación con la actividad anual nacional

- **Cumplimiento de proyectos:**
  - *Métrica:* Número de reseñas con 5 estrellas de Construction Valdes / Número total de puntaje (campo estrellas)
  - *Meta:* Aumento del 5% en un año para Construction Valdes.


## Data

  Los datos crudos se extrajeron de la carpeta de Google Drive proporcionada por Henry, concretamente de fuentes como Google Maps y Yelp. Estos datos se presentan en formatos que incluyen JSON, Parquet y Pickle.

  En particular, se enfocó en la selección de negocios relacionados con el sector de la construcción (conocidos en Estados Unidos como contratistas). A partir de estos datos, se llevaron a cabo procesos de transformación (ETL) y exploración de datos (EDA) con el propósito de crear nuevos conjuntos de datos que estuvieran limpios, transformados y normalizados, listos para ser cargados en una base de datos.

## ETL (Extract, Transform, Load):

### Google Maps:

Los datos de Google Maps se encontraban en dos carpetas en formato JSON y fueron sometidos al siguiente proceso de tratamiento de datos:

- **medata-sitios:**
  - Se leyeron todos los archivos JSON contenidos en esta carpeta y se convirtieron en un dataframe. Este dataset contiene información detallada sobre lugares y negocios registrados en Google Maps.
  - Se creó una lista de categorías relacionadas con la línea de construcción (contratistas), empleada para filtrar los demás archivos.

- **reviews-estados:**
  - Los archivos JSON se leyeron por estados y se convirtieron en un dataframe. Este proceso se realizó para cada estado.
  - Los datasets creados contienen información sobre reseñas y acciones de usuarios en Google Maps por cada estado.
  - De acuerdo a la lista previamente creada con el archivo de medata-sitio (lista que contempla las categorías en el área de construcción), se aplicó una máscara al dataset de cada estado para contar solo con la línea seleccionada.
  - Se creó una columna en cada dataset con el estado correspondiente.
  - Los dataframes de cada estado se concatenaron para contar con la información completa de todos los estados.
  - El nuevo dataframe de todos los estados se fusionó con el dataframe reviews-sitios a través de la columna gmap_id.
    
[Enlace a notebook](https://drive.google.com/drive/folders/1a7djToO058NtHjPVHixx8YmJpIUlK_VP)

### Yelp:

- **Checkin.json:**
  - Se leyó dicho archivo JSON y posteriormente se transformó en dataframe en formato .csv. Este contiene información de la registración del negocio en la plataforma Yelp. No fue empleado en el dataframe del proyecto.

- **tip.csv:**
  - Contiene información de comentarios extras que los usuarios hacen del negocio, no fue empleado en el dataframe del proyecto, ya que no proporciona información adicional necesaria para el análisis.

- **user-001.parquet:**
  - Este archivo se leyó a partir del archivo parquet y posteriormente se transformó en dataframe. De este dataframe se eliminaron las columnas irrelevantes para el análisis, ya que podían prestarse para confusión. Solo cuenta con las columnas: 'user_id', 'user_name' y 'average_stars', y finalmente se transformó en formato CSV.

- **review.json:**
  - El archivo de lectura se dividió en 14 archivos CSV con el propósito de optimizar el rendimiento computacional. Una vez convertidos al formato CSV, los archivos fueron fusionados. Luego, se eliminaron las columnas que no eran relevantes para el análisis, específicamente "useful," "funny" y "cool."

- **business.pkl:**
  - Se leyó el archivo en formato "pickle" de Python y se creó un DataFrame. Se eliminaron 14 columnas que contenían un 90% de datos faltantes para mejorar la calidad del DataFrame.
  - Se corrigió la columna estado, ya que contaba con el estado abreviado.
  - A partir del archivo review.csv, se creó una máscara de las categorías que contiene las categorías de contratista (línea seleccionada). Dicha máscara se aplicó al business.csv.

- Luego de aplicar el tratamiento mencionado, se procedió a concatenar los archivos de review y business en un nuevo archivo CSV, que fue renombrado como "review.csv."

- Se unen los DataFrames review y user, formando un nuevo dataframe llamado yelp.csv.

- Se acondicionaron las columnas de google_maps.csv con el objetivo de unificar criterios respecto al yelp.csv.

- Finalmente, se unen yelp.csv y google_maps.csv mediante la columna gmap_id, generando un nuevo dataframe llamado df_google_yelp en formato CSV. Esta base de datos estática será empleada para alimentar nuestro Google Cloud.

Enlace a notebook [aquí]:(https://drive.google.com/drive/folders/1xJbhJBgdrO2sS8kIYTRATLZvdRHSikmK?usp=drive_link)

## EDA (Exploratory Data Analysis):

<p align="center">
  <img src="src/analisis_sentimientos.jpg" width="300" height="200">
  <img src="src/analisis_sentimientos_anio.jpg" width="300" height="200">
  <img src="src/Ciudades_Negocios.jpg" width="300" height="200">
</p>

<p align="center">
  <img src="src/estados_mas_negocios.jpg" width="300" height="200">
  <img src="src/Distribución_geoespacial_fresno.jpg" width="300" height="200">
  <img src="src/correlación_variables.jpg" width="300" height="200">
</p>

<p align="center">
  <img src="src/Nube_Alta_Calificación.jpg" width="300" height="200">
  <img src="src/Nube_palabras_baja_calificación.jpg" width="300" height="200">
  <img src="src/Calificacion_negocio.jpg" width="300" height="200">
</p>

<p align="center">
  <img src="src/top10_categoria_mas_reseñas.jpg" width="300" height="200">
</p>

[Enlace a notebook](https://drive.google.com/drive/folders/1a7djToO058NtHjPVHixx8YmJpIUlK_VP)


## Stack Tecnológico & Flujo de Trabajo

<p align="center">
  <img src="src/Stack_Tecnológico.jpg" alt="fujo_trabajo">
</p>

## Dashboard: 

Puedes acceder a nuestro dashboard [aquí](https://app.powerbi.com/view?r=eyJrIjoiZjMyNmIwMzgtOWQ3Ni00MzZhLTkxZTktYjY4NGNiZDQ5NmVjIiwidCI6IjU3Y2NiNDViLTY2OWQtNDM2OC1hMmYyLTBhZTdhNGRkMmUzOSIsImMiOjR9&disablecdnExpiration=1699604191).

Acceso a los recursos desde la página web [aquí](https://datagenius.my.canva.site/about)
Password: 568910

  En la era digital actual, la toma de decisiones informada y estratégica es esencial para el éxito de cualquier proyecto o empresa. En este contexto, las dashboards se han convertido en herramientas indispensables que ofrecen una visión integral y en tiempo real de los datos clave que impulsan las operaciones y el rendimiento organizacional. Estas interfaces visuales no solo simplifican la complejidad de la información, sino que también empoderan a los equipos directivos con la capacidad de identificar patrones, evaluar tendencias y, en última instancia, tomar decisiones más acertadas.

### Estructura del Dashboard

  Veamos la estructura del dashboard. La primera sección consta de dos segmentadores: uno para categorías y otro para fechas.

  En esta sección, se muestran los indicadores clave de rendimiento (KPI) de la empresa. El primer KPI presenta el estado general de la empresa, proporcionando una instantánea concisa de su salud operativa. El segundo KPI destaca la satisfacción del cliente, un aspecto crucial para el éxito a largo plazo. Finalmente, el tercer KPI ofrece información detallada sobre la gestión de la empresa, brindando a los responsables decisiones una comprensión profunda de los procesos internos. Estos KPIs no solo simplifican la complejidad de los datos, sino que también sirven como faros que guían la toma de decisiones estratégicas, permitiendo a los líderes dirigir sus esfuerzos hacia áreas específicas que requieren atención y mejora continua. En conjunto, esta estructura de dashboard se posiciona como un recurso invaluable para desbloquear el potencial máximo de una empresa al proporcionar información significativa y accionable.

<p align="center">
  <img src="src/Dashboard.jpg" alt="dashboard">
</p>


## Sistemas de Recomendación

  En el fascinante mundo de los sistemas de recomendación, la etapa inicial desencadena un proceso crucial: la recopilación de datos esenciales para la formulación de recomendaciones perspicaces. Este primer paso implica la adquisición de información detallada sobre usuarios, negocios y las interacciones entre ambos. En esta fase crucial, la depuración meticulosa de los datos se convierte en la piedra angular para identificar y seleccionar los negocios que destacarán en la experiencia de recomendación. Para lograr este objetivo, se consideran diversas características que actúan como criterios de evaluación fundamentales.

### Características Clave para la Selección de Negocios:

- **Alto Consumo:** La propensión de los negocios a un alto consumo de productos o servicios sugiere popularidad y una experiencia positiva para los usuarios.

- **Alto Ingreso Per Cápita:** La ubicación en áreas con un alto ingreso per cápita señala la capacidad de atraer a clientes con mayor poder adquisitivo.

- **Bajo Volumen de Negocios:** La baja rotación de negocios indica menos competencia y la posibilidad de ofrecer una experiencia más personalizada.

- **Alta Calificación de Estrellas:** Los negocios con altas calificaciones de estrellas sugieren la prestación de servicios de calidad y productos que cumplen con las expectativas.

- **Cantidad de Reseñas Alta:** La presencia de un elevado número de reseñas indica confiabilidad y una experiencia positiva respaldada por la comunidad de usuarios.

### Modelo LSH (Local Sensitive Hashing):

  En la siguiente fase, el proceso avanza hacia la implementación de un algoritmo LSH. Este algoritmo transforma los datos en un espacio de características, facilitando una comparación más eficiente entre usuarios y negocios en el vasto conjunto de datos.

### Recomendación:

  Finalmente, se llega al emocionante momento de la recomendación, donde los resultados del sistema se presentan a los usuarios, ofreciendo sugerencias personalizadas que optimizan la experiencia de cada individuo. En este punto, la sinergia entre la recopilación de datos, el modelo LSH y el proceso de recomendación culmina en la entrega de sugerencias relevantes y valiosas para cada usuario.

**API de Recomendación:**

<p align="center">
  <img src="src/API.jpg" alt="API Screenshot 1" width="50%">
  <img src="src/API_1.jpg" alt="API Screenshot 2" width="50%">
</p>


Explora la documentación de la API [aquí](https://final-project-henry-rs-contractors.onrender.com/docs).

Accede a los recursos desde la página web [aquí](https://datagenius.my.canva.site/about)
Password: 568910

## Diccionario de Datos

<div align="center">
  
| Nombre Columna     | Tipo de Dato | Descripción                                                        |
|--------------------|--------------|-------------------------------------------------------------------|
| index              | (int)        | Contador a partir del 0 incrementándose uno a uno según los registros |
| business_id        | (str)        | Identificador único de cada negocio, formado por números y letras |
| business_name      | (str)        | Nombre del negocio                                                |
| city               | (str)        | Ciudad donde se ubica el negocio                                   |
| state              | (str)        | Estado donde se emplaza el negocio                                 |
| latitude           | (float)      | Latitud                                                           |
| longitude          | (float)      | Longitud                                                          |
| stars_business     | (float)      | Puntaje del negocio en promedio, que varía del 1.00 al 5.00      |
| review_count       | (int)        | Cantidad de vistas que tiene el negocio por parte de usuarios   |
| attributes         | (str)        | Servicios extras que ofrece el negocio                            |
| categories         | (str)        | Rubro general de cada negocio                                     |
| biz_category1      | (bool)       | Categoría 'Exterior Remodeling or Construction' - Pertenece o no (true or false) |
| biz_category2      | (bool)       | Categoría 'Interior Remodeling' - Pertenece o no (true or false)  |
| biz_category3      | (bool)       | Categoría 'Masonry & Concrete Services' - Pertenece o no (true or false) |
| biz_category4      | (bool)       | Categoría 'Cleaning Services' - Pertenece o no (true or false)   |
| biz_category5      | (bool)       | Categoría 'HVAC & Air Quality' - Pertenece o no (true or false)   |
| biz_category6      | (bool)       | Categoría 'Roofing & Insulation' - Pertenece o no (true or false) |
| biz_category7      | (bool)       | Categoría 'Appliance Repair & Installation' - Pertenece o no (true or false) |
| biz_category8      | (bool)       | Categoría 'Plumbing Services' - Pertenece o no (true or false)   |
| biz_category9      | (bool)       | Categoría 'Landscape & Garden Services' - Pertenece o no (true or false) |
| biz_category10     | (bool)       | Categoría 'Furniture Services' - Pertenece o no (true or false) |
| biz_category11     | (bool)       | Categoría 'Electrical Services' - Pertenece o no (true or false) |
| biz_category12     | (bool)       | Categoría 'Home Inspection & Real Estate' - Pertenece o no (true or false) |
| biz_category13     | (bool)       | Categoría 'Handyman or Others' - Pertenece o no (true or false) |
| user_id            | (str)        | Identificador único de cada usuario, formado por números y letras |
| stars_by_user      | (float)      | Puntaje que el usuario otorga al negocio                          |
| review_date        | (date)       | Fecha en la que se realizó la vista del usuario al negocio       |
| extract_date       | (date)       | Fecha en la que se extrajeron los datos estáticos                |
| Zip code           | (str)        | Código postal del estado                                         |
| Id                 | (str)        | Identificador único de registro                                  |
| State_Name         | (str)        | Nombre del estado                                                |
| City               | (str)        | Nombre de la ciudad                                              |
| Lat                | (float)      | Latitud                                                          |
| Lon                | (float)      | Longitud                                                         |
| Mean               | (int)        | Valor medio de ingresos                                         |
| Median             | (Int)        | Mediana de ingresos                                              |
| Stdev              | (float)      | Desviación estándar de ingresos                                  |
| Sum_w              | (Int)        | Valor de ingresos                                                |
| Total_income       | (float)      | PIB aproximado                                                   |
| Income_range       | (float)      | Rangos de acuerdo a los ingresos                                 |
</div>

## Metodología SCRUM

### Equipo SCRUM:
- **Product Owner:** 
  - Es el interesado en el producto final. Fue el encargado de establecer las necesidades del producto.

- **Scrum Master:** Andrés Laurizi
  - Cuida el proyecto para que cumpla con los requerimientos del Product Owner. Tiene experiencia laboral previa en el ámbito del Data Analytics, así aconseja al equipo.

- **Desarrolladores:** Adrián Silva, Marianela García, Cecilia Gómez, Juan Camilo Grisales, Germán Robles

### Sprints:
- Total del proyecto: 3 semanas.
- Total de sprints: 3 sprints, 1 por semana.
- Cada semana se entrega un grupo de hitos para mostrar el avance del proyecto.
- Daily Meeting: Reunión diaria Desarrolladores + Scrum Master, 30 minutos.
- Revisión Sprint: Viernes, 30 minutos.

### Increment:
- Registro semanal de las actividades realizadas, incrementa gradualmente hasta completar el proyecto.

### Revisión Sprint:
- Product owner revisa los incrementos, logros alcanzados y faltantes.

### Burndown chart:
- Manejo de Diagrama de Gantt para organizar actividades y rastrear avance.

### Principios SCRUM:
- Transparencia
- Inspección
- Adaptación

### Flexibilidad SCRUM:
- Iterativo (sprints) e incremental
- Priorización dinámica
- Reuniones y eventos flexibles
- Auto-organización del equipo

## Conclusiones

Los productos que entregaremos a Construction Valdes son:

- Dashboard Interactivo con las siguientes visualizaciones:
  - Análisis de tendencias para identificar actividades de contratistas y construcción con más movimiento. 
  - Análisis de tendencias para identificar atributos que son importantes para los clientes. 
  - Análisis geográfico para identificar posibles zonas de inversión en todo Estados Unidos.  
  - Visualización de los Key Performance Indicators (KPIs)
- Sistema de recomendación para zonas futuras de inversión basados en actividades de contratistas y construcción (por ejemplo, Exteriores, Remodelación de Interiores, etc)
- Plan de acción para aumentar las ventas en base al análisis del mercado estadounidense.

## Miembros del equipo

- *Data Analyst / Documentation Manager:* Esta persona tendrá un doble rol. Por un lado, se encargará de analizar los datos, lo que implica recopilar, limpiar y analizar la información para extraer conocimientos y generar informes. Por otro lado, también será el encargado de gestionar la documentación relacionada con el proyecto, como la creación y organización de documentos, informes y registros.

- *Data Analyst:* Este rol estará centrado exclusivamente en el análisis de datos. La persona asignada será responsable de recopilar, limpiar, analizar y presentar los datos de manera efectiva para tomar decisiones informadas.

- *Data Engineer / Machine Learning Engineer:* Esta persona tendrá un rol combinado. Por un lado, se encargará de la ingeniería de datos, lo que implica la preparación y organización de los datos para su análisis. Por otro lado, también estará involucrada en el desarrollo de soluciones de aprendizaje automático si es necesario en el proyecto. Esto incluye la construcción de modelos de machine learning y su implementación.

<p align="center">
  <img src="src/organigrama.jpg" alt="organigrama">
</p>
 
