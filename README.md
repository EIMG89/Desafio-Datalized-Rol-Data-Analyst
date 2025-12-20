# Desafio-Datalized-Rol-Data-Analyst
# 📈 Análisis y Predicción de PM10 | Parque O’Higgins (1997-2025)

![Status](https://img.shields.io/badge/Status-Completed-success)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Statsmodels](https://img.shields.io/badge/Library-Statsmodels-orange)

Este repositorio alberga un estudio avanzado de **series de tiempo** aplicado a la concentración de material particulado (**PM10**) en la estación de monitoreo Parque O'Higgins, Santiago de Chile. El núcleo del proyecto es el desarrollo de un modelo predictivo robusto diseñado para fortalecer la gestión de la calidad del aire.

---

## 🎯 Objetivo del Proyecto
Modelar el comportamiento histórico de casi tres décadas de datos y proyectar niveles futuros de contaminación para anticipar episodios críticos de riesgo sanitario.

## 🛠️ Metodología y Herramientas
El proyecto se rige bajo la metodología rigurosa de **Box-Jenkins**, estructurada en las siguientes etapas:

1.  **Identificación:** Análisis de funciones de autocorrelación (**ACF**) y autocorrelación parcial (**PACF**).
2.  **Estimación:** Ajuste fino de parámetros para el modelo seleccionado.
3.  **Diagnóstico:** Verificación de residuos mediante pruebas de ruido blanco.
4.  **Predicción:** Generación de pronósticos con horizontes temporales hasta finales de 2025.

### Stack Tecnológico
* **Lenguaje:** Python (Pandas, NumPy)
* **Modelado Estadístico:** `statsmodels` (SARIMA)
* **Visualización:** Matplotlib & Seaborn
* **Entorno:** Jupyter Notebooks

---

## 🔍 Descripción del Proceso (¿Qué se hizo?)
Se ejecutó un análisis estadístico y econométrico exhaustivo sobre una serie mensual con **más de 27 años de registros**:

* **Análisis Exploratorio (EDA):** Detección de una estacionalidad determinística marcada (picos en invierno vs. valles en verano) y descomposición de tendencias de largo plazo.
* **Pre-procesamiento:** Limpieza de datos, tratamiento de valores faltantes y test de **Dickey-Fuller Aumentado (ADF)** para evaluar la estacionariedad de la serie.
* **Modelamiento SARIMA:** Implementación de un modelo $(p,d,q) \times (P,D,Q)_s$ capaz de capturar componentes cíclicos y estocásticos simultáneamente.



---

## 💡 Motivación e Impacto
La contaminación por **PM10** en Santiago es un desafío de salud pública exacerbado por la inversión térmica invernal. 
> **Resultado Crítico:** El modelo alcanzó un **RMSE de ~3.7 $\mu g/m^3N$**, proporcionando una herramienta de alta precisión para que autoridades y ciudadanos puedan anticipar episodios de pre-emergencia y emergencia ambiental.

---

## 🏆 Resultados Clave y Conclusiones

| Hito | Detalle |
| :--- | :--- |
| **Modelo Óptimo** | **SARIMA(1,0,1)(0,1,1)₁₂** seleccionado bajo criterio de información de Akaike (AIC). |
| **Precisión de Validación** | Alta fidelidad al comparar con datos reales preliminares de agosto-octubre 2025. |
| **Tendencia Histórica** | Se confirma una reducción gradual en los niveles base de las últimas décadas. |
| **Factor Dominante** | La variabilidad estacional sigue siendo el componente de mayor peso en la varianza de la serie. |

---

## 📂 Estructura del Repositorio
* `data/`: Datasets históricos y procesados.
* `notebooks/`: Jupyter Notebook con el flujo completo del análisis.
* `reports/`: Documentación técnica y PDF del estudio.
* `dashboard/`: Especificaciones y capturas del tablero en Power BI.

---
**Candidato:** Eleazar Israel Madariaga González  
**Fecha:** Diciembre 2025
