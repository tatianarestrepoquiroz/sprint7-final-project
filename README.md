## 🎯 Objetivo del Proyecto

El objetivo de este proyecto es realizar un análisis exploratorio y proceso de limpieza de datos sobre información de usuarios y su uso de servicios (llamadas y mensajes), con el fin de garantizar la calidad del dataset antes de realizar análisis posteriores.

Se buscó identificar:
- Valores faltantes
- Valores inválidos (sentinels)
- Fechas fuera de rango
- Inconsistencias estadísticas

---

## 📂 Datasets Utilizados

El proyecto se desarrolló utilizando tres datasets:

1️⃣ plans.csv

Contiene información sobre los planes actuales ofrecidos por la compañía:
plan_name, monthly_price, minutes_included, gb_included, messages_included, cost_per_extra_minute, cost_per_extra_gb,
cost_per_extra_message. 
Este dataset permite analizar las condiciones comerciales de cada plan.

2️⃣ users.csv

Contiene información demográfica y contractual de los clientes:
user_id, age, city, reg_date, plan, churn
Se utilizó para analizar características de los usuarios, detectar inconsistencias y revisar calidad de datos.

3️⃣ usage.csv

Contiene el detalle del uso real de los servicios:
user_id, date, type (call o text), Variables asociadas al consumo
Este dataset permite analizar el comportamiento real de consumo de los clientes.

---

## 🔎 Etapas del Análisis

El proyecto se desarrolló en las siguientes etapas:

### 1️⃣ Exploración Inicial
- Revisión de tipos de datos
- Estadísticas descriptivas
- Conteo de valores únicos en variables categóricas

### 2️⃣ Identificación de Problemas
Se detectaron:
- Valor sentinel `-999` en `age`
- Valores `'?'` en `city`
- Fechas futuras (2026) en `reg_date`
- Valores faltantes (`NaN`) en múltiples columnas

### 3️⃣ Limpieza de Datos
Se realizaron las siguientes acciones:
- Reemplazo de `-999` por `NaN` y posterior imputación con la mediana en `age`
- Reemplazo de `'?'` por `NaN` en `city`
- Conversión segura de fechas a formato datetime
- Eliminación (marcado como `NaN`) de fechas fuera de rango (>2024)

### 4️⃣ Validación
- Verificación de estadísticas posteriores a la limpieza
- Revisión de años en columnas de fecha
- Confirmación de consistencia en variables categóricas

---

## ▶️ Cómo Ejecutar el Notebook

Puedes ejecutar el análisis directamente en Google Colab haciendo clic en el siguiente botón:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/tatianarestrepoquiroz/sprint7-final-project/blob/main/S7%20Version-Estudiante-Project-ConnectaTel.ipynb)

🔁 Guía de Reproducción

Para reproducir el análisis: Cargar los datasets users y usage. Ejecutar la exploración inicial
Aplicar los pasos de limpieza: Reemplazo de sentinels, conversión de fechas, corrección de valores fuera de rango, verificar estadísticas finales, continuar con análisis posteriores

✅ Resultado Final

Tras el proceso de limpieza:
Se eliminaron valores inválidos
Se corrigieron fechas inconsistentes
Se mejoró la coherencia estadística del dataset
El dataset final está listo para análisis más avanzados y modelado.
