# Curso de Geomática y Sostenibilidad

Material base para introducir conceptos de geomática, análisis espacial y visualización de datos energéticos.

Profesor: Junior Antonio Calvo Montañez

## Estructura del proyecto

- `modules/module01.ipynb`: notebook principal del módulo 1.
- `modules/world.gpkg`: capa geoespacial de países del mundo.
- `modules/ruta.gpkg`: capa usada en ejercicios de geometría y análisis espacial.
- `requirements.txt`: dependencias de Python del curso.

## Instalación

Se recomienda usar `conda`.

```bash
conda create -n GyS-env python=3.12.3
conda activate GyS-env
pip install -r requirements.txt
pip install ipykernel pygments
```
## Codigo Notebook: `module01.ipynb`

El notebook está organizado como una introducción progresiva:

1. Geometrías básicas con `shapely`
   Se trabajan puntos, líneas, polígonos y geometrías múltiples.

2. Mapas, proyecciones y sistemas de referencia (CRS). Medición de áreas y distancias en grados y reproyectado. 

3. Lectura y análisis vectorial con `geopandas`
   Se exploran áreas, perímetros, centroides, buffers, intersecciones y clips.

4. Aplicación temática: energía y sostenibilidad
   Se integran datos tabulares de energía con geometrías de países para construir mapas coropléticos y visualizaciones interactivas.

## Datos sobre energía de `Our World in Data`

La práctica usa el archivo público:

- Fuente: https://github.com/owid/energy-data
- CSV usado en el notebook:
  `https://raw.githubusercontent.com/owid/energy-data/master/owid-energy-data.csv`

Es un dataset no es geoespacial, es una tabla con indicadores por paises y por año. Para hacer mapas, se debe unir esa tabla con la capa espacial `world.gpkg`.

### Columnas de uso en el  `Módulo 01`

El notebook trabaja con estas variables:

- `country`: nombre del país.
- `year`: año del registro.
- `coal_production`: producción de carbón.
- `gas_production`: producción de gas.
- `oil_production`: producción de petróleo.

En este ejercicio, estas variables se interpretan en `TWh`.

## Qué se espera en la práctica

Con base en el notebook, el estudiante debe:

1. Elegir una región del mundo.
2. Filtrar los países de esa región.
3. Unir la tabla energética con la geometría de países.
4. Crear mapas coropléticos para `gas_production`, `oil_production` y `coal_production` en 2024.
5. Crear un mapa animado para una variable entre 2014 y 2024.
6. Escribir una breve interpretación de cada visualización.

## Preguntas guía para el análisis

- ¿Qué países dominan la producción en la región elegida?
- ¿Qué variable muestra mayor concentración espacial?
- ¿Existen países sin datos?
- ¿Se observa crecimiento, caída o estabilidad entre 2014 y 2024?

## Dependencias principales

- `numpy`
- `pandas`
- `geopandas`
- `matplotlib`
- `plotly`
- `nbformat`
- `mapclassify`
