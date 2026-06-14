# Examen — Regresión sobre Retail Sales Dataset
**Autor:** Marco Brante  
**Dataset:** [Retail Sales Dataset — Kaggle](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset)

---

## Descripción

Análisis completo de un dataset de ventas de retail con el objetivo de predecir el monto total de una transacción (`Total Amount`). El trabajo cubre limpieza de datos, exploración, implementación de modelos de regresión y evaluación comparativa.

---

## Estructura del repositorio

```
├── Examen_Retail_Sales_Marco_Brante.ipynb   # Notebook principal
├── retail_sales_dataset.csv                 # Dataset original
└── README.md
```

---

## Contenido del notebook

| Sección | Descripción |
|---|---|
| 0 — Configuración | Librerías y funciones reutilizables |
| 1 — Carga y descripción | Inspección inicial del dataset |
| 2 — Limpieza de datos | Duplicados, nulos, tipos, outliers y data leakage |
| 3 — EDA | Visualizaciones univariadas, multivariadas y mapa de correlaciones |
| 4 — Preparación | Codificación de variables y split train/test |
| 5 — Modelos base | Decision Tree y Random Forest con validación cruzada |
| 6 — Optimización | GridSearchCV para ambos modelos |
| 7 — Evaluación | Métricas, residuos, importancia de features y reflexión de escenarios |
| 8 — Conclusiones | Análisis comparativo y recomendación final |

---

## Modelos implementados

- **Decision Tree Regressor** — base y optimizado con GridSearchCV
- **Random Forest Regressor** — base y optimizado con GridSearchCV

### Métricas obtenidas

| Modelo | RMSE | R² |
|---|---|---|
| Decision Tree (base) | 768.47 | -1.0174 |
| Random Forest (base) | 566.46 | -0.0961 |
| Decision Tree (optimizado) | 550.49 | -0.0352 |
| Random Forest (optimizado) | 544.10 | -0.0113 |

> Los R² negativos son una consecuencia esperada del diseño del experimento: las variables `Quantity` y `Price per Unit` fueron excluidas por generar fuga de datos (`Total Amount = Quantity × Price per Unit`), dejando solo features de perfil de cliente y temporalidad que no tienen relación lineal con el target. Ver sección 2.6 y 8.2 para el análisis completo.

---

## Tecnologías utilizadas

- Python 3
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- Google Colab

---

## Cómo ejecutar

**Opción 1 — Google Drive**
1. Abrir el notebook en [Google Colab](https://colab.research.google.com/)
2. Montar Google Drive y ajustar la ruta del dataset en la sección 1.1
3. Ejecutar todas las celdas en orden (`Runtime → Run all`)

**Opción 2 — Directamente desde este repositorio**
1. Clonar el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/tu-repo.git
   ```
2. Abrir el notebook en Google Colab o Jupyter y reemplazar la ruta de carga en la sección 1.1 por:
   ```python
   df = pd.read_csv('retail_sales_dataset.csv')
   ```
3. Ejecutar todas las celdas en orden (`Runtime → Run all`)
