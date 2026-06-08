
# Trabajo Práctico Integrador - Urban Flow

## Sprint 3

## Objetivo

El objetivo del Sprint 3 fue profesionalizar el tratamiento de los datos del sistema de multas de tránsito, migrando desde un enfoque basado únicamente en archivos CSV hacia una solución que integra bases de datos relacionales y vectoriales.

A partir de los datos procesados en los sprints anteriores, se buscó modelar la información mediante objetos, persistirla en una base de datos estructurada, realizar consultas analíticas y aplicar búsqueda visual por similitud utilizando embeddings de imágenes.

## Contexto del trabajo

En los sprints anteriores se trabajó con datos históricos de multas por exceso de velocidad y con imágenes asociadas a las infracciones. En el Sprint 1 se realizó la limpieza y preparación inicial de los datos. En el Sprint 2 se incorporó el procesamiento de imágenes para determinar qué multas contaban con evidencia visual válida.

En este Sprint 3, el sistema se amplió incorporando persistencia mediante SQLAlchemy, una base de datos relacional y una base vectorial con ChromaDB y OpenCLIP. Esto permitió vincular información administrativa de multas con representaciones vectoriales de imágenes.

## Desarrollo realizado

Durante el trabajo se diseñó un modelo lógico compuesto por cuatro entidades principales:

- Vehículo
- Multa
- Radar
- Evidencia

Luego, ese modelo conceptual fue representado mediante clases de Python y posteriormente transformado en un modelo relacional utilizando SQLAlchemy. Cada entidad fue modelada con su clave primaria, atributos principales, relaciones entre tablas y métodos `__repr__` para mejorar la legibilidad.

Se creó una base de datos llamada `transito`, donde se migraron los datos provenientes del archivo:

`urban_flow/data/processed/speeding_fines_image.csv`

La migración permitió cargar vehículos, radares, multas y evidencias asociadas. Luego se validó la cantidad de registros insertados, comprobando la consistencia entre el archivo CSV y la base de datos.

## Consultas realizadas

Sobre la base relacional se implementaron consultas para responder preguntas relevantes del dominio del problema, entre ellas:

- Las 10 patentes con mayor cantidad de multas.
- Las multas sin evidencia asociada.
- Los radares con mayor volumen de infracciones.
- Las patentes reincidentes dentro de un período determinado.
- El porcentaje de multas confirmadas visualmente.

Estas consultas permitieron obtener indicadores útiles para analizar el comportamiento de los vehículos, la actividad de los radares y la disponibilidad de evidencia visual.

## Base de datos vectorial

Además de la base relacional, se creó una base de datos vectorial llamada `patente_vectorial` utilizando ChromaDB. Para generar los vectores de las imágenes se utilizó el modelo OpenCLIP.

Cada imagen fue transformada en un embedding, es decir, una representación numérica que permite comparar imágenes por similitud. Junto con cada vector se almacenaron metadatos como patente, identificador de multa e imagen de referencia.

Esto permitió implementar una búsqueda por aproximación visual, donde a partir de una imagen de entrada el sistema busca la imagen más parecida dentro de la base vectorial.

## Función de búsqueda por imagen

Se implementó la función `buscar_patente_imagen`, que recibe la ruta de una imagen y devuelve información asociada al vehículo encontrado.

La función realiza los siguientes pasos:

1. Vectoriza la imagen recibida.
2. Consulta la base vectorial para obtener la imagen más similar.
3. Recupera la patente asociada al resultado.
4. Consulta la base relacional para obtener los datos del vehículo.
5. Devuelve las multas asociadas a esa patente.
6. Muestra la distancia vectorial como medida de similitud.

La distancia vectorial indica qué tan parecida es la imagen consultada respecto de la imagen almacenada. Mientras menor sea la distancia, mayor es la similitud entre ambas imágenes.

## Control de versiones

Durante el Sprint 3 se continuó trabajando con Git y GitHub. Se creó la rama `Sprint_3` partiendo desde `Sprint_2`.

También se incorporó DVC para migrar archivos binarios y simular un remote local mediante el directorio:

`/content/remote_dvc`

Se versionaron los archivos necesarios del proyecto y se documentaron los cambios realizados en `CHANGELOG.md`.

## Conclusión

En este trabajo se desarrolló una solución integral para la gestión, persistencia, consulta y búsqueda visual de infracciones de tránsito.

El Sprint 3 permitió pasar de un procesamiento basado en archivos CSV a una arquitectura más organizada, utilizando una base de datos relacional para almacenar entidades estructuradas y una base vectorial para trabajar con imágenes mediante embeddings.

La integración entre SQLAlchemy, ChromaDB y OpenCLIP permitió vincular datos administrativos con evidencia visual, logrando que una imagen pueda utilizarse como entrada para recuperar información asociada a un vehículo y sus multas.

En conclusión, el trabajo permitió aplicar conceptos de programación orientada a objetos, modelado lógico, modelo relacional, ORM, consultas a base de datos, control de versiones de datos y búsqueda vectorial. Esta integración representa una base sólida para construir sistemas más avanzados de análisis, control y validación de infracciones vehiculares.
