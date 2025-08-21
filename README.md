# OilyGiant_Analisis_Rentabilidad
La compañía OilyGiant busca identificar los mejores lugares para abrir 200 pozos nuevos de petróleo. Para ello, se desarrolló un modelo de regresión lineal capaz de predecir el volumen de reservas en nuevos pozos y seleccionar las regiones más rentables considerando los beneficios y riesgos.

🎯 Objetivos del proyecto

Leer y explorar los datos de pozos petrolíferos.
Entrenar un modelo de regresión lineal para predecir el volumen de reservas.
Seleccionar los 200 mejores pozos en cada región.
Calcular el beneficio esperado considerando el presupuesto y el ingreso por barril.
Aplicar bootstrapping para estimar beneficios y riesgos de pérdida.
Elegir la región óptima con el mayor beneficio promedio y un riesgo < 2.5%.

📂 Datos

Cada archivo contiene información de 100,000 pozos en una región:
id → Identificador del pozo
f0, f1, f2 → Parámetros técnicos
product → Volumen de reservas (en miles de barriles)

⚙️ Metodología

1. División de datos → Entrenamiento (75%) y validación (25%).
2. Normalización de características con StandardScaler.
3. Entrenamiento de modelo de regresión lineal en cada región.
4. Evaluación con métricas MSE y RMSE.
5. Cálculo de ganancias:
Se seleccionan 500 pozos aleatorios en cada iteración.
Se eligen los 200 mejores según el modelo.
Beneficio = (reservas reales × 4500 USD) – 100M USD (coste de inversión).
6. Bootstrapping con 10,000 iteraciones para estimar distribución de beneficios y riesgos.

📊 Resultados

✅ Desempeño del modelo
| Región | Media de reservas | RMSE     |
| ------ | ----------------- | -------- |
| 0      | 92.5              | 37.57    |
| 1      | 68.8              | **0.89** |
| 2      | 95.0              | 40.02    |

📉 Riesgo de pérdida

| Región | Riesgo estimado |
| ------ | --------------- |
| 0      | 6.64%           |
| 1      | **1.18%**       |
| 2      | 7.77%           |

📌 Conclusiones

La Región 1 presenta el menor RMSE (0.89), lo que indica una excelente precisión entre los valores predichos y reales.
Además, el riesgo de pérdidas es de solo 1.18%, por debajo del umbral de 2.5%.
A pesar de que las regiones 0 y 2 tienen un promedio de reservas mayor, sus riesgos superan el 6%.
La Región 1 es la mejor opción para invertir en los 200 nuevos pozos petrolíferos.

🛠️ Tecnologías utilizadas

Python
Pandas, NumPy
Scikit-learn
Matplotlib / Seaborn
SciPy (intervalos de confianza)
