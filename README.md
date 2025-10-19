# Proyecto: Evaluación y Comparación de Modelos Regularizados para Scoring Crediticio

**Autora:** Mary Huaiquin  
**Curso:** Machine Learning – Módulo 5  
**Plataforma:** Google Colab  
**Lenguaje:** Python 3  

---

## Estructura del Repositorio

| Archivo / Carpeta | Descripción |
|--------------------|-------------|
| `EM5_MHZ.ipynb` | Notebook principal con el desarrollo completo del modelo de scoring crediticio. Incluye preprocesamiento, entrenamiento, regularización Lasso y Ridge, métricas, curva ROC y matriz de confusión. |
| `Informe_Scoring_Crediticio_MHZ.docx` | Informe técnico extendido con análisis detallado, tablas comparativas y conclusiones profesionales. |
| `README_Credit_Scoring_MHZ.md` | Descripción general del proyecto. |

---

## S – Situation

Este proyecto corresponde a la **Evaluación Modular 7** del curso de Machine Learning, cuyo objetivo fue **desarrollar un modelo predictivo de riesgo crediticio** utilizando regresión logística regularizada.

El dataset utilizado, **“credit-g”** (OpenML), contiene 1000 registros de clientes con información financiera, historial crediticio y características socioeconómicas.  
El problema consistía en predecir si un cliente representaba un **riesgo “bueno” o “malo”**, aplicando y comparando **regularización L1 (Lasso)** y **L2 (Ridge)** para mejorar la estabilidad y la interpretabilidad del modelo.

---

## T – Task

Las tareas principales incluyeron:

1. Cargar y explorar el dataset, identificando las variables relevantes.  
2. Aplicar preprocesamiento (imputación, codificación categórica, escalado).  
3. Entrenar dos modelos de **regresión logística regularizada (Lasso y Ridge)**.  
4. Evaluar su desempeño mediante métricas como Accuracy, Recall, F1-score y AUC.  
5. Visualizar resultados a través de la **matriz de confusión** y la **curva ROC**.  
6. Analizar las variables más influyentes y reflexionar sobre la aplicabilidad en contextos reales.

---

## A – Action

El notebook fue estructurado en bloques secuenciales que abarcan todas las etapas del flujo de trabajo de Machine Learning:

1. **Preprocesamiento de datos:**  
   Se aplicó OneHotEncoder para variables categóricas y StandardScaler para variables numéricas.  
   Los datos se dividieron en conjuntos de entrenamiento (80%) y prueba (20%).

2. **Entrenamiento de modelos:**  
   Se implementaron las versiones L1 y L2 de la regresión logística utilizando *scikit-learn*.  
   Se ajustaron hiperparámetros de regularización mediante validación cruzada.

3. **Evaluación:**  
   - Cálculo de métricas de rendimiento.  
   - Generación de la **matriz de confusión** para evaluar predicciones correctas e incorrectas.  
   - Trazado de la **curva ROC** para comparar la capacidad discriminativa (AUC).  

4. **Interpretación:**  
   - Análisis de los coeficientes de cada modelo para determinar qué variables influyen más en la predicción.  
   - Identificación de factores de riesgo como `checking_status_no checking` o `credit_history_critical/other`.  

---

## R – Result

Los modelos Lasso y Ridge alcanzaron un **accuracy de 0.78** y un **AUC promedio de 0.81**, evidenciando un rendimiento sólido y equilibrado.  

- **Lasso (L1)**: mostró mejor interpretabilidad, eliminando variables irrelevantes y destacando las más influyentes.  
- **Ridge (L2)**: ofreció mayor estabilidad frente a multicolinealidad, pero menor capacidad de simplificación.

Ambos modelos clasificaron correctamente 78% de los casos, con un balance adecuado entre precisión y recall.  
La curva ROC mostró una leve ventaja para Lasso (AUC = 0.8127 frente a 0.8055 en Ridge).

---

## Reflexión

Este proyecto me permitió consolidar conceptos sobre **regularización y evaluación de modelos**.  
Aprendí cómo la regularización L1 y L2 actúan sobre los coeficientes, reduciendo el sobreajuste y mejorando la interpretabilidad.  

En contextos financieros, comprendí que la **transparencia del modelo** es tan importante como su rendimiento.  
Por ello, considero que **Lasso** es más apropiado cuando se requiere justificar las decisiones de riesgo ante auditores o clientes.

Además, este trabajo reforzó la importancia de las métricas de validación y de la visualización (ROC y matriz de confusión) para interpretar correctamente el comportamiento del modelo.

---

## Entorno y versiones utilizadas

- Python: 3.10.12  
- NumPy: 1.26.4  
- Pandas: 2.2.2  
- Scikit-learn: 1.4.2  
- Matplotlib: 3.8.4  
- Seaborn: 0.13.2  
- OpenML: 0.14.2  

---

## Cómo ejecutar el proyecto

1. Abrir el notebook `EM5_MHZ.ipynb` en Google Colab.  
2. Ejecutar las celdas en orden, desde la carga de datos hasta la evaluación de resultados.  
3. Los gráficos (curva ROC, matriz de confusión) y métricas se generarán automáticamente al final del notebook.  

---

**Etiquetas:**  
#MachineLearning #ScoringCrediticio #Regularización #Lasso #Ridge #GoogleColab #Educativo
