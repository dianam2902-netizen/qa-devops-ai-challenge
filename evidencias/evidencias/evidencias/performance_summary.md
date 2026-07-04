# 📈 Resumen Ejecutivo - Pruebas de Rendimiento (JMeter)

**Métrica de simulación:** 10 Usuarios concurrentes en bucle continuo.
**Escenario de Prueba:** Consulta masiva al endpoint `/api/products`.

## 📊 Tabla de Resultados Consolidados

| Endpoint | Peticiones Totales | Tiempo Promedio (Avg) | Percentil 95 (P95) | Tasa de Errores (%) | Estado del Quality Gate |
| :--- | :---: | :---: | :---: | :---: | :---: |
| `/api/products` | 50 | 257.5 ms | 310.0 ms | 0.00% | **PASSED (Cumple < 1%)** |

## 🔍 Análisis Asistido por Inteligencia Artificial (Hallazgos)
Tras procesar los registros de ejecución (`jmeter_results.csv`), se concluye que la infraestructura de **QA Store** responde de forma óptima bajo los criterios establecidos en el Plan de Pruebas:
- El tiempo de respuesta promedio se ubicó en **257.5ms**, muy por debajo del umbral límite de **500ms**.
- No se registraron caídas de servidor, timeouts ni códigos HTTP 5xx, garantizando un **0% de error** (umbral máximo permitido: 1%).
