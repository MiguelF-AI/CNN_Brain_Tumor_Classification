# Clasificación de Tumores Cerebrales mediante MRI (Custom CNN)

Este proyecto implementa una Red Neuronal Convolucional (CNN) diseñada desde cero para clasificar imágenes de resonancia magnética (MRI) en cuatro categorías: **Glioma, Meningioma, Sin Tumor y Tumor Pituitario.**

Lo más destacado de este proyecto es alcanzar un **88% de precisión (Accuracy)** utilizando una arquitectura propia, sin recurrir a Transfer Learning, aplicando técnicas avanzadas de optimización y regularización.

##  Características del Proyecto

- **Arquitectura Personalizada:** Diseñada con bloques Convolucionales, Batch Normalization y Global Average Pooling para reducir la complejidad y evitar el sobreajuste.
- **Data Augmentation:** Aplicación de transformaciones aleatorias (rotación, zoom, giros) para mejorar la robustez del modelo.
- **Manejo de Desbalanceo:** Uso de **Class Weights** para priorizar el aprendizaje en categorías difíciles como Glioma y Meningioma.
- **Optimización Dinámica:** Implementación de `ReduceLROnPlateau` para ajustar la tasa de aprendizaje y `EarlyStopping` para evitar el overfitting.

##  Resultados del Modelo

Después de varias iteraciones de optimización, el modelo alcanzó las siguientes métricas en el conjunto de test:

| Clase | Precision | Recall | F1-Score |
|-------|-----------|--------|----------|
| Glioma | 0.90 | 0.79 | 0.84 |
| Meningioma | 0.91 | 0.75 | 0.83 |
| No Tumor | 0.81 | 0.99 | 0.89 |
| Pituitary | 0.91 | 0.98 | 0.95 |

**Accuracy Global: 88%**

### Análisis de resultados:
- El modelo es extremadamente confiable detectando cerebros sanos y tumores pituitarios (Recall > 98%).
- Se logró equilibrar la detección de Gliomas y Meningiomas mediante el ajuste de pesos de clase, superando las dificultades iniciales de clasificación.

##  Estructura del Repositorio

- `notebook-clasificacion-tumores.ipynb`: Notebook completo con el proceso de carga, aumento de datos, entrenamiento y evaluación.
- `modelo_tumores_cerebrales.keras`: Archivo del modelo entrenado listo para ser cargado y utilizado para inferencia.

##  Requisitos

Para ejecutar este proyecto, necesitarás las siguientes librerías:

```bash
pip install tensorflow numpy matplotlib seaborn scikit-learn
