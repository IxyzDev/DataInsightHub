# Detección y Tratamiento de Outliers (Valores Atípicos)

## ¿Qué son los Outliers?

Los outliers, o valores atípicos, son observaciones que se desvían tanto de las demás que levantan sospechas sobre si fueron generadas por un mecanismo diferente. En el contexto de los datos, un outlier puede ser resultado de una variabilidad en la medición o indicar un error experimental; los outliers pueden ser unidimensionales (individuales), multidimensionales y en series temporales.

## ¿Cómo afectan y distorsionan los resultados?

Los outliers pueden tener un impacto significativo en los resultados de tus análisis estadísticos y modelos predictivos:

- Pueden causar una distorsión significativa en el promedio y la desviación estándar de tus datos.
- Pueden afectar las suposiciones de los tests estadísticos y los resultados de los modelos de regresión.
- En aprendizaje automático, pueden causar que los algoritmos se sobreajusten, aprendiendo de los datos atípicos como si fueran patrones comunes.

## Identificación de Outliers

### Métodos Estadísticos

1. **Z-Score:** El puntaje Z indica cuántas desviaciones estándar una observación está del promedio. Un Z-score puede usarse para identificar outliers cuando los valores son más altos o más bajos que lo que se consideraría normal, típicamente valores con un Z-score mayor de 3 o menor de -3.

2. **Rango Intercuartílico (IQR):** El IQR es la diferencia entre el tercer cuartil (Q3) y el primer cuartil (Q1). Un valor es considerado un outlier si es mayor que Q3 + 1.5*IQR o menor que Q1 - 1.5*IQR.

### Gráficos para Identificación

1. **Boxplot (Diagrama de caja):** Los boxplots son excelentes para visualizar la distribución de los datos y detectar outliers, que se muestran como puntos individuales fuera del "bigote" del diagrama.

2. **Scatter Plot (Gráfico de dispersión):** Útil para identificar outliers, especialmente en el contexto de relaciones bivariadas, donde puedes ver puntos que no encajan con la tendencia general.

### Ejemplos de Detección

- **Z-Score:**

  ```python
  import numpy as np

  datos = np.random.normal(0, 1, 100)
  outliers = datos[np.abs(stats.zscore(datos)) > 3]
  ```

- **IQR:**

  ```python
  Q1 = np.percentile(datos, 25)
  Q3 = np.percentile(datos, 75)
  IQR = Q3 - Q1
  outliers = datos[(datos < Q1 - 1.5 * IQR) | (datos > Q3 + 1.5 * IQR)]
  ```

- **Boxplot:**

  ```python
  import matplotlib.pyplot as plt

  plt.boxplot(datos)
  plt.show()
  ```

## Métodos de Tratamiento

Una vez identificados los outliers, puedes decidir cómo manejarlos según el contexto de tu análisis:

1. **Exclusión:** Si determinas que los outliers son el resultado de un error o no son relevantes para tu análisis, puedes optar por excluirlos.

2. **Transformación:** A veces, una transformación de los datos puede reducir el efecto de los outliers, por ejemplo, utilizando una transformación logarítmica.

3. **Imputación:** En algunos casos, puedes optar por imputar los valores atípicos, reemplazándolos con medias, medianas o mediante métodos de imputación más sofisticados.

4. **Capping:** Esta técnica implica poner un límite superior e inferior en los datos, de modo que los valores extremos se "recortan" a estos límites.

El tratamiento adecuado de los outliers es crucial para la validez y fiabilidad de tus análisis y resultados en ciencia de datos. La elección del método depende del contexto de tus datos y de tus objetivos de análisis.

## Post-Procesamiento de Outliers

Para verificar que has tratado correctamente los outliers en tu conjunto de datos, es importante realizar un análisis estadístico detallado antes y después del tratamiento. Esto te permite evaluar el impacto de tu tratamiento y asegurarte de que los resultados sean más representativos de la población general. A continuación, describo cómo puedes aplicar y interpretar diversas pruebas y medidas estadísticas:

### Medidas de Tendencia Central y Dispersión

Antes y después de tratar los outliers, calcula y compara las siguientes medidas:

1. **Media:** Es sensible a los outliers. Un tratamiento efectivo de outliers debería estabilizar la media, acercándola a la mediana si los outliers eran significativos.
2. **Mediana:** Es robusta a los outliers y no debería cambiar drásticamente a menos que los outliers afecten una porción considerable de tus datos.
3. **Varianza y Desviación Estándar:** Los outliers pueden inflar la varianza. Un tratamiento efectivo debería reducir la varianza, indicando una distribución más homogénea de los datos.
4. **Rango y Rango Intercuartílico (IQR):** Estas medidas también deberían mostrar cambios, indicando una distribución más compacta después del tratamiento de outliers.

### Pruebas Estadísticas

Para evaluar la normalidad y la homogeneidad de tus datos antes y después del tratamiento, puedes emplear:

