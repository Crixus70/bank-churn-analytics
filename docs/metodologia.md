# Metodología del análisis

Documento complementario al [README](../README.md). Describe el enfoque metodológico sin incluir código.

## Diseño del experimento

- **Tipo de problema:** clasificación binaria supervisada (abandona / permanece).
- **Datos:** 10,000 clientes, 13 características + objetivo.
- **Partición:** 60 % entrenamiento / 20 % validación / 20 % prueba, estratificada por la variable objetivo.
- **Regla de oro:** todo el preprocesamiento (imputación, codificación, escalado) se ajusta **únicamente con entrenamiento** para evitar fuga de información; la prueba se usa una sola vez, al final.

## Decisiones metodológicas clave

1. **Métrica principal: F1.** Con solo 20 % de casos positivos, predecir "nadie abandona" acertaría el 80 % de las veces sin aportar valor. F1 equilibra precisión y recall sobre la clase que importa al negocio.
2. **Dos técnicas de balanceo comparadas:** pesos de clase y sobremuestreo de la clase minoritaria (solo en entrenamiento).
3. **Tres familias de modelos:** regresión logística (interpretable, requiere escalado), árbol de decisión y bosque aleatorio (con búsqueda de hiperparámetros).
4. **Selección sin tocar la prueba:** el modelo final se elige por F1 de validación, con AUC-ROC como desempate.

## Limitaciones declaradas

- El modelo **prioriza** clientes en riesgo; no demuestra por sí solo qué acciones de retención serán efectivas ni su rentabilidad.
- Las 190 falsas alarmas y 143 abandonos no detectados (en 2,000 casos de prueba) deben ponderarse contra los costos de intervención antes de su aplicación.
- Los resultados corresponden a un conjunto de datos histórico; su aplicación real requiere validación con datos vigentes y monitoreo de deriva.
