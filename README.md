# Autoencoder-based Classification of Astronomical Alerts

## Autores
- Agustín González Hidalgo
- Felipe Poblete Contreras

##  Tutor
-  Sebastián Guzmán

## Descripción del problema
El proyecto busca mejorar la clasificación de alertas astronómicas del Zwicky Transient Facility (ZTF), un observatorio dedicado al estudio del cielo nocturno. Estas alertas incluyen imágenes de referencia, ciencia y diferencia, y su clasificación precisa es esencial para identificar fenómenos transitorios como supernovas. La motivación es desarrollar un modelo que no solo reconstruya imágenes astronómicas de manera efectiva, sino que también clasifique secuencialmente las alertas con alta precisión.

## Objetivos del proyecto
1. Implementar un AutoEncoder convolucional para reconstruir imágenes de alertas.
2. Desarrollar un clasificador basado en redes de percepción multicapa (MLP) utilizando el embedding del AutoEncoder.
3. Mejorar la clasificación incorporando una capa recurrente para capturar patrones temporales en las alertas.

## Base de datos
Los datos provienen de conjuntos de alertas del ZTF, con imágenes de 21x21 píxeles. Se utilizaron dos datasets: `stamp_dataset_28.pkl` y `stamp_dataset_21_new.pkl`. El último se ajusta mejor a la arquitectura diseñada para este proyecto.

## Pre-procesamiento de datos
El preprocesamiento inicial se centró en la visualización y análisis de los datos. Se prevé la incorporación de técnicas de normalización y *data augmentation* para mejorar la generalización en fases posteriores.

## Algoritmos utilizados
Se implementaron tres versiones de modelos:
- **Autoencoder_reconstructor_v1**: Reconstrucción de imágenes astronómicas utilizando un AutoEncoder convolucional.
- **Autoencoder_clasificador_v1**: Clasificación de imágenes mediante un MLP acoplado al AutoEncoder sin congelar los pesos, lo cual generó problemas de reconstrucción.
- **Autoencoder_clasificador_v2**: Versión con congelación de los pesos del AutoEncoder durante la fase de clasificación para preservar la calidad de reconstrucción.

## Salidas deseadas y optimización
Las salidas incluyen:
- Reconstrucción precisa de imágenes astronómicas.
- Clasificación de alertas en categorías específicas.
La optimización se realiza mediante funciones de pérdida como RMSE para la reconstrucción y *Cross Entropy* para la clasificación.

## Criterios de detención y ajuste de parámetros
Se utiliza *early stopping* con diferentes configuraciones de paciencia para evitar el sobreajuste. Los parámetros a ajustar incluyen tasa de aprendizaje, número de épocas y tamaño de batch.

## Software
El desarrollo se realizó con las siguientes herramientas:
- **PyTorch**: Para la implementación de modelos de aprendizaje profundo.
- **Matplotlib**: Para visualización de métricas de rendimiento.
- **Scikit-learn**: Para preprocesamiento de datos y evaluación de modelos.
- **UMAP**: Para la proyección y análisis de los embeddings.

## Resultados esperados
- Una mejora en la precisión de la clasificación.
- Representación visual clara de la segmentación de las clases mediante UMAP.
Los resultados se presentarán mediante tablas y gráficos de métricas de precisión y proyecciones de embeddings.

## Estimación de recursos computacionales
Se realizarán simulaciones en Google Colab, utilizando GPUs para reducir el tiempo de entrenamiento. Se estima un total de 50 simulaciones.

##  Ejecución código
Para ejecutar los notebooks dispuestos en este repositorio, es necesario contar con el dataset `stamp_dataset_28.pkl`. Este debe estar en local o en Google Drive.
1.- Contar con el path del dataset.
2.- Modificar en la sección "Datos" el path asociado según la plataforma esté usando.
3.- Ejecutar el resto del código.
   

