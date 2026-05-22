# CHANGELOG.md
## Dia 1 (21/4/2026)
Ejercicio 1
- Creacion del repositorio github.
- Cracion del token, Secrets y configuracion del repo.
- Clonado del repo.
- Creacion de Rama Nueva.
- Creacion de la estructura de directorios.
- Creacion de (README.md).
- Creacion de (CHANGELOG.md).
- Creacion de (.gitignore).

## Dia 2 (22/4/2026)
Ejercicio 02
- Descarga del dataset raw original.
- Almacenamiento del archivo en (urban_flow/data/raw/speeding_fines.csv).
- Visualización de las primeras 5 filas.
- Revisión de tipos de datos.
- Conteo de valores nulos por columna.

## Día 3 (23/04/2026)
Ejercicio 03
- Normalización de fechas.
- Normalización de horas.
- Normalización de ubicaciones.
- Normalización de patentes.
- Eliminación de filas con vacíos relevantes.
- Detección de outliers.
- Creación de exceso_velocidad_real.
- Creación de exceso_velocidad.
- Eliminación de filas sin infracción.
- Guardado del dataset limpio en (urban_flow/data/interim/speeding_fines.csv).

## Día 4 (24/04/2026)
Ejercicio 4
- Se creó la clase FineAnalyzer.
- Se encapsuló el DataFrame limpio dentro del objeto.
- Se implementó el ranking top 5 de patentes más multadas.
- Se implementó el ranking top 5 de horarios con más multas.
- Se calculó el exceso promedio de velocidad.
- Se calculó el exceso real promedio de velocidad.
- Se contabilizaron las multas por ubicación.
- Se creó el objeto analizador y se probaron sus métodos.

Ejercicio 5
- Se generaron y exportaron los gráficos solicitados del ejercicio 5:
  - fines.jpg
  - hours.jpg
  - months.jpg
  - hour.jpg
  - date.jpg
- Se trabajó sobre los datos limpios guardados en urban_flow/data/interim/speeding_fines.csv.
- Se ajustó el gráfico de torta para representar mejor el porcentaje de infracciones por hora agrupadas.

## Día 6 (25/04/2026)
Ejercicio 06
- Se calculó el porcentaje de infracciones ocurridas en la fecha 1932-01-01.
- Se calculó el porcentaje de infracciones ocurridas a la hora 00:00.

Ejercicio 07
- Se redactó la conclusión final sobre los datos del dataset.
- Se incorporó la conclusión en el README.md.

## Día 7 - Correcciones TP1 según devolución docente

- Se corrigieron los gráficos de líneas del Ejercicio 05 usando agrupación con groupby y promedio.
- Se dejó de graficar cada registro individual por índice secuencial.
- Se agregaron type hints a la clase FineAnalyzer y a sus métodos.
- Se mantuvo la estructura del Sprint_1 como base para iniciar luego el Sprint_2.

## Día 8 - Inicio Sprint_2

### Ejercicio 01
- Se configuró el repositorio para trabajar sobre la rama Sprint_2.
- Se clonó el repositorio del TP1 partiendo desde Sprint_1.
- Se descargó el dataset de imágenes urban_flow_plates.zip.
- Se descomprimieron las imágenes en urban_flow/data/raw/imgs.
- Se validó que el dataset contiene 110 imágenes reales.


### Ejercicio 02
- Se listaron las imágenes disponibles mostrando nombre y tamaño en KB.
- Se clasificaron las imágenes en los grupos 'plates' y 'completes'.
- Se calcularon dimensiones y área de cada imagen utilizando OpenCV.
- Se creó el diccionario group_images con metadata de imágenes.
- Se calculó la resolución promedio por grupo.
- Se guardó el archivo group_images.json en urban_flow/data/interim/.
- Se implementó una función reutilizable para visualizar imágenes aleatorias.
- Se mostraron 8 imágenes aleatorias en formato 4x2.


## Día 9 - Sprint_2

### Ejercicio 03
- Se convirtieron las imágenes originales a escala de grises.
- Se guardaron las imágenes procesadas en `urban_flow/data/interim/imgs/03_01_gray_scale/`.
- Se aplicó suavizado mediante blur.
- Se guardaron las imágenes suavizadas en `urban_flow/data/interim/imgs/03_02_blur/`.
- Se aplicó detección de bordes con Canny.
- Se guardaron las imágenes con bordes en `urban_flow/data/interim/imgs/03_03_canny/`.
- Se reutilizó la función de visualización aleatoria para validar las imágenes procesadas.

### Ejercicio 04
- Se utilizó EasyOCR para extraer texto de las imágenes.
- Se limpiaron las patentes detectadas dejando solo letras y números.
- Se almacenaron las patentes detectadas en la clave `patent` del diccionario `group_images`.
- Se compararon las patentes detectadas contra el dataset `speeding_fines.csv`.
- Se calculó el porcentaje de coincidencia mediante ratio.
- Se aceptaron coincidencias con 80% o más.
- Se generó el dataframe final con las columnas `imagen`, `patente_imagen` y `ratio`.


## Día 10 - Sprint_2

### Ejercicio 05
- Se calcularon métricas del dataset final relacionado con imágenes.
- Se contabilizaron multas con y sin imágenes asociadas.
- Se identificaron imágenes sin match con el dataset de multas.
- Se calcularon multas pendientes considerando estados IMPAGA y APELADA.
- Se calcularon multas pendientes con imágenes relacionadas.

### Ejercicio 06
- Se redactó la conclusión final del Sprint_2 sobre la relación entre imágenes y datos.
- Se documentó el uso de OCR para extraer patentes desde imágenes.
- Se incorporó la exploración extra con procesamiento morfológico, contornos y filtrado geométrico.
- Se creó el archivo README_Sprint_2.md con objetivos, procesamiento, resultados y conclusión.
