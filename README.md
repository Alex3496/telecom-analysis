
# 📊 Análisis ConnectaTel - Comportamiento de Clientes

## 🎯 Objetivo del Proyecto

Este proyecto analiza el **comportamiento de los clientes** de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, con el propósito de:

- Construir un **perfil estadístico** de los clientes
- Detectar **comportamientos atípicos** en el uso de servicios
- Crear **segmentos de clientes** basados en patrones de consumo
- **Identificar estrategias de retención** y mejoras en los planes ofrecidos
- Proporcionar **insights accionables** para la toma de decisiones de negocio

El análisis se basa en datos registrados hasta el año **2024**.

---

## 📁 Datasets Utilizados

El proyecto trabaja con **tres datasets principales**:

| Dataset | Descripción | Columnas Principales |
|---------|-------------|---------------------|
| **plans.csv** | Información de los planes actuales | Precio, minutos incluidos, GB incluidos, costo por extra |
| **users_latam.csv** | Información de los clientes | Edad, ciudad, fecha de registro, plan, churn |
| **usage.csv** | Detalle del uso real de servicios | Llamadas, mensajes, duración, fecha |

**Ubicación de los datos:** `/datasets/`

---

## 🔍 Etapas del Análisis

### 1️⃣ **Carga y Exploración de Datos**
- Importación de librerías (pandas, numpy, seaborn, matplotlib)
- Carga de los tres datasets
- Revisión inicial de estructura, tipos de datos y dimensiones

### 2️⃣ **Identificación de Problemas de Calidad**
- Detección de valores nulos y su proporción
- Identificación de valores inválidos y sentinels (-999 en edad, "?" en ciudad)
- Revisión y validación de fechas fuera de rango
- Análisis de valores atípicos en columnas numéricas

### 3️⃣ **Limpieza de Datos**
- Corrección de sentinels (reemplazo de -999 por mediana en edad)
- Reemplazo de valores "?" por NA en ciudad
- Marcado de fechas imposibles como NA
- Verificación de valores MAR (Missing At Random) en duration y length

### 4️⃣ **Agregación y Métricas de Uso**
- Creación de tabla agregada por usuario con:
  - Cantidad total de mensajes
  - Cantidad total de llamadas
  - Total de minutos de llamada
- Combinación con datos de usuarios para crear perfil completo

### 5️⃣ **Visualización de Distribuciones**
- Histogramas de edad, mensajes, llamadas y minutos
- Análisis de distribuciones por tipo de plan (Básico vs Premium)
- Boxplots para identificación visual de outliers
- Cálculo de límites IQR para detección de valores extremos

### 6️⃣ **Segmentación de Clientes**
- **Segmentación por uso:** Bajo uso, Uso medio, Alto uso
- **Segmentación por edad:** Joven, Adulto, Adulto Mayor
- Visualización de la distribución de segmentos

### 7️⃣ **Insights Ejecutivos**
- Traducción de hallazgos en conclusiones accionables
- Recomendaciones para mejora de planes
- Identificación de oportunidades comerciales

---

## 🚀 Cómo Ejecutar el Notebook

### **Opción 1: Google Colab (Recomendado)**

1. Accede a [Google Colab](https://colab.research.google.com/)
2. Sube el archivo `S7 Version-Estudiante-Project-ConnectaTel.ipynb`
3. Asegúrate de tener acceso a los datasets en la ruta `/datasets/`
4. Ejecuta las celdas en orden secuencial (⌘/Ctrl + Enter para cada celda)

### **Opción 2: Jupyter Notebook Local**

```bash
# Instalar dependencias
pip install pandas numpy seaborn matplotlib

# Iniciar Jupyter
jupyter notebook

# Abrir el archivo .ipynb desde la interfaz
```

### **Opción 3: VS Code con extensión de Jupyter**

1. Instala la extensión "Jupyter" en VS Code
2. Abre el archivo `.ipynb`
3. Selecciona el kernel de Python
4. Ejecuta las celdas

---

## 📋 Guía de Reproducción

### **Prerrequisitos**

```python
# Librerías necesarias
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```

### **Pasos para Reproducir el Análisis**

1. **Preparación del entorno:**
   - Asegúrate de tener Python 3.7+ instalado
   - Instala las librerías necesarias: `pip install pandas numpy seaborn matplotlib`

2. **Ubicación de los datos:**
   - Coloca los archivos CSV en la carpeta `/datasets/`
   - Verifica que los nombres sean exactos: `plans.csv`, `users_latam.csv`, `usage.csv`

3. **Ejecución secuencial:**
   - Ejecuta las celdas en orden, desde la primera hasta la última
   - Cada paso está documentado con instrucciones y objetivos claros
   - Los comentarios en el código guían el proceso

4. **Personalización:**
   - Puedes modificar los umbrales de segmentación en el Paso 6
   - Ajusta los parámetros de visualización según tus necesidades
   - Complementa el análisis ejecutivo con tus propias conclusiones

---

## 📊 Resultados Principales

- **Problemas de datos identificados:** Sentinels en edad (-999), valores "?" en ciudad, fechas futuras
- **Segmentación exitosa:** Clasificación de usuarios por nivel de uso y grupo de edad
- **Patrones detectados:** La mayoría de usuarios tienen uso medio, con un segmento pequeño de alto valor con uso intensivo
- **Outliers:** Se identificaron valores extremos en llamadas y minutos, pero se conservaron por representar comportamiento real

---

## 👤 Autor

**Proyecto:** Sprint 7 - Análisis de Datos ConnectaTel  
**Institución:** TripleTen  
**Fecha:** 2024

---

## 📝 Notas Adicionales

- El análisis se enfoca en datos del año 2024
- Los segmentos creados pueden ajustarse según necesidades del negocio
- Se recomienda actualizar el análisis periódicamente con nuevos datos
- Para preguntas o sugerencias, consulta la documentación del notebook

---
