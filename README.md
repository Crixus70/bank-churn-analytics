# Predicción de abandono de clientes bancarios (Churn Analytics)

> Caso de estudio de **análisis de negocio aplicado con ciencia de datos**: identificación temprana de clientes con riesgo de abandono para apoyar estrategias de retención en una institución bancaria.

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)]()
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikitlearn&logoColor=white)]()
[![Pandas](https://img.shields.io/badge/Pandas-analytics-150458?logo=pandas&logoColor=white)]()
[![Estado](https://img.shields.io/badge/estado-completado-brightgreen)]()

---

## 1. El problema de negocio

Un banco observa la **pérdida progresiva de clientes**. Retener a un cliente actual resulta menos costoso que captar uno nuevo, por lo que la pregunta de negocio es:

> **¿Qué clientes tienen mayor probabilidad de abandonar la institución, de modo que el equipo de retención pueda actuar antes de que se vayan?**

Este proyecto responde esa pregunta con un **modelo predictivo de clasificación** entrenado sobre el comportamiento histórico de **10,000 clientes**, y —lo más importante— traduce los resultados a **decisiones de negocio accionables**.

---

## 2. Beneficios para el negocio

| Beneficio | Descripción |
|---|---|
| 🎯 **Priorización de retención** | El modelo identifica a los clientes con mayor riesgo de abandono, permitiendo concentrar los esfuerzos (y el presupuesto) de retención donde más impacto tienen. |
| 💰 **Asignación eficiente de recursos** | Con una precisión del 58 % en las alertas, el equipo de retención sabe que ~6 de cada 10 contactos corresponden a clientes que realmente iban a abandonar. |
| 📉 **Detección temprana** | Se detecta el **65 % de los abandonos reales** antes de que ocurran, frente a solo un 21 % con un enfoque analítico básico sin corrección del desequilibrio de datos. |
| 📊 **Decisiones basadas en evidencia** | Cada conclusión se acompaña de métricas, matrices de confusión y análisis de errores, con limitaciones cuantificadas explícitamente. |
| ⚖️ **Cultura de riesgo y cumplimiento** | El análisis documenta qué puede y qué no puede afirmarse a partir de los datos: el modelo prioriza riesgo, pero no demuestra por sí solo la rentabilidad de las acciones de retención. |

### Impacto medible del enfoque analítico

| Enfoque | Abandonos detectados (recall) | F1 |
|---|---|---|
| Modelo básico sin corrección | 20.6 % | 0.31 |
| **Modelo final seleccionado** | **64.9 %** | **0.61** |

> El enfoque final **triplica la capacidad de detección** de clientes en riesgo respecto al análisis básico, manteniendo un equilibrio aceptable entre detección y falsas alarmas.

---

## 3. Metodología (visión general)

El proyecto sigue un flujo de trabajo estándar de la industria para analítica predictiva:

1. **Comprensión del negocio y de los datos** — 10,000 registros de clientes con 13 características (saldo, antigüedad, productos contratados, actividad, geografía, demografía).
2. **Preparación y calidad de datos** — tratamiento de valores ausentes, codificación de variables categóricas, escalado y partición estratificada en entrenamiento / validación / prueba, con controles explícitos contra la **fuga de información**.
3. **Diagnóstico del desequilibrio de clases** — solo el 20 % de los clientes abandona; se demuestra por qué la exactitud es una métrica engañosa en este contexto.
4. **Comparación de modelos y técnicas de balanceo** — regresión logística, árboles de decisión y bosques aleatorios, con pesos de clase y sobremuestreo; selección por F1 con AUC-ROC como complemento.
5. **Evaluación final independiente** — el modelo seleccionado se evalúa una sola vez sobre datos nunca utilizados en entrenamiento ni selección, y se analizan sus errores en términos de negocio.

---

## 4. Resultados

Evaluación final sobre **2,000 clientes** nunca vistos por el modelo:

| Exactitud | Precisión | Recall | F1 | AUC-ROC |
|---|---|---|---|---|
| 83.4 % | 58.2 % | 64.9 % | **0.613** | **0.857** |

**Lectura de negocio:**

- De cada 100 clientes que abandonan, el modelo **detecta 65 a tiempo**.
- De cada 100 alertas generadas, **58 corresponden a abandonos reales**.
- El análisis de errores cuantifica el costo de las falsas alarmas (contactos innecesarios) frente al costo de los abandonos no detectados, insumo directo para decidir el umbral de intervención.

---

## 5. Habilidades demostradas

Este proyecto ejemplifica las competencias de un **Data Science / Business Analytics Analyst**:

- **Análisis estratégico de datos**: identificación de insights e implicaciones de negocio, con recomendaciones y limitaciones explícitas.
- **Minería y preparación de datos**: calidad de datos, tratamiento de ausentes, codificación y escalado con prevención de fuga de información.
- **Modelado estadístico y machine learning**: regresión logística, árboles de decisión, bosques aleatorios, balanceo de clases, selección de hiperparámetros.
- **Evaluación rigurosa**: F1, precisión, recall, AUC-ROC, matriz de confusión y análisis de errores traducido a consecuencias de negocio.
- **Comunicación de resultados**: hallazgos presentados de forma sistemática y comprensible para audiencias técnicas y no técnicas.

**Stack técnico:** Python · Pandas · NumPy · scikit-learn · Matplotlib · Jupyter

---

## 6. Nota sobre el código

El código fuente y los datos no se publican en este repositorio: el proyecto se desarrolló como parte de un programa de formación y el objetivo de este espacio es **documentar el enfoque analítico, los resultados y su valor de negocio**. Con gusto puedo explicar la metodología y las decisiones técnicas en una entrevista o conversación técnica.

---

## Autor

**Cristóbal Antonio Hernández Juárez**
Maestro en Ingeniería Industrial · Doctorante en Finanzas y Empresa · Científico de Datos (TripleTen, en curso)

📍 Poza Rica de Hidalgo, Veracruz, México
📧 crotalushj@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/cristóbal-hernández-5201b6277)
