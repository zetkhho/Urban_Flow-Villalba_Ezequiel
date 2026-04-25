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
