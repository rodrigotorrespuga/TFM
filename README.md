# Clasificación automática de preguntas mediante Deep Learning

Comparación de cinco enfoques para la clasificación automática de preguntas en lenguaje natural usando el dataset TREC Question Classification. El sistema predice la categoría semántica de una pregunta (persona, lugar, número, entidad, descripción o abreviatura) a partir de su texto.

---

## Descripción del proyecto

El objetivo principal es desarrollar un pipeline reproducible que permita comparar distintos modelos de complejidad creciente :

| Enfoque | Modelo |
|---|---|
| Machine Learning clásico | TF-IDF + Logistic Regression |
| Deep Learning recurrente | LSTM |
| Deep Learning recurrente | BiLSTM |
| Transformer (fine-tuning) | DistilBERT |
| Transformer (fine-tuning) | BERT |

Además de comparar el rendimiento (Accuracy, Precision, Recall, F1-Score), el proyecto analiza el efecto del *class-weighting* sobre la clase minoritaria ABBR, estudia la variabilidad de los mejores modelos con 5 semillas aleatorias y define un estandar para producción (accuracy > 90 % y macro F1 > 0,90).

---

## Dataset

**TREC Question Classification Dataset** — disponible públicamente en https://www.kaggle.com/datasets/thedevastator/the-trec-question-classification-dataset-a-longi/data.

---

## Requisitos

Python 3.10 o superior. Instala las dependencias con:

```bash
pip install -r requirements.txt
```

Se recomienda disponer de GPU (el notebook fue ejecutado en Google Colab con GPU T4).

---

## Ejecución

### En local

1. Clona el repositorio:
   ```bash
   git clone https://github.com/rodrigotorrespuga/TFM.git
   cd TFM
   ```
2. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Coloca `train.csv` y `test.csv` en la misma carpeta que el notebook.
4. Ejecuta el notebook.


### En Google Colab

Accede directamente al notebook con todas las salidas generadas:

https://colab.research.google.com/drive/1nCsJXYCBYkBHdzCbE4yMiCV0z3ebckC3?usp=sharing

Sube `train.csv` y `test.csv` mediante el panel de archivos de Colab o móntalo desde Google Drive antes de ejecutar.

---

## Reproducibilidad

- Semilla fija (`SEED = 42`) en todas las ejecuciones individuales.
- El análisis de variabilidad usa 5 semillas distintas para BERT y DistilBERT.

---

## Repositorio y recursos

- **GitHub:** https://github.com/rodrigotorrespuga/TFM.git
- **Notebook en Colab:** https://colab.research.google.com/drive/1byTAW6AUkNil8yhGx8jQMrG1QcYpaWYc?usp=sharing
- **Dataset (Kaggle):** https://www.kaggle.com/datasets/thedevastator/the-trec-question-classification-dataset-a-longi/data

