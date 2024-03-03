# Introducción al Aprendizaje Supervisado

El aprendizaje supervisado es una categoría fundamental dentro del aprendizaje automático que implica entrenar un modelo en un conjunto de datos etiquetado para que pueda aprender a predecir las salidas correctas a partir de nuevas entradas no vistas anteriormente. Esta guía proporciona una visión general de los conceptos básicos del aprendizaje supervisado, sus aplicaciones, los tipos de algoritmos más comunes, y cómo y cuándo se utilizan.

## ¿Qué es el Aprendizaje Supervisado?

El aprendizaje supervisado es un enfoque en el que se enseña a los modelos de inteligencia artificial a tomar decisiones a partir de ejemplos. Estos ejemplos son un conjunto de datos que incluyen entradas y las salidas deseadas (etiquetas). Durante el entrenamiento, el modelo ajusta sus parámetros para minimizar el error en sus predicciones en comparación con las salidas reales.

## Aplicaciones del Aprendizaje Supervisado

El aprendizaje supervisado se aplica en una variedad de campos, incluyendo pero no limitándose a:

- **Diagnóstico médico:** Clasificar imágenes médicas para identificar enfermedades.
- **Predicción financiera:** Estimar el precio futuro de activos financieros.
- **Filtrado de correo electrónico:** Clasificar correos electrónicos en categorías como importante, no importante, spam, etc.
- **Evaluación de riesgo de crédito:** Predecir la probabilidad de impago de un préstamo.

## Algoritmos de Clasificación

 **¿En qué consisten?** Los algoritmos de clasificación se utilizan para predecir la categoría o clase de una entidad basándose en sus características. Por ejemplo, clasificar correos electrónicos en "spam" o "no spam" implica aprender de ejemplos de correos previamente etiquetados para predecir la categoría de nuevos correos.

- **¿Cuándo se utilizan?** Se utilizan cuando la variable de salida es categórica, es decir, cuando hay dos o más categorías que definen la variable objetivo.

- **¿Por qué se utilizan?** Permiten automatizar tareas de decisión basadas en datos, facilitando la identificación y categorización automática de entidades en diversas aplicaciones, desde diagnósticos médicos hasta filtrado de contenido en internet.

- **¿Cuándo elijo un algoritmo de clasificación?** Debes elegir un algoritmo de clasificación cuando tu objetivo es etiquetar entradas con categorías predefinidas y deseas que el modelo pueda identificar y asignar estas etiquetas a nuevas observaciones.

### Árboles de Decisión

- **Cómo funciona:** Un árbol de decisión divide los datos a través de una serie de decisiones binarias tomadas en los nodos. En cada nodo, elige el atributo que mejor divide el conjunto de datos en subconjuntos más homogéneos respecto a la variable objetivo.
- **Cuándo se usa:** Ideal cuando se busca un modelo intuitivo y transparente, que pueda explicarse fácilmente a personas no expertas.
- **Ejemplo práctico:** Decidir si conceder o no un préstamo bancario basándose en la historia crediticia, ingresos y deudas del solicitante.

### K-Vecinos Más Cercanos (K-NN)

- **Cómo funciona:** Este algoritmo clasifica cada dato nuevo basándose en la mayoría de votos de sus 'k' vecinos más cercanos. La clase asignada es la más común entre los k vecinos.
- **Cuándo se usa:** Efectivo cuando los datos son intuitivamente agrupables y no hay un número excesivo de dimensiones.
- **Ejemplo práctico:** Recomendar un producto en un e-commerce basándose en la similitud de preferencias y compras previas de usuarios cercanos en el espacio de características.

### Máquinas de Vectores de Soporte (SVM)

- **Cómo funciona:** SVM encuentra el hiperplano que mejor divide las clases de datos en el espacio de características. Utiliza "trucos del kernel" para tratar datos no linealmente separables, mapeándolos a un espacio de mayor dimensión donde puedan ser separados.
- **Cuándo se usa:** Útil para clasificaciones claras y marginadas, incluso en espacios de alta dimensión.
- **Ejemplo práctico:** Distinguir entre correos electrónicos spam y no spam basándose en la frecuencia de palabras clave y otros atributos.

### Redes Neuronales

- **Cómo funciona:** Consisten en capas de neuronas interconectadas que transmiten señales y se ajustan en el proceso de aprendizaje. Las capas intermedias permiten abstraer características a diferentes niveles.
- **Cuándo se usa:** Adecuadas para modelar problemas complejos y no lineales, especialmente aquellos con grandes cantidades de datos.
- **Ejemplo práctico:** Identificar y clasificar enfermedades a partir de imágenes médicas, como radiografías o resonancias magnéticas.

### Regresión Logística

- **Cómo funciona:** Modela la probabilidad de que una observación pertenezca a una categoría específica mediante la función logística. A pesar de su nombre, se utiliza para clasificación binaria.
- **Cuándo se usa:** Ideal para situaciones donde se necesita estimar la probabilidad de un evento binario.
- **Ejemplo práctico:** Predecir si un cliente de un banco incurrirá en impago de un préstamo basándose en su historial crediticio y situación financiera.

### Naive Bayes

