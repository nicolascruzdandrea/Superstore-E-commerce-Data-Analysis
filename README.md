# 🛒 Superstore E-commerce Data Analysis

## 📖 Descripción del Proyecto

Este proyecto es un **análisis de rentabilidad** enfocado en el dataset global de ventas de una *Superstore*. El objetivo principal fue diagnosticar la **causa raíz de la baja rentabilidad neta** de la compañía, a pesar de registrar un crecimiento constante en ventas.

El análisis se centró en la **Categoría Furniture** y en dos subcategorías de alto volumen y margen negativo: **Tables**, **Chairs** y **Machines**, identificando el impacto directo del **descuento** en la destrucción del valor.

---

## ⚙️ Metodología Usada

La metodología se basó en una exploración de datos (EDA) y una segmentación profunda, siguiendo estos pasos:

1.  **Análisis Exploratorio de Datos (EDA):**
    * Inspección de la estructura del dataset (51,290 registros y 24 columnas).
    * Identificación de tipos de datos y manejo de valores nulos (se notó una alta tasa de valores nulos en `Postal Code`).

2.  **Análisis Temporal y Estacionalidad:**
    * Evaluación de la tendencia de ventas y beneficio a lo largo de los años.
    * Cálculo del margen de beneficio promedio por trimestre y año, detectando la **desaceleración del crecimiento del margen**.

3.  **Análisis de Rentabilidad por Categoría:**
    * Se calculó el margen de beneficio por `Category` y `Sub-Category`.
    * Se identificó la **Categoría Furniture** como la única generadora de pérdidas (`-3.8%`), mientras que `Technology` (`+3.3%`) y `Office Supplies` (`+2.9%`) son rentables.

4.  **Análisis Profundo del Impacto del Descuento:**
    * Se segmentaron las transacciones de las subcategorías críticas (**Tables**, **Chairs**, **Machines**) en **grupos de descuento** (ej: 0-5%, 5-10%, 15-20%).
    * **Métricas Clave:** Se calculó el `Profit Margin`, la `Cantidad de Transacciones` y el `Profit per Unit` para cada grupo de descuento para cuantificar la fuga de capital.

---

## 📈 Insights y Conclusiones Principales

### 1. El Descuento como Factor Destructor de Valor
El **descuento** es el principal factor que arrastra la rentabilidad neta. En todas las subcategorías analizadas, cualquier promoción por encima de un umbral bajo (entre el 5% y el 10%) resulta en pérdidas.

### 2. Prioridad Crítica: Tables
* **Problema Estructural:** `Tables` registra una pérdida catastrófica del **-19.01%** y la mayor pérdida promedio por unidad (aproximadamente **-$46.69**).
* **Fuga por Volumen:** El **mayor volumen de transacciones no rentables** se concentra en los descuentos **moderados (15-30%)**.

### 3. Fugas por Volumen vs. Fugas por Intensidad
* **Chairs (Fuga por Volumen):** La subcategoría está cerca del equilibrio (`-1.59%`), pero la pérdida es impulsada por el **alto volumen de ventas** en el rango de descuento **15-20%**.
* **Machines (Riesgo Extremo):** La subcategoría está en equilibrio (`-2.60%`), pero registra pérdidas extremas en el rango de **65-70% de descuento** (`-147.35%`), lo que arrastra el margen total.

### 4. El Único Motor de Ganancia
El rango de descuento **0-5%** es consistentemente el **único segmento altamente rentable** en todas las subcategorías, demostrando que el precio base o precio regular es la estrategia de venta comprobada y debe protegerse.

---

## 💡 Recomendaciones de Negocio

### 1. **Priorización de Intervención**
Se recomienda una matriz de acción:
* **Crítica:** `Tables` (Requiere reestructuración de costes o precio base).
* **Alta:** `Chairs` (Requiere disciplina de descuento para asegurar rentabilidad inmediata).
* **Media:** `Machines` (Requiere eliminar descuentos extremos).

### 2. **Implementación de Política de Descuento (Regla del 10%)**
* Establecer el **10% como el límite máximo de descuento permitido** para las subcategorías `Tables` y `Chairs`, ya que el 5-10% es el último umbral de rentabilidad.
* **Eliminar inmediatamente** los rangos de descuento **15-30%** en `Tables/Chairs` y **65-70%** en `Machines`.

### 3. **Objetivos Operativos de Costes/Precios**
* Para `Tables`, buscar un aumento de precio o reducción de costes que compense la pérdida de **$46.69 por unidad**.
* Para `Chairs`, una mejora de solo **$2 por unidad** aseguraría la rentabilidad total de la subcategoría.

---

## 💻 Tecnologías Utilizadas

* **Python:** Lenguaje principal de análisis.
* **Pandas:** Manipulación y limpieza de datos.
* **NumPy:** Operaciones numéricas y vectoriales.
* **Matplotlib:** Visualización de tendencias temporales y gráficos de barras.
* **Seaborn:** Creación de gráficos estadísticos de alta calidad (ej: análisis de rentabilidad por descuentos).

* ## 📊 Origen del dataset  
El dataset utilizado proviene de **Kaggle** (https://www.kaggle.com/datasets/jamsbrown/global-superstore-data-of-2016).
