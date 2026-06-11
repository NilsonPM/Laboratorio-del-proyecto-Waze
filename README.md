# Proyecto de Análisis de Abandono de Usuarios (Waze)

Este proyecto tiene como objetivo analizar la actividad de los usuarios de Waze para identificar comportamientos correlacionados con la deserción o abandono (churn). El análisis preliminar e inspección de datos se estructuró bajo el marco metodológico **PACE** (Plan, Analyze, Construct, Execute).

---

## 📋 Estructura del Repositorio

El repositorio está organizado con los siguientes archivos principales:

* **`Waze_Laboratorio_Python_ES.ipynb`**: Notebook de Jupyter con el proceso completo de carga, limpieza preliminar, análisis exploratorio de datos (EDA) y cálculo de métricas derivadas en español.
* **`waze_dataset.csv`**: Conjunto de datos con 14,999 registros de usuarios y sus métricas de interacción mensual.
* **`images/`**: Carpeta de recursos gráficos utilizada para documentar las etapas de la metodología PACE.

---

## 🎯 Objetivos del Proyecto

1. **Exploración y Diagnóstico (EDA):** Analizar y validar la calidad del conjunto de datos e investigar las relaciones de sus variables mediante medianas y proporciones.
2. **Identificación de Patrones de Abandono:** Comprender las diferencias de uso y movilidad entre usuarios retenidos (`retained`) y aquellos que abandonaron la plataforma (`churned`).
3. **Preparación para Modelado:** Estructurar y crear variables derivadas útiles para el futuro desarrollo de modelos predictivos de Machine Learning.

---

## 📈 Resumen de Hallazgos y Métricas Clave

A partir del análisis exploratorio realizado en el notebook, se identificaron los siguientes patrones críticos:

### ⚡ El Comportamiento del "Súper Conductor" (Usuarios Churned)

Los usuarios etiquetados como `churned` presentan un comportamiento de conducción extremadamente intensivo en comparación con los usuarios retenidos:

* **Kilómetros conducidos por día activo:** El usuario promedio que abandonó condujo **697.54 km** por día de conducción, mientras que el usuario retenido condujo **289.55 km** (~240% de diferencia).
* **Frecuencia de viajes:** Los usuarios que abandonaron realizaron una mediana de **10 viajes por día activo**, frente a los **4.06 viajes** de los usuarios retenidos.
* **Uso de la Aplicación:** A pesar de recorrer mayores distancias y realizar más viajes, los usuarios que abandonaron abrieron la aplicación aproximadamente la mitad de días en el mes comparado con el grupo de retenidos.

### 📱 Análisis por Dispositivo Móvil

No se detectó un desequilibrio estadístico significativo en el abandono según el sistema operativo:

* **Usuarios de iPhone:** Representan el 64% de la muestra. La proporción se mantiene casi idéntica en usuarios retenidos y desertores.
* **Usuarios de Android:** Representan el 36% de la muestra, con el mismo comportamiento de deserción que iOS.
* *Conclusión:* El sistema operativo no es un factor correlacionado con el abandono de usuarios.

---

## 🛠️ Metodología PACE Aplicada

El flujo de trabajo documentado en el notebook sigue el marco PACE:

1. **Plan (Planificar):** Comprensión del negocio, revisión del diccionario de datos y definición de las preguntas analíticas de interés.
2. **Analyze (Analizar):** Carga y limpieza preliminar de datos, aislamiento y caracterización de valores faltantes (700 registros sin etiqueta `label`), cálculo de descriptivos estadísticos basados en medianas para contrarrestar el impacto de valores atípicos (outliers).
3. **Construct (Construir):** Creación de nuevas columnas derivadas:
    * `km_per_drive` (Kilómetros por viaje)
    * `km_per_driving_day` (Kilómetros conducidos por día activo)
    * `drives_per_driving_day` (Viajes realizados por día activo)
4. **Execute (Ejecutar):** Formulación de respuestas cuantitativas, síntesis de conclusiones operativas y preparación del resumen ejecutivo para los directivos de Waze.

---

## 🚀 Requisitos e Instalación

Para ejecutar y explorar el notebook de análisis localmente, se requiere contar con un entorno de Python 3 y las siguientes librerías de manipulación de datos instaladas:

```bash
# Instalación de librerías esenciales
pip install pandas numpy jupyter
```

Para iniciar el entorno interactivo:

```bash
jupyter notebook Waze_Laboratorio_Python_ES.ipynb
```
