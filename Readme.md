# Clasificación Automática de Tickets

## Índice
- [Introducción](#introducción)
  - [Métodos Utilizados](#métodos-utilizados)
  - [Tecnologías](#tecnologías)
- [Descarga y Configuración](#descarga-y-configuración)
  - [Requisitos Previos](#requisitos-previos)
  - [Cómo Ejecutar](#cómo-ejecutar)
- [Declaración del Problema](#declaración-del-problema)
  - [Objetivo Comercial](#objetivo-comercial)
  - [Preparación de Datos](#preparación-de-datos)
  - [Construcción y Evaluación del Modelo](#construcción-y-evaluación-del-modelo)
  - [Conclusiones](#conclusiones)

---

## Introducción

La **Clasificación Automática de Tickets** es un proyecto basado en técnicas de Procesamiento de Lenguaje Natural (NLP) y aprendizaje automático (ML) diseñado para automatizar la asignación de tickets de soporte al departamento adecuado. Esto mejora la eficiencia y reduce el tiempo de respuesta en la gestión de tickets.

### Métodos Utilizados

- **Preprocesamiento de texto**: Tokenización, eliminación de stopwords, lematización.
- **Vectorización**: Técnicas como TF-IDF y embeddings para representar texto.
- **Modelos de Clasificación**: Modelos supervisados como Regresión logistica y Random Forest.
- **Evaluación**: Métricas como precisión, recall, F1-score y matriz de confusión.

### Tecnologías

Este proyecto utiliza las siguientes tecnologías:
- **Python**: Lenguaje principal de desarrollo.
- **Bibliotecas**: 
  - `scikit-learn`
  - `spaCy`
  - `NLTK`
  - `pandas`
  - `numpy`
- **Entorno de ejecución**: Jupyter Notebook o cualquier IDE compatible con Python.

---

## Descarga y Configuración

### Requisitos Previos

1. Descargar el dataset del siguiente enlace

https://drive.google.com/file/d/1AWGcwWxYTH1D7jnGWEt2NHQrr-tkqrKa/view?usp=drive_link

2. Clonar este repositorio

```
git clone <GITHUB_REPO_URL>
```

3. Abra el archivo notebook ** *.ipynb** en Anaconda.

## Declaración del problema

### Objetivo Comercial

Automatizar el proceso de clasificación de tickets para:

- Reducir tiempos de asignación.
- Mejorar la precisión en la categorización.
- Optimizar la experiencia del cliente al minimizar errores humanos.

### Preparación de Datos
1. Importar datos: Leer el dataset desde un archivo en formato .json.
2. Limpieza de datos: Eliminación de duplicados y valores nulos. Normalización del texto.
3. Análisis exploratorio:Identificación de categorías desequilibradas. Visualización de distribuciones.

### Construcción y Evaluación del Modelo

División de datos de entrenamiento y prueba: Se realizó la división de un conjunto de datos en dos subconjuntos: datos de entrenamiento y datos de prueba, utilizando la función train_test_split de la biblioteca scikit-learn
Se asigno el 20% de los datos que se asignarán al conjunto de prueba (test) y el 80% al conjunto de entrenamiento (train). Se uso un random_state 40 es decir una semilla para generar aleatoriedad reproducible. Esto asegura que al ejecutar el código varias veces, la división de datos sea siempre la misma.

Se definen un conjunto de hiperparámetros para un modelo de Regresión Logística, Decisión tree y otros.

Las métricas utilizadas para evaluar los modelos son:

-  Precisión: La proporción de resultados verdaderos (tanto verdaderos positivos como verdaderos negativos) entre el número total de casos examinados.
-  Precisión: La proporción de verdaderos positivos entre el número total de casos previstos como positivos.
-  Recordatorio: Proporción de verdaderos positivos entre el número total de casos positivos reales.
-  Puntuación F1: La media armónica de precisión y recuperación.
-  Puntuación AUC ROC: el área bajo la curva característica operativa del receptor (ROC), que mide el rendimiento del modelo en diferentes umbrales de clasificación.

Con base en estas métricas, los modelos Logistic Regression obtuvo el mejor desempeño, con alta precisión, exactitud, recuperación, puntaje F1 y puntaje ROC AUC. 


## Conclusiones

El modelo seleccionado logra clasificar los tickets con una precisión promedio del 0.91%. Implementar la solución en un entorno productivo puede reducir significativamente el tiempo de gestión de tickets.

### Futuras mejoras incluyen:
- Uso de embeddings preentrenados como BERT.
- Integración del modelo con un sistema de gestión de tickets en tiempo real.
