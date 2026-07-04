# 📋 Plan de Pruebas y Criterios de Aceptación - QA Store

Este documento define la estrategia de pruebas, los umbrales de aceptación y los mecanismos de control bajo un enfoque DevSecOps para asegurar la estabilidad, seguridad y el rendimiento de la aplicación **QA Store** antes de su despliegue a producción.

## 🚀 Quality Gates Definidos

Para que un Pull Request (PR) sea aprobado e integrado a la rama principal (`main`), debe cumplir obligatoriamente con las siguientes compuertas de calidad automatizadas y manuales:

### 1. Pruebas Funcionales Automatizadas
- **Criterio:** El 100% de las pruebas automatizadas de regresión e integración deben ejecutarse y finalizar con éxito (`PASS`).
- **Mecanismo:** Validación automática a través de la suite de CI en GitHub Actions. No se permiten fallos intermitentes (*flaky tests*).

### 2. Pruebas de Performance (Rendimiento)
- **Tasa de Errores:** El porcentaje total de peticiones fallidas (HTTP 5xx, timeouts) durante la prueba de carga debe ser **estrictamente menor al 1%**.
- **Tiempo de Respuesta (Avg/P95):** El tiempo de respuesta promedio (Average) de la API/sitio no debe superar los **500ms**, y el Percentil 95 (P95) debe mantenerse por debajo de los **1500ms** bajo condiciones de carga normal.

### 3. Seguridad Estática (DevSecOps)
- **Detección de Secretos:** Queda estrictamente prohibido subir credenciales, tokens de API, llaves privadas o contraseñas en texto plano dentro del código fuente.
- **Mecanismo:** Escaneo estático en el pipeline para bloquear integraciones que expongan variables sensibles (Secret Detection).

### 4. Evidencias y Artefactos
- **Requisito:** Cada ejecución o cambio que altere el comportamiento del sistema debe adjuntar evidencias claras (reportes HTML, logs de consola o capturas de pantalla) dentro del directorio `/evidencias` o adjuntos en el cuerpo del Pull Request como registro de auditoría.

---

## 🔒 Visión DevSecOps en el Ciclo de QA
La calidad ya no solo implica verificar que un botón funcione o que la página cargue rápido; la seguridad es un pilar fundamental de la calidad del software. 

Bajo la filosofía DevSecOps, el equipo de QA desplaza la seguridad hacia la izquierda (*Shift-Left Testing*). Esto significa que las vulnerabilidades y las malas prácticas de configuración se mitigan de forma temprana mediante validaciones automatizadas en cada Pull Request, garantizando que el código entregado sea estable, rápido y seguro desde su origen.