- **Cómo funciona:** Aplica el teorema de Bayes asumiendo independencia entre las características. Calcula las probabilidades de cada clase para una observación y clasifica en la que tenga mayor probabilidad.
- **Cuándo se usa:** Funciona bien en clasificación de textos y situaciones donde la independencia entre características es una aproximación razonable.
- **Ejemplo práctico:** Clasificar noticias en categorías basándose en la frecuencia de palabras y términos clave.

### Random Forest

- **Cómo funciona:** Construye múltiples árboles de decisión durante el entrenamiento y su predicción final se basa en la media (regresión) o moda (clasificación) de las predicciones de todos los árboles.
- **Cuándo se usa:** Útil cuando se necesita un modelo robusto y preciso, capaz de manejar datos con mucha variabilidad y características.
- **Ejemplo práctico:** Evaluar el riesgo de enfermedades en pacientes basándose en un conjunto diverso de indicadores y historial médico.

## Algoritmos de Regresión

- **¿En qué consisten?** Los algoritmos de regresión predicen una cantidad continua a partir de una o más variables independientes. Por ejemplo, predecir el precio de una casa basándose en su tamaño, ubicación y características es un problema de regresión.

- **¿Cuándo se utilizan?** Se utilizan cuando la variable de salida es numérica o continua, como precios, temperaturas, distancias, etc.

- **¿Por qué se utilizan?** Facilitan la comprensión de las relaciones entre variables y la predicción de valores futuros, lo que es crucial en áreas como la economía, la ingeniería o la ciencia, donde se necesitan estimaciones precisas basadas en datos existentes.

- **¿Cuándo elijo un algoritmo de regresión?** Debes elegir un algoritmo de regresión cuando tu objetivo es predecir una cantidad continua y deseas entender cómo varía esta cantidad en respuesta a cambios en otras variables.

### Regresión Lineal

- **Cómo funciona:** La regresión lineal establece un modelo lineal entre la variable dependiente \(y\) y una o más variables independientes \(x\). Se busca la línea (en 2D) o hiperplano (en más dimensiones) que mejor se ajusta a los datos, minimizando la suma de las diferencias cuadradas entre los valores observados y los predichos.
- **Cuándo se usa:** Se utiliza cuando se espera que la relación entre las variables sea aproximadamente lineal. Es ideal para entender la influencia de una o varias características independientes sobre una característica dependiente.
- **Ejemplo práctico:** Predecir el precio de venta de un automóvil basándose en su kilometraje y año de fabricación.

### Regresión Polinomial

- **Cómo funciona:** Extiende la regresión lineal permitiendo que la relación entre las variables independientes y la variable dependiente sea un polinomio. Por ejemplo, en lugar de \( y = ax + b \), podríamos tener \( y = ax^2 + bx + c \).
- **Cuándo se usa:** Útil cuando la relación entre las variables independientes y la dependiente es no lineal pero puede ser aproximada por un polinomio.
- **Ejemplo práctico:** Modelar la relación entre la velocidad de un vehículo y su consumo de combustible, donde aumentos incrementales en velocidad pueden incrementar el consumo de forma no lineal.

### Árboles de Decisión para Regresión

- **Cómo funciona:** Similar a los árboles de decisión para clasificación, pero en lugar de predecir una clase, predicen un valor continuo. El árbol divide el espacio de las características en regiones, y para cada región, predice un valor constante.
- **Cuándo se usa:** Adecuado cuando los datos tienen estructuras no lineales y complejas que un modelo lineal no puede capturar.
- **Ejemplo práctico:** Predecir el valor de casas basándose en características como área, número de habitaciones, ubicación, etc.

### Lasso y Ridge Regression (Regresión L1 y L2)

- **Cómo funcionan:** Tanto Lasso como Ridge modifican la regresión lineal añadiendo un término de penalización al tamaño de los coeficientes para prevenir el sobreajuste. Ridge (L2) penaliza la suma de los cuadrados de los coeficientes, mientras que Lasso (L1) penaliza la suma de los valores absolutos de los coeficientes, lo que puede resultar en algunos coeficientes exactamente iguales a cero.
- **Cuándo se usan:** Útiles cuando hay muchas características poco importantes o cuando se sospecha de multicolinealidad (Ridge). Lasso se prefiere cuando se cree que muchos de los atributos no son relevantes para la predicción.
- **Ejemplo práctico:** En la genómica, donde se tiene un alto número de características (genes), Lasso puede ayudar a identificar cuáles son relevantes para predecir un fenotipo (como una enfermedad).

### Elastic Net

- **Cómo funciona:** Combina las penalizaciones de Lasso y Ridge, controlando la mezcla de las dos mediante un parámetro. Puede heredar las ventajas de ambos, manteniendo la capacidad de Ridge para manejar situaciones multicolineales y la de Lasso para seleccionar características.
- **Cuándo se usa:** Es especialmente útil cuando hay múltiples características correlacionadas entre sí. Elastic Net puede equilibrar la selección de grupos de características correlacionadas.
- **Ejemplo práctico:** En la modelización predictiva de datos financieros, donde muchas variables económicas pueden estar interrelacionadas, Elastic Net puede ayudar a identificar los predictores más robustos y estables.

## Conclusión

La elección entre utilizar un algoritmo de clasificación o de regresión se basa en el tipo de variable de salida que estás tratando de predecir:

- **Elige clasificación** cuando la salida es categórica (p.ej., sí/no, colores, tipos de productos).
- **Elige regresión** cuando la salida es numérica y continua (p.ej., precios, temperaturas).