1. **Prueba de Shapiro-Wilk:** Ideal para muestras pequeñas, esta prueba evalúa la hipótesis de normalidad. Si el p-valor es menor que el nivel de significancia (usualmente 0.05), la hipótesis nula de normalidad se rechaza. Después del tratamiento de outliers, esperarías obtener un p-valor mayor si los datos se asemejan más a una distribución normal.
   
   ```python
   from scipy.stats import shapiro
   
   # Aplicar la prueba de Shapiro-Wilk
   stat, p_valor = shapiro(datos)
   print('Estadístico de prueba:', stat, 'P-valor:', p_valor)
   ```

2. **Prueba de D'Agostino's K^2:** Esta prueba evalúa la asimetría y curtosis de la distribución de los datos. Valores de p significativos indican desviaciones de la normalidad. Post-tratamiento, deberías buscar p-valores no significativos, indicando que no hay evidencia para rechazar la normalidad.

   ```python
   from scipy.stats import normaltest
   
   # Aplicar la prueba de D'Agostino's K^2
   stat, p_valor = normaltest(datos)
   print('Estadístico de prueba:', stat, 'P-valor:', p_valor)
   ```

### Interpretación y Relevancia de las Pruebas

- **Cuándo son relevantes cada prueba:** La relevancia de cada prueba depende del tamaño de tu muestra y de tus objetivos específicos. La prueba de Shapiro-Wilk es más adecuada para muestras pequeñas, mientras que la prueba de D'Agostino's K^2 funciona mejor con muestras más grandes.
  
- **Identificación de un buen tratamiento:** Sabrás que el tratamiento ha sido efectivo si observas que la media y la varianza son más estables y si las pruebas de normalidad muestran p-valores no significativos (indicando no rechazo de la normalidad) después del tratamiento.

  - Una reducción en la varianza y en la desviación estándar post-tratamiento indica que has controlado los valores extremos.
  - Mejoras en la normalidad, reflejadas por las pruebas estadísticas, sugieren que los datos se ajustan mejor a la distribución asumida después de tratar los outliers.

Al aplicar y comparar estos métodos y medidas antes y después del tratamiento, podrás tener una comprensión clara de la eficacia de tu intervención en los outliers y asegurarte de que tus análisis posteriores sean más robustos y representativos.

## P-valor y Significancia Estadística

El p-valor es un concepto estadístico crucial utilizado para decidir si el resultado de un experimento es estadísticamente significativo. Aquí te explico qué es, para qué sirve y cómo se interpreta:

### ¿Qué es el p-valor?

El p-valor es la probabilidad de obtener resultados al menos tan extremos como los resultados observados durante el experimento, bajo la suposición de que la hipótesis nula es cierta. En esencia, el p-valor te dice cómo de compatible son tus datos con la hipótesis nula.

### ¿Para qué sirve?

1. **Toma de Decisiones en Pruebas de Hipótesis:** El p-valor es fundamental en el contexto de las pruebas de hipótesis estadísticas. Ayuda a determinar si los resultados observados en tu muestra son lo suficientemente inusuales bajo la suposición de que la hipótesis nula es correcta.

2. **Evaluación de Evidencia Contra la Hipótesis Nula:** Un p-valor bajo indica que la evidencia en contra de la hipótesis nula es fuerte. En cambio, un p-valor alto sugiere que la evidencia contra la hipótesis nula es débil.

### ¿Cómo se interpreta?

- **P-valor Bajo (< 0.05):** Tradicionalmente, si el p-valor es menor que 0.05, se considera que los resultados son estadísticamente significativos. Esto significa que hay menos de un 5% de probabilidad de que tus resultados sean producto del azar bajo la hipótesis nula. En tal caso, se rechaza la hipótesis nula.

- **P-valor Alto (≥ 0.05):** Si el p-valor es mayor o igual a 0.05, generalmente se considera que no hay suficiente evidencia para rechazar la hipótesis nula. Esto no significa que la hipótesis nula sea verdadera, sino que no tienes suficiente evidencia estadística para descartarla.

- **Contexto y Disciplina:** Es crucial entender que el umbral de 0.05 no es una regla fija y puede variar según el campo de estudio o el contexto específico. En algunas áreas de investigación, un umbral de 0.01 (o incluso más riguroso) puede ser apropiado, mientras que en otros, un umbral menos estricto como 0.1 podría ser aceptable.

### Ejemplo Práctico:

Imagina que estás investigando si un dado es justo (hipótesis nula) y obtienes una proporción inusualmente alta de seises en tus lanzamientos. Si calculas un p-valor basado en esta experimentación y resulta ser 0.03, interpretarías que, si el dado fuera justo, la probabilidad de obtener una proporción de seises tan alta o más, puramente por azar, sería del 3%. Dado que esto está por debajo del umbral común de 0.05, podrías concluir que hay evidencia estadística suficiente para rechazar la hipótesis de que el dado es justo.

En resumen, el p-valor es una herramienta estadística que te ayuda a determinar si los resultados de tu estudio proporcionan suficiente evidencia para rechazar la hipótesis nula, basándote en la probabilidad de observar tus resultados (o más extremos) si la hipótesis nula fuera cierta.
