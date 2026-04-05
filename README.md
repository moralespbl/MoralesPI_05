# MoralesPI_05
Análisis Riesgo Crediticio
# 📈 Modelo de Scoring Crediticio: Predicción de Default (Dirty 1)

Este repositorio contiene el desarrollo de un modelo de riesgo crediticio diseñado para identificar la probabilidad de mora técnica en una cartera de préstamos de consumo. El proyecto abarca desde la limpieza de datos crudos hasta la optimización de métricas de negocio.

## 🧠 El Modelo: Regresión Logística
Se implementó un modelo de **Regresión Logística** debido a su alta interpretabilidad en el sector financiero. El modelo estima la probabilidad de incumplimiento basándose en el comportamiento histórico, permitiendo asignar un "score" de riesgo a cada cliente.

## 🛠️ Proceso de Ingeniería de Datos
* **Normalización Regional:** Conversión de formatos decimales (comas a puntos) y casteo de tipos para variables monetarias.
* **Tratamiento de Sesgo:** Aplicación de escala logarítmica (**LN**) para normalizar distribuciones de ingresos y saldos.
* **Discretización (Binnings):** Segmentación de variables de Edad y Mora para capturar comportamientos de riesgo no lineales.

## 📊 Variables de Mayor Influencia (Top Predictors)
Tras el proceso de selección de variables (pasando de 26 a 13 predictores significativos), las variables que mostraron mayor impacto en el score final fueron:

1. **Mora Técnica (Bins):** El predictor más potente. Pequeños saltos en los días de atraso disparan exponencialmente la probabilidad de Default.
2. **Situación BCRA:** El historial en el Banco Central actúa como una señal de alerta temprana crítica.
3. **Ratio de Endeudamiento:** La relación entre saldos totales e ingresos netos; a mayor ratio, mayor vulnerabilidad financiera.
4. **Antigüedad del Cliente:** Los clientes con relaciones de mayor plazo con la entidad tienden a presentar menores tasas de mora.
5. **Ingresos Netos (LN):** Un estabilizador del modelo que modula la capacidad de pago real.



## 📈 Resultados de Validación
* **Gini Index:** > 0.40 (Indica una capacidad de discriminación sólida para la industria).
* **Ajuste de Clases:** Uso de `class_weight='balanced'` para compensar la baja frecuencia de casos de default.
* **Optimización de Cut-off:** Selección del punto de equilibrio para maximizar la detección de riesgo sin sacrificar la aprobación de buenos clientes.

---
**Autor:** Pablo - San Salvador de Jujuy, Argentina.
