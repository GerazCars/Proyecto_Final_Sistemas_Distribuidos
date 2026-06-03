# Proyecto_Final_Sistemas_Distribuidos_CNN
En este repositorio encontrara todo lo solicitado del proyecto final CNN para el dataset flowers

## Descripción del Proyecto

El objetivo de este proyecto es analizar el impacto de diferentes técnicas de preprocesamiento de imágenes sobre el desempeño de una Red Neuronal Convolucional (CNN) para la clasificación automática de flores.

Se implementaron dos técnicas de procesamiento digital de imágenes vistas durante el curso:

1. Filtro de Mediana.
2. Ecualización del Histograma en el espacio de color HSV.

Cada técnica fue aplicada a todas las imágenes del dataset antes del entrenamiento de la CNN para evaluar su influencia en las métricas de clasificación.

---

## Dataset Utilizado

Flowers Recognition Dataset

Clases:

* Daisy
* Dandelion
* Rose
* Sunflower
* Tulip
---

## Técnicas Implementadas

### 1. Filtro de Mediana

El filtro de mediana reemplaza cada píxel por la mediana de sus vecinos dentro de una ventana determinada.

#### Objetivo

* Reducir ruido en las imágenes.
* Conservar bordes importantes.
* Mantener la forma de pétalos y hojas.

#### Beneficio esperado

Mejorar la calidad visual de la imagen eliminando pequeñas variaciones que podrían afectar el aprendizaje de la CNN.

---

### 2. Ecualización del Histograma en HSV

La imagen es convertida al espacio de color HSV y posteriormente se aplica ecualización del histograma al canal V (brillo).

#### Objetivo

* Mejorar el contraste.
* Resaltar detalles visuales.
* Mantener la información cromática de las flores.

#### Beneficio esperado

Facilitar la identificación de patrones visuales por parte de la CNN.

---

## Estructura del Proyecto

```text
Proyecto/
│
├── imagenes/
│
├── Proyecto_Final_RGB_Filtro_Mediana.ipynb
│
├── Proyecto_Final_RGB_Flowers.ipynb
│
├── Proyecto_Final_RGB_HSV.ipynb
│
├── README.md
│
├── preprocesamiento_HSV.ipynb
│
├── preprocesamiento_Filtro_Mediana.ipynb
│
└── Presentacion_Proyecto_Final_CNN.pptx
```

---

## Requisitos

## Obtención del Dataset

Antes de ejecutar los scripts de preprocesamiento es necesario descargar el conjunto de datos utilizado en el proyecto.

Dataset utilizado:

https://www.kaggle.com/datasets/alxmamaev/flowers-recognition

### Pasos

1. Ingresar al enlace del dataset en Kaggle.
2. Descargar el archivo comprimido (.zip).
3. Extraer el contenido del archivo.
4. Subir la carpeta `flowers` a tu Google Drive.
5. Verificar que la estructura de carpetas sea la siguiente:

```text
flowers/
│
├── daisy
├── dandelion
├── rose
├── sunflower
└── tulip
```

---
## Montar tu Google Drive en Google Colab

Abre Google Colab

Fuente:

https://colab.research.google.com/

Montar Google Drive

```python
from google.colab import drive
drive.mount('/content/drive')
```

---
## Entrenamiento de la CNN

1. Abrir el notebook `Proyecto_Final_RGB_Flowers.ipynb`.
2. Modificar la variable de ruta del dataset a tu google drive.

```python
DATASET_DIR = "/content/drive/MyDrive/flowers/"
```
4. Ejecutar todas las celdas del entrenamiento utilizando:

   * Dataset original (flowers/).
  
5. Realizar y Guardar el resultado de una Prueba Interactiva de la sección 8. del Entrenamiento de la CNN.

6. Registrar las métricas obtenidas en el entrenamiento.

Métricas evaluadas:
* Accuracy
* Precision
* Recall
* F1-Score
* Matriz de Confusión
---
---

7. Abrir el notebook `preprocesamiento_Filtro_Mediana.ipynb`.
8. Modificar la variable de ruta del dataset original a tu google drive.

```python
input_dir = "/content/drive/MyDrive/flowers"
```
9. Modificar la variable de ruta del dataset de salida a tu google drive.

```python
output_dir = "/content/drive/MyDrive/flowers_preprocesadas_Filtro_Mediana"
```
10. Ejecutar todas las celdas del preprocesamiento_Filtro_Mediana.ipynb

Resultado:

```text
flowers_preprocesadas_Filtro_Mediana/
│
├── daisy
├── dandelion
├── rose
├── sunflower
└── tulip
```
11. Regresar al notebook `Proyecto_Final_RGB_Flowers.ipynb`.
12. Modificar la variable de ruta del dataset a tu google drive.

