
# Creación y Actualización de requirements.txt en Python

A continuación, te guiaré en la creación y actualización de un archivo `requirements.txt` en Python, así como en los pasos para instalar las librerías desde ese archivo y desactivar el entorno virtual. Sigue estos pasos:

## Paso 1: Instalar las Librerías

Dentro del entorno virtual, puedes instalar las librerías necesarias para tu proyecto utilizando `pip`. Supongamos que has instalado algunas librerías y ahora deseas generar el archivo `requirements.txt`:

```bash
pip freeze > requirements.txt
```

Esto creará un archivo `requirements.txt` que enumera todas las librerías instaladas en tu entorno virtual junto con sus versiones exactas.

## Paso 2: Actualizar las Librerías

Si añades, actualizas o eliminas librerías en tu proyecto, necesitas actualizar el archivo `requirements.txt`. Puedes hacerlo manualmente o utilizando un comando similar al que se usó para crearlo:

```bash
pip freeze > requirements.txt
```

Esto sobrescribirá el archivo `requirements.txt` con las librerías y versiones actuales.

## Paso 3: Instalar Librerías desde requirements.txt

Cuando desees instalar las librerías desde el archivo `requirements.txt` en otro entorno, puedes hacerlo con el siguiente comando:

```bash
pip install -r requirements.txt
```

Esto instalará todas las librerías y versiones exactas que están especificadas en el archivo.

Recuerda que estos pasos te ayudarán a mantener un control más preciso de las librerías utilizadas en tu proyecto, lo que es especialmente útil cuando trabajas en equipo o cuando necesitas reproducir el entorno en otro lugar.
