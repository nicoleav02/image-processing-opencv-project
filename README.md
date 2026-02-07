# Trabajo Integrador – Procesamiento de Imágenes

## Estructura del Proyecto

El proyecto está organizado de la siguiente manera:

Trabajo_Procesamiento_Imagenes/
├── Trabajo_Practico_Imagenes.ipynb   # Notebook con ejercicios 1 y 2
├── ejercicio3_interfaz.py            # Script con interfaz interactiva del ejercicio 3
├── README.md                         # Archivo explicativo (este documento)
├── imagenes_originales/              # Imágenes originales utilizadas como entrada
│   ├── figuras_geometricas.png
│   ├── imagen_juego_nueva.png
│   └── rostros.jpg
├── resultados/                       # Resultados de cada ejercicio
│   ├── ejercicio1/                   # Resultados de operaciones morfológicas y bordes
│   ├── ejercicio2/                   # Clasificación de figuras geométricas
│   └── ejercicio3/                   # Resultados de la detección interactiva y agudeza visual
├── templates/                        # Plantillas utilizadas para template matching
│   ├── template_objeto.png
│   ├── triangulo.png
├── haarcascade_frontalface_default.xml # Clasificador Haar Cascade para detección de rostros

---

##  Instrucciones de Instalación

Asegúrese de tener Python 3.8 o superior instalado.

Instalar las dependencias necesarias ejecutando:


---

##  Cómo Ejecutar Cada Ejercicio

- **Ejercicio 1 y 2**:
  - Abrir el archivo `Trabajo_Practico_Imagenes.ipynb` en Jupyter Notebook o JupyterLab.
  - Ejecutar las celdas correspondientes a cada ejercicio siguiendo el orden.

- **Ejercicio 3**:
  - Abrir el archivo `ejercicio3_interfaz.py` en un editor como VSCode.
  - Ejecutar el archivo desde la terminal:
    ```
    python ejercicio3_interfaz.py
    ```
  - La interfaz permite:
    - Cambiar entre diferentes templates (`t`).
    - Ajustar el umbral de detección dinámicamente.
    - Cambiar el método de comparación (`m`).
    - Guardar los resultados (`s`).
    - Salir (`q`).

---

##  Descripción Breve de las Técnicas Implementadas

### Ejercicio 1 – Limpieza y Detección de Bordes
- **Umbralización** para binarización de imágenes.
- **Operaciones morfológicas**: erosión, dilatación, apertura y cierre.
- **Detección de bordes**: Sobel (gradientes X e Y) y Canny (filtrado y doble umbralización).
- **Comparación** de diferentes tamaños de kernel (3x3, 5x5, 7x7) y métodos de detección.

### Ejercicio 2 – Clasificación de Figuras Geométricas
- **Detección de contornos** con `cv2.findContours`.
- **Clasificación** mediante `cv2.approxPolyDP` contando vértices.
- **Cálculo de características**:
  - Área (píxeles cuadrados).
  - Perímetro (píxeles).
  - Centroide (coordenadas de píxeles).
- **Conteo automático** de figuras por tipo.

### Ejercicio 3 – Interfaz Interactiva y Agudeza Visual
- **Template Matching** con `cv2.matchTemplate`.
- **Supresión de solapamientos** para evitar detecciones duplicadas.
- **Interfaz interactiva**:
  - Cambio de template y método en tiempo real.
  - Ajuste dinámico del umbral.
  - Guardado de resultados automáticos.

---

##  Enlace al Video Demostrativo

https://drive.google.com/file/d/1-tyKXVZhMhkxKfCBPdL3cXyKhgJZjKDW/view?usp=sharing


---

##  Notas Finales

- Las unidades de medición (área, perímetro y centroide) están expresadas en píxeles ya que se trabaja sobre imágenes digitales sin escala física real.
- Durante el desarrollo se enfrentaron y resolvieron problemas relacionados con la carga de imágenes (`NoneType`), rutas de archivos, manejo de ventanas interactivas de OpenCV y organización automática de resultados.


