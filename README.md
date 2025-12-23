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
* **Lenguaje:** Python (Pandas, NumPy, Matplotlib, statsmodels, pmdarima)
* **Modelado Estadístico:** `statsmodels` (SARIMA)
* **Visualización:** Matplotlib & Seaborn
* **Entorno:** Jupyter Notebooks

---

### 🔍 Descripción del Proceso (¿Qué se hizo?)

Se ejecutó un análisis estadístico y econométrico exhaustivo sobre una serie de tiempo mensual con **más de 27 años de registros históricos** (1997-2024), estructurado en las siguientes fases técnicas:

#### 1. Análisis Exploratorio de Datos (EDA) y Descomposición
* **Identificación de Patrones:** Se detectó una estacionalidad anual determinística con picos críticos durante el trimestre invernal (mayo-julio) y valles en verano, consistente con los fenómenos de inversión térmica y escasa ventilación de la cuenca de Santiago.
* **Análisis de Autocorrelación:** Mediante el uso de correlogramas (**ACF y PACF**), se identificaron dependencias significativas en los primeros rezagos y una persistencia cíclica cada 12 meses, lo que confirmó la necesidad de un enfoque estacional para el modelado.

#### 2. Pre-procesamiento y Rigurosidad Estadística
* **Tratamiento de Datos:** Limpieza y estructuración de la serie temporal a partir de los registros de la estación **Parque O'Higgins**, asegurando la continuidad mensual y la integridad de la variable objetivo.
* **Evaluación de Estacionariedad:** Se aplicó el test de **Dickey-Fuller Aumentado (ADF)** para verificar la raíz unitaria. Tras observar que la serie presentaba variaciones cíclicas, se determinó la aplicación de una **diferenciación estacional ($D=1$)** para estabilizar la media y eliminar la componente estacional de la serie.

#### 3. Modelamiento Predictivo SARIMA
* **Arquitectura del Modelo:** Se implementó y comparó una familia de modelos **SARIMA $(p,d,q) \times (P,D,Q)_{12}$**. Tras evaluar múltiples configuraciones mediante la búsqueda de parsimonia, el modelo **SARIMA(1,0,1)(0,1,1)₁₂** resultó óptimo.
* **Selección por Criterios de Información:** El modelo final fue seleccionado por minimizar el **AIC (Akaike Information Criterion)**, logrando el mejor equilibrio entre ajuste y complejidad para evitar el sobreajuste (*overfitting*).
* **Captura de Dinámicas:** Se utilizó un término de media móvil estacional ($Q=1$) para corregir los errores en los ciclos anuales y términos autorregresivos para gestionar la memoria de corto plazo de la contaminación.

#### 4. Diagnóstico y Validación de Precisión
* **Diagnóstico de Idoneidad:** Se confirmó mediante pruebas de diagnóstico que los residuos se comportan como **ruido blanco** (independientes e idénticamente distribuidos), validando que el modelo capturó toda la información sistemática de la serie.
* **Benchmarking de Predicción:** El modelo se validó contrastando el pronóstico frente a datos reales preliminares del segundo semestre de 2025, alcanzando un **RMSE (Error Cuadrático Medio Raíz) de 3.7 µg/m³N**. Este resultado es excepcionalmente bajo considerando la variabilidad histórica de la serie, demostrando una alta fiabilidad predictiva.


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
* `data/`: PM10-Prque Ohigginns-Santiago
* `notebooks/`: Desafio_Datalized_Analisis
* `reports/`: Desafio Datalized Informe
* `dashboard/`: Dashboard PM10

## 📊 Visualización Interactiva
Se ha desarrollado un dashboard interactivo en Power BI para explorar las proyecciones y el comportamiento histórico del PM10 de manera dinámica.

* **Dashboard en línea:** [Acceder al Dashboard Interactivo](https://drive.google.com/file/d/18WsTVj1oePkYuD6wjjcmp-YYLZVPGqWa/view?usp=sharing)

### Vista Previa del Tablero
A continuación, se presentan capturas del entorno de análisis y el modelo de datos implementado:

| Dashboard de Control y Pronóstico |
[Dashboard PM10](https://drive.google.com/file/d/1eOTC5vV5xfEEVRjRkkcSxzKavbj_Cp8T/view?usp=drive_link)

A continuación se presenta el panel de control desarrollado para el monitoreo y seguimiento de los niveles de PM10:

<p align="center">
  <img src="https://lh3.googleusercontent.com/d/1eOTC5vV5xfEEVRjRkkcSxzKavbj_Cp8T" alt="Dashboard PM10 Parque O'Higgins" width="100%">
</p>


---
**Candidato:** Eleazar Israel Madariaga González  
**Fecha:** 23/12/2025
