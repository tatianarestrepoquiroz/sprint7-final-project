## 🎯 Objetivo del Proyecto

El objetivo de este proyecto es realizar un análisis exploratorio y proceso de limpieza de datos sobre información de usuarios y su uso de servicios (llamadas y mensajes), con el fin de garantizar la calidad del dataset antes de realizar análisis posteriores.

Se buscó identificar:
- Valores faltantes
- Valores inválidos (sentinels)
- Fechas fuera de rango
- Inconsistencias estadísticas

---

## 📂 Datasets Utilizados

El proyecto trabaja con los siguientes datasets:

### 1️⃣ `users`
Contiene información demográfica de los usuarios:
- `user_id`
- `age`
- `city`
- `reg_date`

### 2️⃣ `usage`
Contiene información de uso del servicio:
- `user_id`
- `date`
- `type` (call o text)

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

Puedes ejecutar el análisis de las siguientes maneras:

### Opción 1: Google Colab
1. Ir a https://colab.research.google.com/
2. Subir el archivo `.ipynb`
3. Subir los datasets necesarios
4. Ejecutar las celdas en orden

### Opción 2: Localmente
1. Clonar el repositorio
2. Instalar dependencias necesarias (pandas, numpy, matplotlib si aplica)
3. Ejecutar:

```bash
jupyter notebook

Abrir el archivo .ipynb y ejecutar las celdas en orden.

🔁 Guía de Reproducción

Para reproducir el análisis: Cargar los datasets users y usage. Ejecutar la exploración inicial
Aplicar los pasos de limpieza: Reemplazo de sentinels, conversión de fechas, corrección de valores fuera de rango, verificar estadísticas finales, continuar con análisis posteriores

✅ Resultado Final

Tras el proceso de limpieza:
Se eliminaron valores inválidos
Se corrigieron fechas inconsistentes
Se mejoró la coherencia estadística del dataset
El dataset final está listo para análisis más avanzados y modelado.
