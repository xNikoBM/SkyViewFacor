# SkyViewFactor 

Sistema de segmentación por instancias utilizando **YOLOv8-Seg** para calcular el **Sky View Factor (SVF)** o **Factor de Visión del Cielo** en entornos urbanos de la Universidad Autónoma de Occidente.

El proyecto permite identificar automáticamente áreas de **cielo** y **estructuras urbanas** en imágenes capturadas dentro del campus universitario, generando máscaras de segmentación y calculando el porcentaje de cielo visible presente en cada escena.

---

# Objetivo del Proyecto

Desarrollar un pipeline de visión por computadora capaz de:

- Detectar y segmentar cielo y estructuras urbanas.
- Calcular automáticamente el **Sky View Factor (SVF)**.
- Analizar la relación entre morfología urbana, apertura del cielo y confort ambiental.
- Aplicar técnicas de **Procesamiento Digital de Imágenes** y **Deep Learning** en un contexto de sostenibilidad urbana.

---

#  Tecnologías Utilizadas

- Python
- YOLOv8-Seg
- Ultralytics
- OpenCV
- NumPy
- Matplotlib
- Roboflow
- Google Colab / Jupyter Notebook

---

# Arquitectura del Proyecto

El sistema implementa una arquitectura basada en **YOLOv8-Seg**, compuesta por:

- **Backbone** → extracción de características
- **Neck** → fusión multiescala
- **Head Segmentation** → generación de máscaras por instancia

## Flujo general del sistema

1. Captura de imágenes urbanas.
2. Preprocesamiento.
3. Etiquetado en Roboflow.
4. Entrenamiento del modelo YOLOv8-Seg.
5. Inferencia y segmentación.
6. Cálculo del SVF.
7. Visualización de resultados.

---

# Dataset

El dataset fue construido manualmente utilizando imágenes capturadas dentro de la Universidad Autónoma de Occidente.

## Clases utilizadas

-  Cielo
-  Estructuras

## Cantidad de imágenes

- 150 imágenes de estructuras
- 120 imágenes de cielo

## División del dataset

- 80% Train
- 10% Validation
- 10% Test

---

#  Preprocesamiento

Se aplicaron las siguientes técnicas:

- Redimensionamiento a `640x640`
- Normalización RGB
- Organización en formato YOLO
- Aplicación de filtro Gaussiano para reducción de ruido

---

#  Entrenamiento

Parámetros principales utilizados:

```python
epochs = 40
imgsz = 640
batch = 8
model = "yolov8s-seg.pt"
```

---

# Métricas Obtenidas

| Métrica | Resultado |
|---|---|
| Precision | 0.621 |
| Recall | 0.660 |
| F1-Score | ~0.640 |
| mAP@50 | 0.605 |
| mAP@50-95 | 0.397 |
| Tiempo de inferencia | ~15 ms |

---

# Cálculo del Sky View Factor

El SVF se calcula mediante la siguiente fórmula:

```math
SVF = \frac{Píxeles\ de\ cielo}{Píxeles\ totales\ de\ la\ imagen}
```

Donde:

- Numerador → cantidad de píxeles segmentados como cielo
- Denominador → total de píxeles de la imagen

---

#  Resultados

El modelo logra:

 Segmentar correctamente cielo y estructuras urbanas.  
 Generar máscaras binarias precisas.  
 Calcular automáticamente el porcentaje de cielo visible.  
 Procesar imágenes en tiempo real (~66 FPS).

---

#  Aplicaciones

Este proyecto puede utilizarse en:

- Estudios de microclima urbano
- Análisis de isla de calor urbana (ICU)
- Planeación urbana sostenible
- Evaluación de confort ambiental
- Smart Cities
- Sistemas de monitoreo ambiental

---

#  Posibles Mejoras

- Incrementar épocas de entrenamiento.
- Utilizar modelos YOLOv8 más grandes (`yolov8l-seg.pt`).
- Expandir el dataset.
- Agregar nuevas clases:
  - Árboles
  - Vegetación
  - Materiales urbanos
- Implementar análisis en video en tiempo real.

---

# Integrantes

- Niko Alejandro Bonilla Martinez
- David Alejandro Perez

---

# Universidad

**Universidad Autónoma de Occidente**  
Facultad de Ingeniería y Ciencias Básicas  
Procesamiento Digital de Imágenes

---

# Referencias

El proyecto se basa en investigaciones relacionadas con:

- Sky View Factor (SVF)
- Urban Heat Island (UHI)
- Segmentación por instancias
- YOLOv8
- Microclima urbano

---

# Repositorio

Si te gustó el proyecto, puedes darle una  al repositorio y apoyar el desarrollo.

GitHub:
https://github.com/xNikoBM/SkyViewFacor
