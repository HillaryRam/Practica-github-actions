# Practica-github-actions
## 1. Descripción general
He elegido actions/checkout. Resuelve el problema de clonar el código del repositorio en el servidor virtual para poder trabajar con él. Se usa en prácticamente cualquier proyecto que requiera CI/CD.
## 2. Ubicación
Ruta del archivo: [.github/workflows/analisis.yml](https://github.com/HillaryRam/Practica-github-actions/tree/main/.github/workflows)
## 3. Explicaión detallada
```yaml
name: Analisis de Action Checkout

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout del codigo
        uses: actions/checkout@v4

      - name: Verificar archivos
        run: ls -R
```
| Etiqueta | Explicación |
| --- | --- |
| name | Define el nombre del workflow que aparecerá en la pestaña "Actions" de GitHub. |
| on | Define el evento disparador. El valor [push] indica que la acción se ejecuta cada vez que se sube código al repositorio. |
| jobs | Organiza el conjunto de tareas que se ejecutarán. Aquí se define el trabajo llamado build.|
| runs-on | Especifica la máquina virtual donde se ejecutará el código (en este caso, la versión más reciente de Ubuntu Linux). |
| steps | Es la secuencia de tareas. Incluye el uso de uses (para llamar a acciones creadas por otros) y run (para ejecutar comandos directamente en la consola).|
| Variables de entorno | En este workflow básico no se han requerido, pero permitirían configurar credenciales o parámetros dinámicos.|

## 4. Explicación de pasos
Paso 1: actions/checkout@v4 descarga el código fuente.

Paso 2: ls -R lista los archivos para confirmar que la descarga fue exitosa.
## 5. Ejecución
Se ejecuta automáticamente al hacer push.

### Evidencias de ejecución:
<img width="1084" height="479" alt="Captura de pantalla 2026-01-06 212801" src="https://github.com/user-attachments/assets/67cc78fb-0870-45a4-8163-e6840c372ab6" />

## 6. Conclusión
El análisis de esta GitHub Action demuestra que la automatización es vital para el desarrollo moderno. La acción actions/checkout es el punto de partida esencial, ya que permite que el entorno de ejecución sea una copia fiel de nuestro repositorio. Sin esta capacidad de "clonado automático", no sería posible realizar pruebas de software o despliegues continuos de forma eficiente.
