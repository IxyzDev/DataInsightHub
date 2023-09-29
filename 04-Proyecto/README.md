### 1) Depuración del dataset (10%)
- Carga el dataset y revisa si hay datos faltantes o erróneos.
- Aplica técnicas de limpieza de datos para asegurarte de que los nodos y las aristas sean coherentes y estén en el formato que necesitas.

### 2) Medidas de Centralidad (20%)
- Utiliza bibliotecas como NetworkX en Python para calcular las medidas de centralidad, como grado (in-degree y out-degree si la red es dirigida), cercanía (closeness), intermediación (betweenness) y PageRank.

### 3) Modelo de Dispersión de Influencia (20%)
- Implementa el modelo de dispersión de influencia Linear Threshold en Python, posiblemente utilizando también NetworkX.

### 4) Cálculo de la Dispersión de Influencia (20%)
- Utiliza el modelo de dispersión de influencia para analizar cómo se propaga la influencia a través de los nodos más centrales (top-10 nodos) identificados en el paso 2.

### 5) Correlación de Medidas de Centralidad (20%)
- Utiliza el coeficiente de correlación de Spearman para analizar cómo se relacionan las diferentes medidas de centralidad entre sí.
- Visualiza los resultados con una matriz de correlación, señalando específicamente los valores con un p-value < 0.05.

### 6) Interpretación de Resultados (10%)
- Redacta un párrafo resumiendo cómo interpretas los resultados obtenidos en los pasos 4 y 5 en el contexto del dominio de aplicación del dataset que has escogido.

### Formato de entrega
Para el cuaderno de Jupyter, asegúrate de incluir:
1) Celdas de texto que expliquen cada paso.
2) Códigos para cada análisis y cálculo.
3) Salidas de ejecución, incluyendo gráficos y tablas.

### Rúbrica
- Asegúrate de cumplir con los criterios indicados en la rúbrica para maximizar tu puntuación en cada sección de la asignación.

Dada la complejidad de la tarea, lo más probable es que debas dividirla en diferentes fases y asegurarte de ir comprobando tus resultados en cada etapa.

Si tienes preguntas específicas o necesitas más detalles en cualquiera de los pasos, no dudes en preguntar. ¡Buena suerte!



https://snap.stanford.edu/data/#as
https://snap.stanford.edu/data/sx-stackoverflow.html


El dataset del Stack Overflow temporal network es una fuente rica para analizar las interacciones entre los usuarios de la comunidad de Stack Overflow. Los tipos de interacción como responder a preguntas, comentar en preguntas y comentar en respuestas podrían arrojar luz sobre la centralidad y la dispersión de influencia en este tipo de redes.

### 1) Depuración del dataset
- En primer lugar, necesitas descomprimir los archivos .gz y leer los datos en Python, posiblemente usando Pandas o NetworkX.
- Deberás determinar si necesitas todas las interacciones o si te centrarás en una subcategoría, como "respuestas a preguntas".

### 2) Medidas de Centralidad
- Este dataset es especialmente interesante para aplicar medidas de centralidad, ya que podría ayudarte a identificar usuarios clave en la comunidad de Stack Overflow.
- Podrías usar 'in-degree' para saber quiénes son los usuarios más consultados (a quienes más se les responde o comenta) y 'out-degree' para saber quiénes son los más activos en responder o comentar.

### 3) Modelo de Dispersión de Influencia
- Implementar un modelo como el Linear Threshold podría ayudarte a entender cómo una respuesta o comentario puede influir en otros usuarios a lo largo del tiempo.

### 4) Cálculo de la Dispersión de Influencia
- Usarás el modelo para evaluar cómo se propaga la influencia a partir de los 10 nodos más centrales identificados en cada tipo de interacción.
  
### 5) Correlación de Medidas de Centralidad
- Al comparar diferentes medidas de centralidad entre sí y contra la dispersión de influencia, podrás entender si las personas que son centrales en un aspecto (por ejemplo, responder preguntas) también lo son en otros (por ejemplo, comentar en respuestas).

### 6) Interpretación de Resultados
- En el contexto de Stack Overflow, una alta centralidad podría indicar expertos en la materia o usuarios muy activos que contribuyen significativamente a la comunidad.
- Una correlación fuerte entre diferentes medidas de centralidad podría sugerir que los usuarios activos en un tipo de interacción también suelen ser activos en otros, lo que podría ser útil para estrategias de gamificación o moderación del sitio.

Recuerda que este es un conjunto de datos muy grande, por lo que el rendimiento computacional y la memoria podrían ser una consideración. Podrías necesitar trabajar con un subconjunto de datos o emplear técnicas de optimización.