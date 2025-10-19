# Evaluación y Comparación de Modelos Regularizados para Scoring Crediticio

### Curso: Machine Learning – Módulo 11  
**Autora:** Mary Huaiquin 
**Fecha:** Octubre 2025  
**Institución:** Kibernum Capacitación – Data Science & Machine Learning  
**Herramientas:** Python 3, Scikit-learn, Pandas, Matplotlib, Seaborn, Google Colab  

---

## 1. Descripción general del proyecto

Este proyecto corresponde a la Evaluación Modular 11 del curso de Machine Learning, cuyo objetivo fue aplicar modelos de clasificación regularizados para predecir el **riesgo crediticio** de clientes a partir de sus características personales y financieras.  

Se desarrollaron dos modelos: **Regresión Logística Lasso (L1)** y **Regresión Logística Ridge (L2)**, utilizando el dataset público **“credit-g”** disponible en **OpenML**.  

El propósito fue comparar el desempeño, la interpretabilidad y el impacto de la regularización sobre las variables predictoras.  

---

## 2. Objetivos específicos

- Entrenar modelos de clasificación con regularización L1 (Lasso) y L2 (Ridge).  
- Analizar el efecto de la regularización en la selección de variables.  
- Evaluar el desempeño mediante métricas de clasificación y curva ROC.  
- Comparar la interpretabilidad de ambos modelos.  
- Reflexionar sobre la aplicabilidad del modelo en contextos financieros reales.  

---

## 3. Descripción del dataset

**Fuente:** OpenML – Dataset “credit-g”  
**Observaciones:** 1000 registros  
**Clases:** Riesgo “bueno” (0) y “malo” (1)  
**Número de variables:** 20 (mixtas: categóricas y numéricas)  

Principales variables analizadas:
- `checking_status`: estado de cuenta corriente  
- `credit_history`: historial crediticio  
- `savings_status`: nivel de ahorros  
- `purpose`: motivo del crédito  
- `foreign_worker`: trabajador extranjero  

El preprocesamiento incluyó:
- Imputación de valores faltantes  
- Codificación de variables categóricas con OneHotEncoder  
- Escalado de variables numéricas  
- División en conjuntos de entrenamiento (80%) y prueba (20%)  

---

## 4. Modelos aplicados

| Modelo | Tipo de Regularización | Características principales |
|--------|------------------------|-----------------------------|
| **Lasso (L1)** | Penaliza la suma de los valores absolutos de los coeficientes. | Elimina variables irrelevantes, mejorando interpretabilidad. |
| **Ridge (L2)** | Penaliza la suma de los cuadrados de los coeficientes. | Reduce la varianza y mejora la estabilidad del modelo. |

---

## 5. Métricas de evaluación

| Métrica | Lasso | Ridge |
|----------|--------|--------|
| Accuracy | 0.78 | 0.78 |
| Precision (Clase 1) | 0.67 | 0.67 |
| Recall (Clase 1) | 0.53 | 0.53 |
| F1-Score (Clase 1) | 0.59 | 0.59 |
| AUC | **0.8127** | 0.8055 |

Conclusión técnica: ambos modelos muestran un rendimiento similar, con una leve ventaja de **Lasso en AUC** y mayor interpretabilidad.

---

## 6. Análisis de resultados

- Ambos modelos clasifican correctamente 32 de 60 clientes de riesgo.  
- La curva ROC muestra un buen desempeño, con Lasso ligeramente superior.  
- **Lasso** elimina variables irrelevantes, lo que simplifica la explicación del modelo.  
- **Ridge** mantiene todas las variables, favoreciendo estabilidad pero reduciendo interpretabilidad.  

Variables más influyentes detectadas:
- `checking_status_no checking` → alto riesgo.  
- `credit_history_critical/other` → historial crítico.  
- `purpose_education` → créditos menos seguros.  
- `foreign_worker_yes` → riesgo adicional.  
- `savings_status_>=1000` → factor protector.  

---

## 7. Visualizaciones sugeridas

El análisis se complementa con:
- **Curva ROC** → evaluación del desempeño del modelo.  
- **Matriz de confusión** → errores de clasificación.  
- **Importancia de variables (coeficientes)** → para comparar Lasso vs Ridge.  

---

## 8. Reflexión personal y aprendizajes

Este proyecto permitió comprender cómo la **regularización controla la complejidad del modelo**, evitando sobreajuste y mejorando la interpretabilidad.  
Aprendí que **Lasso** es útil cuando se busca simplicidad y selección automática de variables, mientras que **Ridge** es más apropiado cuando se desea conservar toda la información.  

Además, comprendí que en contextos financieros, la interpretabilidad es esencial para justificar decisiones automatizadas, por lo que un modelo más explicable puede ser preferible a uno con una pequeña mejora en rendimiento.

---

## 9. Archivos del repositorio

```
📁 Scoring_Crediticio_Lasso_Ridge/
│
├── EM5_MHZ.ipynb                       # Notebook principal (Google Colab)
├── Informe__Scoring_Crediticio_MHZ.pdf   # Informe técnico completo
└── README_Credit_Scoring_MHZ.md        # Descripción del proyecto (este archivo)
```

---

## 10. Conclusiones generales

- Lasso y Ridge ofrecen resultados similares, pero difieren en interpretabilidad.  
- Lasso es preferible cuando se requiere transparencia y selección de variables.  
- Ridge es más estable en presencia de colinealidad.  
- La combinación de análisis técnico y reflexión ética es clave en proyectos de scoring crediticio.

---

## 11. Referencias

- Dataset: OpenML “credit-g”.  
- Librerías: scikit-learn, pandas, numpy, matplotlib, seaborn.  
- Curso: Machine Learning – Kibernum Capacitación, 2025.
  
## 12. Entorno y versiones utilizadas

Este proyecto fue desarrollado en **Python 3.10** (Google Colab) con las siguientes versiones de librerías para asegurar la reproducibilidad:

- numpy == 1.26.4  
- pandas == 2.2.2  
- scikit-learn == 1.4.2  
- matplotlib == 3.8.4  
- seaborn == 0.13.2  
- openml == 0.14.2  
- joblib == 1.4.2  
