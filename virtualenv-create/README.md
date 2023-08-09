# Hand-Tracking

## Instalación y Uso del Entorno Virtual en Python

Este proyecto te guiará a través del proceso de creación de un entorno virtual en Python desde una instalación limpia. También aprenderás cómo instalar y utilizar las librerías necesarias para el proyecto utilizando el archivo `requirements.txt`.

## Requisitos Previos

Antes de comenzar, asegúrate de tener lo siguiente instalado en tu sistema:

- Python (versión 3.x recomendada): Puedes descargar la última versión de Python desde el sitio web oficial: https://www.python.org/downloads/

## Pasos para Crear y Utilizar el Entorno Virtual

**Paso 1: Clonar el Repositorio (opcional)**

Si estás utilizando un repositorio Git para tu proyecto, puedes clonarlo en tu máquina local. Si no estás utilizando Git, simplemente crea una carpeta para tu proyecto y continúa con los siguientes pasos.

```
git clone URL_DEL_REPOSITORIO.git
cd Hand-Tracking
```

**Paso 2: Instalar la libreria virtualenv**

Dentro de tu terminal.

Con pip:

```
pip install virtualenv
```

**Paso 3: Crear el Entorno Virtual**

Dentro del directorio de tu proyecto, crea un nuevo entorno virtual utilizando `virtualenv`. El siguiente comando creará una carpeta llamada `venv` en tu directorio de proyecto, que contendrá el entorno virtual.

```
virtualenv venv
```

**Paso 4: Activar el Entorno Virtual**

En sistemas basados en Unix (Linux o macOS), activa el entorno virtual con el siguiente comando:

```
venv\Scripts\activate
```

Después de activar el entorno virtual, verás que el indicador de la terminal cambia, mostrando el nombre del entorno virtual actual.

**Paso 5: Habilitar la Ejecución de Scripts en PowerShell (Windows)**

Si estás utilizando PowerShell en Windows y encuentras el error de ejecución de scripts deshabilitados, debes cambiar la política de ejecución de scripts en PowerShell. Sigue estos pasos:

1. Abre una nueva ventana de PowerShell con privilegios de administrador. Para hacerlo, busca "PowerShell" en el menú de inicio, haz clic derecho sobre "Windows PowerShell" y selecciona "Ejecutar como administrador". A continuación, acepta la confirmación de permisos que aparezca.

2. Verifica la política actual de ejecución de scripts en PowerShell. Para hacerlo, ejecuta el siguiente comando:

```powershell
Get-ExecutionPolicy
```

Te mostrará la política actual. Si ves "Restricted", eso significa que los scripts están deshabilitados.

3. Cambia la política de ejecución de scripts. Puedes hacerlo con el siguiente comando:

```powershell
Set-ExecutionPolicy RemoteSigned
```

`RemoteSigned` permite la ejecución de scripts locales y de scripts remotos firmados por un editor confiable. Esta configuración es bastante segura y es la opción recomendada para desarrolladores.

4. Aparecerá un mensaje de confirmación preguntándote si deseas cambiar la política de ejecución. Presiona "S" y luego Enter para aceptar.

5. Intenta nuevamente activar el entorno virtual usando el siguiente comando:

```powershell
venv\Scripts\Activate.ps1
```

Con este cambio en la política de ejecución de scripts, deberías poder activar el entorno virtual sin recibir el mensaje de error.

Recuerda que cambiar la política de ejecución de scripts puede tener implicaciones de seguridad, así que asegúrate de descargar y ejecutar scripts solo de fuentes confiables.

**Paso 5: Instalar las Librerías desde `requirements.txt`**

Una vez que hayas activado el entorno virtual, dentro de este entorno, instala las librerías especificadas en el archivo `requirements.txt`. Esto asegurará que todas las librerías necesarias para tu proyecto se instalen en este entorno.

```
pip install -r requirements.txt
```

**Paso 6: Desactivar el Entorno Virtual**

Cuando hayas terminado de trabajar en tu proyecto y quieras salir del entorno virtual, simplemente escribe:

```
deactivate
```

El entorno virtual se desactivará, y volverás al entorno global de Python de tu sistema.

## ¡Listo para trabajar en tu proyecto Hand-Tracking!

Hecho