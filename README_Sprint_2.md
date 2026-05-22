# Urban Flow - Sprint 2

## Objetivo
En este sprint se trabajó sobre la relación entre imágenes de vehículos y el dataset de multas utilizando técnicas de procesamiento de imágenes y OCR.

## Procesamiento realizado

- Agrupamiento de imágenes por tipo.
- Detección de regiones de patente.
- Extracción de texto mediante OCR con EasyOCR.
- Limpieza y normalización de patentes.
- Comparación contra el dataset de multas usando similitud de texto.
- Generación de matches utilizando ratio de similitud.

## Resultados obtenidos

- Multas totales analizadas: 1713
- Matches iniciales encontrados: 751
- Imágenes sin match inicial: 78
- Nuevos matches recuperados mediante exploración extra: 9

## Criterio sobre multas pendientes

Para el análisis se consideraron como multas pendientes aquellas cuyo estado es `IMPAGA` o `APELADA`, ya que en ambos casos la multa no se encuentra cerrada definitivamente como `PAGADA`.
Esto permite diferenciar entre multas ya resueltas y multas que todavía requieren pago, revisión o resolución administrativa.

## Exploración Extra

Se aplicaron técnicas adicionales de visión computacional sobre imágenes sin coincidencias:

- Cierre morfológico rectangular.
- Detección de contornos.
- Filtrado geométrico por área y aspect ratio.
- Nueva ejecución de OCR sobre regiones candidatas.

Esto permitió recuperar coincidencias adicionales manteniendo un umbral confiable de similitud del 80%.

## Conclusión

El trabajo permitió relacionar correctamente una gran cantidad de imágenes con multas reales. Sin embargo, se observaron errores típicos de OCR producidos por desenfoque, iluminación, perspectiva y similitud visual entre caracteres.

La exploración extra demostró que técnicas de procesamiento morfológico pueden mejorar la detección de patentes en casos difíciles.
