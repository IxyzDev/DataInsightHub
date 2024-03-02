# Limpieza de Strings en Ciencia de Datos

La limpieza de strings es un paso esencial en el preprocesamiento de datos, especialmente cuando trabajamos con texto. Esta etapa es crucial para asegurar la calidad y la consistencia de los datos, lo que a su vez afecta la precisión de los análisis y modelos de aprendizaje automático.

## ¿Cuándo es necesario tratar los strings?

Es necesario tratar los strings cuando:

- Los datos contienen errores tipográficos.
- Existe inconsistencia en el uso de mayúsculas y minúsculas.
- Los datos incluyen caracteres especiales no deseados.
- Hay presencia de espacios en blanco extra o no deseados.
- Se requiere unificar el formato de los strings para el análisis.

## ¿Cómo se tratan y normalizan los strings?

El tratamiento y normalización de strings puede involucrar varios métodos, entre los que se incluyen:

- **Conversión a mayúsculas o minúsculas:** Esto asegura la consistencia en la comparación de strings.
  
  ```python
  texto = "Ciencia de Datos"
  texto_minuscula = texto.lower()
  texto_mayuscula = texto.upper()
  ```

- **Eliminación de espacios en blanco:** Se eliminan espacios al inicio, al final o duplicados en el medio de los strings.

  ```python
  texto = "   Ciencia de Datos   "
  texto_sin_espacios = texto.strip()
  ```

- **Eliminación de caracteres especiales o no deseados:** Esto puede incluir puntuaciones, caracteres especiales o números, dependiendo del contexto.

  ```python
  import re
  texto = "¡Ciencia, de Datos!"
  texto_limpio = re.sub(r'[^\w\s]', '', texto)
  ```

- **Normalización de caracteres (NFD, NFC):** Esto convierte los caracteres a una forma consistente, especialmente útil para comparar strings.

  ```python
  import unicodedata
  texto = "café"
  texto_normalizado = unicodedata.normalize('NFD', texto)
  ```

## Métodos de limpieza de strings

Los métodos más comunes para la limpieza de strings incluyen:

- **strip(), lstrip(), rstrip():** Remueven espacios en blanco (o otros caracteres) del inicio, final o ambos lados del string.
- **replace():** Reemplaza una subcadena especificada por otra.
- **re.sub():** Permite reemplazar partes de strings usando expresiones regulares.

## Ejemplos prácticos

Consideremos un conjunto de datos con nombres de ciudades que presentan problemas de consistencia:

```python
ciudades = ["  Madrid", "Barcelona ", " VALENCIA", "Sevilla."]
```

Para limpiar estos datos, aplicaríamos los siguientes pasos:

```python
ciudades_limpio = [ciudad.strip().replace(".", "").title() for ciudad en ciudades]
```

Después de la limpieza, `ciudades_limpio` contendría:

```python
["Madrid", "Barcelona", "Valencia", "Sevilla"]
```

## Ejmplo practico de aplicación

Imaginemos que tenemos un dataset que contiene información sobre nombres de películas, y estas entradas tienen varios problemas comunes de limpieza, como espacios innecesarios, mayúsculas/minúsculas inconsistentes y caracteres especiales. El objetivo será limpiar estos strings para estandarizar los nombres de las películas.

Primero, necesitaremos instalar pandas si aún no lo hemos hecho:

```bash
pip install pandas
```

Ahora, vamos a crear un pequeño dataset de ejemplo y aplicarle varios pasos de limpieza:

```python
import pandas as pd

# Creación de un DataFrame de ejemplo.
data = {'Peliculas': ['  El Padrino ', 'el PADRINO', 'Los Vengadores', 'los VENGAdores!!', 'Interestelar ', ' interestelar']}
df = pd.DataFrame(data)

# Mostramos el DataFrame original.
print("DataFrame Original:\n", df)

# Limpieza de strings.
# 1. Eliminación de espacios en blanco al inicio y al final.
df['Peliculas'] = df['Peliculas'].str.strip()

# 2. Conversión a mayúsculas o minúsculas para estandarizar.
df['Peliculas'] = df['Peliculas'].str.lower()

# 3. Eliminación de caracteres especiales.
df['Peliculas'] = df['Peliculas'].str.replace('[^\w\s]', '', regex=True)

# 4. Opcional: Capitalización de cada palabra para un formato más estético.
df['Peliculas'] = df['Peliculas'].str.title()

# Mostramos el DataFrame después de la limpieza.
print("\nDataFrame Después de la Limpieza:\n", df)
```

Este script realizará los siguientes pasos de limpieza en los nombres de las películas:

1. **strip()**: Elimina los espacios al inicio y al final de cada string.
2. **lower()**: Convierte todos los caracteres a minúsculas para estandarizar el texto.
3. **replace() con regex**: Elimina los caracteres especiales, dejando solo letras y números.
4. **title()**: Convierte la primera letra de cada palabra a mayúscula para un formato más estético y estandarizado.

El resultado será un DataFrame con los nombres de las películas limpios y estandarizados, listo para ser utilizado en análisis posteriores o como parte de un sistema de recomendación, por ejemplo. Esta metodología de limpieza puede adaptarse y ampliarse según las necesidades específicas del dataset con el que estés trabajando.

## Conclusión

La limpieza de strings es un paso fundamental en el preprocesamiento de datos que ayuda a mejorar la calidad y la uniformidad de los datos, facilitando análisis más precisos y efectivos.
