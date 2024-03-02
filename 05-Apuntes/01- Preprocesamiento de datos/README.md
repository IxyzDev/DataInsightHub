# Lista de tareas para preprocesamiento de datos 📊

¡Bienvenido a la lista de tareas para preprocesamiento de datos! Aquí encontrarás una guía paso a paso para preparar tus datos antes de aplicar técnicas de análisis o modelado.

## Índice

1. [Identificación de datos faltantes o nulos](./01-Identificación%20de%20datos%20faltantes%20o%20nulos.md): Es fundamental identificar y tratar los valores faltantes. Puedes optar por eliminar los registros con valores nulos o imputarlos utilizando diversas técnicas, como la media, la mediana o incluso modelos predictivos.

2. [Detección y tratamiento de outliers](./02-Detección%20y%20tratamiento%20de%20outliers%20(valores%20atípicos).md): Los outliers pueden distorsionar los resultados de tu análisis. Identifícalos mediante métodos estadísticos o gráficos y decide si los eliminas, ajustas o mantienes

3. [Limpieza de strings](/carpeta/limpieza_strings.md): En datos textuales, es útil normalizar los strings eliminando espacios extra, convirtiendo todo a mayúsculas o minúsculas y eliminando caracteres especiales o acentos.

4. [Codificación de variables categóricas](/carpeta/codificacion_categorica.md): Los modelos de machine learning trabajan con números, por lo que debes convertir las variables categóricas en numéricas mediante técnicas como el one-hot encoding o el label encoding.

5. [Normalización o estandarización de los datos](/carpeta/normalizacion.md): Esto es especialmente importante para algoritmos que son sensibles a la magnitud de los datos, como los basados en distancia. La normalización ajusta los datos en una escala de 0 a 1, mientras que la estandarización centra los datos con media 0 y desviación estándar 1.

6. [Reducción de dimensionalidad](/carpeta/reduccion_dimensionalidad.md): Técnicas como el Análisis de Componentes Principales (PCA) pueden ayudarte a reducir el número de variables, manteniendo la mayor cantidad de información posible.

7. [Verificación de consistencia](/carpeta/verificacion_consistencia.md): Asegúrate de que los datos sean consistentes en todo el conjunto de datos, verificando por ejemplo, que las variables categóricas no contengan valores fuera de las categorías esperadas.

8. [División en conjuntos de entrenamiento y prueba](/carpeta/division_entrenamiento_prueba.md): Antes de aplicar técnicas de modelado, divide tus datos en conjuntos de entrenamiento y prueba para poder evaluar la generalización de tu modelo.
