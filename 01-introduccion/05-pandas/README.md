# Guía de Uso de Scikit-Learn

## ¿Qué es Scikit-Learn?

Scikit-Learn es una biblioteca de aprendizaje automático (machine learning) de código abierto para Python. Proporciona herramientas simples y eficientes para la minería y el análisis de datos, así como para la construcción y evaluación de modelos de aprendizaje automático.

## Instalar

```python
pip install -U scikit-learn
```

## Características Principales

- Ofrece una amplia gama de algoritmos de aprendizaje automático.
- Compatible con otras bibliotecas populares como NumPy y pandas.
- Proporciona utilidades para la preparación de datos, selección de modelos y evaluación de rendimiento.
- Diseñada para ser fácil de usar y extensible.

## Ejemplo de Uso

A continuación, mostraremos un ejemplo de cómo utilizar Scikit-Learn para entrenar y evaluar un modelo de clasificación. Utilizaremos el conjunto de datos Iris, que es un conjunto de datos clásico para problemas de clasificación en aprendizaje automático.

```python
# Importar Scikit-Learn y cargar el conjunto de datos Iris
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import accuracy_score

# Cargar el conjunto de datos Iris
iris = load_iris()
X = iris.data
y = iris.target

# Dividir los datos en conjuntos de entrenamiento y prueba
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Crear un modelo de clasificación KNeighbors
modelo = KNeighborsClassifier(n_neighbors=3)

# Entrenar el modelo
modelo.fit(X_train, y_train)

# Realizar predicciones en el conjunto de prueba
predicciones = modelo.predict(X_test)

# Calcular la precisión del modelo
precision = accuracy_score(y_test, predicciones)
print("Precisión del modelo:", precision)
```

En este ejemplo, utilizamos Scikit-Learn para cargar el conjunto de datos Iris, dividir los datos en conjuntos de entrenamiento y prueba, crear y entrenar un modelo de clasificación KNeighbors, realizar predicciones y evaluar la precisión del modelo utilizando la función `accuracy_score` de Scikit-Learn.

## Conclusión

Scikit-Learn es una biblioteca esencial para cualquier persona interesada en el aprendizaje automático en Python. Proporciona una variedad de algoritmos y herramientas para construir, evaluar y mejorar modelos de aprendizaje automático. Ya sea que estés trabajando en tareas de clasificación, regresión o agrupamiento, Scikit-Learn te ofrece las herramientas necesarias para abordar problemas de aprendizaje automático de manera efectiva.
