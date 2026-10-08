# Clasificación de cultivares con el conjunto Wine

Este repositorio corresponde a la actividad R1-A2-S8 de Sofía. La pregunta que
guía el ejercicio es sencilla: ¿hasta qué punto trece mediciones químicas
permiten distinguir tres cultivares producidos en una misma región italiana?

El conjunto Wine contiene 178 observaciones y no tiene valores faltantes. Para
evitar que el resultado dependiera de una sola medida, comparé seis modelos con
la misma partición estratificada y validación cruzada de cinco pliegues:
regresión logística, árbol de decisión, bosque aleatorio, SVM, KNN y Naive
Bayes.

## Archivos principales

- `Sofia_ML_Wine_Colab.ipynb`: cuaderno para ejecutar el experimento en Colab.
- `analisis_ml_supervisado_sofia.py`: versión ejecutable del análisis.
- `metricas_prueba_sofia.csv`: resultados sobre las 45 muestras reservadas.
- `metricas_validacion_sofia.csv`: media y desviación en validación cruzada.
- Los PNG y JSON permiten comprobar las figuras y cada matriz de confusión.

## Ejecución local

```bash
python -m pip install -r requirements.txt
python analisis_ml_supervisado_sofia.py
```

La semilla es 23. El escalado está dentro de cada `Pipeline`, por lo que se
ajusta de nuevo en cada pliegue y no recibe información del conjunto de prueba.

## Lectura del resultado

El mejor puntaje puntual no debe interpretarse como una garantía general. El
conjunto es pequeño, sus clases están bien separadas y las muestras proceden de
una situación experimental concreta. Por eso el informe contrasta la prueba con
la validación cruzada y no propone usar el modelo como herramienta comercial.

Fuente de los datos: Aeberhard, S. y Forina, M. (1992), *Wine*, UCI Machine
Learning Repository, https://doi.org/10.24432/C5PC7J.