```python
DATASET_DIR = "/content/drive/MyDrive/flowers_preprocesadas_Filtro_Mediana/"
```
13. Ejecutar todas las celdas del entrenamiento utilizando:

   * Dataset procesado con filtro de mediana (flowers_preprocesadas_Filtro_Mediana/).

14. Realizar y Guardar el resultado de una Prueba Interactiva de la sección 8. del Entrenamiento de la CNN.

15. Registrar las métricas obtenidas en el entrenamiento.

Métricas evaluadas:
* Accuracy
* Precision
* Recall
* F1-Score
* Matriz de Confusión
---
---

16. Abrir el notebook `preprocesamiento_HSV.ipynb`.
17. Modificar la variable de ruta del dataset original a tu google drive.

```python
input_dir = "/content/drive/MyDrive/flowers"
```
18. Modificar la variable de ruta del dataset de salida a tu google drive.

```python
output_dir = "/content/drive/MyDrive/flowers_preprocesadas_HSV"
```
19. Ejecutar todas las celdas de preprocesamiento_HSV.ipynb

Resultado:

```text
flowers_preprocesadas_HSV/
│
├── daisy
├── dandelion
├── rose
├── sunflower
└── tulip
```
20. Regresar al notebook `Proyecto_Final_RGB_Flowers.ipynb`.
21. Modificar la variable de ruta del dataset a tu google drive.

```python
DATASET_DIR = "/content/drive/MyDrive/flowers_preprocesadas_HSV/"
```
22. Ejecutar todas las celdas del entrenamiento utilizando:

   * Dataset procesado con equalización HSV (flowers_preprocesadas_HSV/).

23. Realizar y Guardar el resultado de una Prueba Interactiva de la sección 8. del Entrenamiento de la CNN.

24. Registrar las métricas obtenidas en el entrenamiento.

Métricas evaluadas:
* Accuracy
* Precision
* Recall
* F1-Score
* Matriz de Confusión
---
---

## Comparación Visual

| Imagen Original | Filtro de Mediana | Ecualización HSV |
|----------------|------------------|------------------|
| ![](imagenes/original.jpg) | ![](imagenes/median.jpg) | ![](imagenes/hsv.jpg) |

### Observaciones

- El filtro de mediana reduce ruido conservando los bordes principales de pétalos y hojas.
- La ecualización HSV mejora el contraste y resalta detalles visuales manteniendo la información de color.

## Comparación de Resultados

| Modelo Original | Filtro de Mediana | Ecualización HSV |
|----------------|------------------|------------------|
| ![](imagenes/original_matriz_confusión.jpg) | ![](imagenes/mediana_matriz_confusión.jpg) | ![](imagenes/hsv_matriz_confusión.jpg) |

### Observaciones

- El modelo original obtuvo un Accuracy de 75%, sirviendo como referencia para evaluar el impacto de las técnicas de preprocesamiento.
- El Filtro de Mediana redujo el Accuracy a 70%, indicando que la eliminación de detalles visuales afectó negativamente la capacidad de clasificación de la CNN.
- La Ecualización del Histograma en HSV mantuvo un Accuracy de 75%, igualando el desempeño del modelo original.
- El modelo con HSV mostró una mejora importante en la clasificación de la clase Tulip, alcanzando un Recall de 0.81 frente a 0.71 del modelo original.
- La clase Rose presentó la mayor dificultad de clasificación en los tres experimentos, siendo confundida frecuentemente con Tulip debido a similitudes de color y forma.
- La matriz de confusión muestra que la mayoría de las predicciones correctas se concentran sobre la diagonal principal, indicando un desempeño adecuado del modelo.
- La Ecualización HSV permitió conservar mejor la información visual relevante que el Filtro de Mediana, obteniendo un equilibrio más favorable entre contraste y preservación de características.

---
---

## Conclusiones

Este proyecto permitió evaluar el efecto de diferentes técnicas de preprocesamiento sobre el desempeño de una CNN para clasificación de flores.

Mediante la comparación de Accuracy, Precision, Recall, F1-Score y Matriz de Confusión fue posible determinar qué técnica proporcionó una mejor representación visual para el proceso de clasificación.

Los resultados obtenidos muestran que el preprocesamiento puede influir significativamente en la capacidad de aprendizaje de una red neuronal, mejorando o degradando su desempeño dependiendo de la técnica aplicada.

---
---

## Autor

Nombre: Gerardo Alejandro Carrillo Aguirre

Matricula: 42208760

Materia: Sistemas Distribuidos

Fecha: 05 de Junio 2026
