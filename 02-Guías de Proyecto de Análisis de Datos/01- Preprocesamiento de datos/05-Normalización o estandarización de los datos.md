# Normalización o Estandarización de los Datos

La normalización y la estandarización son técnicas cruciales en el preprocesamiento de datos, especialmente en el contexto de la ciencia de datos y el aprendizaje automático. Ambas técnicas ajustan la escala de las características (features) pero de diferentes maneras y por distintas razones.

## ¿Qué es la normalización?

La normalización, también conocida como escalado mínimo-máximo, es el proceso de reescalar los datos para que estén en un rango específico, usualmente de 0 a 1. La fórmula para la normalización es la siguiente:

\[ x_{\text{normalizado}} = \frac{x - \min(x)}{\max(x) - \min(x)} \]

Donde \( x \) es el valor original, \( \min(x) \) es el valor mínimo de la característica, y \( \max(x) \) es el valor máximo.

## ¿Qué es la estandarización?

La estandarización, por otro lado, reescala los datos para que tengan una media de 0 y una desviación estándar de 1. La fórmula para la estandarización es:

\[ x_{\text{estandarizado}} = \frac{x - \mu}{\sigma} \]

Donde \( \mu \) es la media de la característica y \( \sigma \) es la desviación estándar.

## ¿Por qué se hace?

Estas técnicas se utilizan para homogeneizar la escala de las variables numéricas, especialmente cuando dichas variables tienen rangos de magnitud muy diferentes. Esto es importante porque muchos algoritmos de aprendizaje automático asumen que todos los datos están en una escala similar y son sensibles a la magnitud de las características.

## ¿Cuándo es importante?

La normalización y la estandarización son especialmente importantes en contextos donde:

- Se utilizan algoritmos que son sensibles a la magnitud de los datos, como k-vecinos más cercanos (k-NN) o SVM.
- Se realizan comparaciones o se suman características que tienen diferentes unidades de medida.
- Se aplican técnicas que requieren suposiciones sobre la distribución de los datos, como el análisis de componentes principales (PCA).

## Diferencia entre Normalización y Estandarización

La normalización y la estandarización son técnicas de preprocesamiento que reescalan los datos, pero lo hacen de maneras que son conceptual y prácticamente diferentes:

### Normalización

- **Objetivo:** Cambia la escala de los datos para que se ajusten a un rango específico, generalmente [0, 1] o [-1, 1].
- **Fórmula:** \(\frac{x - \min(x)}{\max(x) - \min(x)}\).
- **Uso común:** Es útil cuando los datos necesitan tener límites específicos. Esto ayuda a la convergencia en algoritmos que son sensibles a la magnitud de los valores, especialmente aquellos que no asumen ninguna distribución específica de los datos, como los algoritmos basados en distancias.
- **Influencia de los valores atípicos:** Los valores extremos o atípicos pueden afectar significativamente el resultado de la normalización porque los valores mínimos y máximos determinan la escala.
- **Ejemplo de aplicación:** Redes neuronales y algoritmos de clustering que requieren una escala definida y consistente.

### Estandarización

- **Objetivo:** Reescala los datos para que tengan una media de cero (0) y una desviación estándar de uno (1), transformando los datos en una distribución aproximadamente normal.
- **Fórmula:** \(\frac{x - \mu}{\sigma}\), donde \( \mu \) es la media y \( \sigma \) es la desviación estándar.
- **Uso común:** Es preferible cuando los algoritmos asumen que los datos siguen una distribución normal, como en el caso de los algoritmos basados en métodos estadísticos.
- **Influencia de los valores atípicos:** La estandarización es menos sensible a los valores atípicos en comparación con la normalización. Los valores extremos tienen menos efecto sobre la media y la desviación estándar que sobre los valores mínimos y máximos.
- **Ejemplo de aplicación:** Algoritmos que asumen una distribución normal de los datos como la regresión lineal, regresión logística o el análisis de componentes principales (PCA).

## ¿Cuándo usar normalización y cuándo usar estandarización?

La elección entre normalización y estandarización depende del contexto específico y los algoritmos que planeas utilizar:

### Usar Normalización cuando

- Los algoritmos que aplicarás son sensibles a la escala de los datos y no asumen ninguna distribución específica para los datos, como K-vecinos más cercanos (K-NN) y redes neuronales.
- Necesitas que los datos estén acotados en un rango específico. Esto es particularmente útil para técnicas que calculan distancias entre los pares de puntos.
- Estás trabajando con imágenes en el procesamiento de imágenes, donde la normalización se utiliza para escalar los valores de los píxeles a un rango estándar.

### Usar Estandarización cuando

- Quieres que tu modelo sea menos sensible a los valores atípicos, dado que la estandarización no fija los valores a un rango específico.
- Los algoritmos presuponen que los datos están normalmente distribuidos. Esto aplica a algoritmos como el Análisis de Componentes Principales (PCA), donde la estandarización es crucial para obtener resultados correctos.
- Estás utilizando algoritmos que son sensibles a la varianza y la media de los datos, como la regresión lineal, regresión logística, o máquinas de vectores de soporte (SVM).

En conclusión, la decisión de normalizar o estandarizar debe basarse en el algoritmo específico que se utilizará y en las propiedades intrínsecas del conjunto de datos. La experimentación y la validación cruzada pueden ofrecer orientación adicional sobre cuál método es más apropiado para tu situación particular.

## Ejemplo práctico

Imaginemos que tienes un conjunto de datos con dos características: altura en centímetros y peso en kilogramos. La altura varía de 150 a 200 cm, y el peso de 50 a 120 kg. Si utilizas un algoritmo como k-NN sin estandarizar o normalizar, la característica con mayor magnitud (peso) dominará el cálculo de la distancia, sesgando los resultados.

En Python, podrías normalizar o estandarizar estos datos de la siguiente manera utilizando `sklearn`:

```python
from sklearn.preprocessing import StandardScaler, MinMaxScaler
import numpy as np

# Supongamos que estos son tus datos
datos = np.array([[180, 70], [160, 60], [170, 80]])

# Normalización
scaler_min_max = MinMaxScaler()
datos_normalizados = scaler_min_max.fit_transform(datos)

# Estandarización
scaler_std = StandardScaler()
datos_estandarizados = scaler_std.fit_transform(datos)

print("Datos Normalizados:\n", datos_normalizados)
print("\nDatos Estandarizados:\n", datos_estandarizados)
```

En este ejemplo, la normalización ajusta la altura y el peso al rango de 0 a 1, mientras que la estandarización ajusta las características para que tengan una media de cero y una desviación estándar de uno.

 La elección entre normalización y estandarización dependerá del algoritmo específico que estés utilizando y de la naturaleza de tus datos.
