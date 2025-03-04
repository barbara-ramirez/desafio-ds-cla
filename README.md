- Utilicé la técnica de Machine Learning XGBoost, específicamente el modelo XGBClassifier. Opté por esta librería porque se basa en árboles de decisión, lo que la hace adecuada para problemas de clasificación binaria. Además, XGBoost tiene la capacidad de ajustar errores de manera iterativa, funciona bien para datasets desbalanceados y también funciona bien con Optuna, útil para el ajuste de hiperparámetros. Entre otras cosas, esta libreria es muy utilizada debido a su eficiencia en entrenamiento y predicción.

- Considerando las condiciones del dataset desbalanceado (1% aproximadamente de target 1 en el dataset) intenté diferentes técnicas de balanceo de clases, como agregar clases 1 (con SMOTE) o reducir clases 0 (con RandomUnderSampler), pero finalmente encontré mejores resultados utilizando el balance de pesos incorporado de XGBoost (scale_pos_weight).

- Se  considera un balance entre la prueba y el entrenamiento de 15% y 85% respectivamente, debido a que el dataset no tiene tantos datos (2000 filas).

- La optimización de hiperparámetros la realicé modificando el rango de valores de acuerdo a los resultados obtenidos, para acercarme a mejores resultados.

- Escogí la métrica F1-score sobre AUC para maximizar, pues se recomienda utilizar esta métrica para clases desbalanceadas.
