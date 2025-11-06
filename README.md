# 🛒 Superstore E-commerce — Data Analysis

## 📖 Descripción del proyecto
Objetivo: Diagnosticar la causa raíz de la baja rentabilidad neta de una Superstore global a pesar del crecimiento en ventas, focalizando el análisis en la categoría Furniture y sus subcategorías críticas (Tables, Chairs, Machines).

Se analizó el efecto de los descuentos sobre la rentabilidad y se propusieron medidas operativas y estratégicas para recuperar margen.
Dataset: Global Superstore (2016) — origen: Kaggle (https://www.kaggle.com/datasets/jamsbrown/global-superstore-data-of-2016).

---

## ⚙️ Metodología
### EDA (Exploratory Data Analysis)
* Inspección de estructura, tipos y nulos (51.290 registros, 24 columnas).
* Estadísticas descriptivas, detección de *outliers* y visualizaciones (histogramas, *scatter*, series temporales).

### Preparación y reglas de representatividad
* Limpieza y cálculo de métricas clave: **Sales, Net Profit, Profit Margin, Profit per Unit**.
* Umbral de representatividad: **mín. 35 unidades vendidas por producto** para evitar ruido estadístico.

### Análisis por categoría / subcategoría
* Cálculo de margen y pérdida por unidad por **Category** y **Sub-Category**.
* Segmentación por **Discount Groups** (ej. 0–5%, 5–10%, 10–15%, …) para medir impacto del descuento.

### Diagnóstico y recomendaciones
* Análisis temporal de descuento promedio y su relación con el margen.
* Identificación de rangos de descuento catastróficos y umbrales críticos.

---

## 📈 Principales resultados e insights
### Magnitud del problema:
* Órdenes totales: **51.290**.
* Órdenes con margen negativo: **21.695** (**42.30%**). Esto indica problemas en *pricing*, *cost structure* o políticas de descuento.

### Impacto del descuento:
* Alta correlación negativa entre **Discount** y **Profit Margin** (coef. $\approx$ **–0.84**).
* **Umbral crítico:** a partir del **10% de descuento** el margen tiende a colapsar.
* **Rango consistentemente rentable:** **0–5%** (principal *driver* de volumen y margen).

### Subcategorías críticas:
* **Tables:** Margen **–19.01%**; pérdida por unidad $\approx$ **–€46.69** $\rightarrow$ **máximo foco de urgencia**.
* **Chairs:** Margen cercano a equilibrio **–1.59%**, alta exposición por volumen; rango **15–20%** genera muchas transacciones no rentables.
* **Machines:** Margen **–15.20%**; presenta descuentos extremos (ej. 65–70%) con pérdidas muy severas.

### Patrones por categoría:
* **Technology** muestra mayor resistencia a descuentos intermedios; sin embargo, descuentos extremos (>40%) provocan pérdidas severas también en esta categoría.

---

## 💡 Recomendaciones de negocio

### Regla de descuento (acción inmediata):
* Limitar descuento máximo recomendado al **10%** para **Tables** y **Chairs**.
* Bloquear o requerir aprobación ejecutiva para descuentos **>20%** en **Furniture** y **Office Supplies**.

### Control de promociones:
* Evitar campañas que impulsen rangos **15–30%** en **Tables/Chairs** y **65–70%** en **Machines**. Reservar descuentos extremos solo para liquidación de inventario obsoleto con control de **LTV**.

### Acciones por subcategoría:
* **Tables:** Auditoría de coste directo (**COGS**, logística, montaje) y/o *reprice* para cubrir $\sim$**€46.7** por unidad o considerar despriorización de SKUs no rentables.
* **Chairs:** Ajuste de política de descuentos (**cerrar 15–20%**); mejorar margen por unidad mediante pequeños incrementos de precio o reducción de coste ($\sim$€2 por unidad puede revertir pérdidas).
* **Machines:** eliminar descuentos extremos; investigar causas de márgenes negativos por SKU.

### Estrategia comercial y producto:
* Priorizar promociones en rangos **0–5%** y **5–10%** (rentables).
* Reemplazar descuentos de precio por **valor agregado** (envío gratuito, montaje, financiación) para mantener el precio base.
* Implementar análisis de **CLV** para priorizar inversión comercial y retención por tipo de cliente.

### Mejoras operativas:
* Monitorizar el *discount average* por campaña y por canal; establecer alertas si supera umbrales.
* Integrar métricas de margen en *dashboards* operativos (alertas diarias/semanales).

---

## 🔍 Insights accionables (resumen)
* El descuento es el principal motor de erosión de margen; **atacar la política de descuentos es la palanca más efectiva**.
* **Tables exige intervención inmediata** (*pricing*/cost *control*).
* **Chairs es una oportunidad rápida:** eliminar fugas en descuentos moderados recupera márgenes por volumen.
* El **0–5%** debe ser el núcleo de la estrategia promocional: genera la mayor parte del volumen rentable.

---

## 🧰 Tecnologías utilizadas
* **Lenguaje:** Python
* **Librerías:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
* **Notebook / Script:** Jupyter
* **Fuente de datos:** Kaggle — Global Superstore (2016)
