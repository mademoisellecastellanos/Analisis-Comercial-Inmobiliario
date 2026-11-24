📊 Proyecto: Análisis Comercial Inmobiliario

Evaluación del desempeño comercial en el sector inmobiliario (enero 2023 – diciembre 2024) para analizar crecimiento, rentabilidad, comportamiento por canal y segmento, estacionalidad y recurrencia de clientes mediante un dashboard interactivo en **Tableau**.

🔗 **Dashboard en Tableau Public:** [Ver visualización interactiva](https://public.tableau.com/shared/JYCYX79PX?:display_count=n&:origin=viz_share_link)

## 📂 Estructura de Datos y Modelado

### Datasets
* `hecho_ventas_propiedades`: Tabla de hechos con transacciones de venta (precio, cliente, propiedad, canal, fecha, porcentaje de comisión)
* `dim_clientes`: Información y segmentación de clientes.
* `dim_propiedades`: Características de las propiedades (tipo, tamaño, ubicación, etc.).
* `dim_fecha`: Dimensión temporal (en Tableau se aprovechan directamente las jerarquías de fecha sobre `fecha_venta`).

### Proceso Realizado
1. **Limpieza y validación:** Formato de fechas (`Date`), estandarización numérica y porcentual (`porcentaje_comision`), revisión de valores nulos y verificación de unicidad en claves primarias de `dim_clientes` y `dim_propiedades`.
2. **Modelado (Esquema Estrella):** Relación central en `hecho_ventas_propiedades` conectada a dimensiones con cardinalidad `1:*`, filtro simple y relaciones activas
3. **Cálculos y métricas:** KPIs base (Ingreso Total, Cantidad de Ventas, Ticket Promedio, Comisión Total), participaciones porcentuales (`%`), métricas temporales (YTD, YoY) y campos para análisis de cohortes (primera compra, mes de cohorte y mes de venta).


## 🖥️ Estructura del Dashboard

* **1. Overview Ejecutivo:** KPIs principales, tendencia de ventas en el tiempo, ingresos/ventas por ciudad y crecimiento YoY
* **2. Análisis Comercial:** Ingresos por tipo de propiedad, canal de venta y segmento de clientes, junto con tabla de desempeño con formato condicional y tooltips de participación
* **3. Análisis de Cohortes:** Matriz de recurrencia cruzando **Mes Cohorte** (filas) y **Mes Venta** (columnas)
## 🛠️ Herramientas Utilizadas
* **Visualización y BI:** Tableau Public
* **Documentación / Análisis:** Jupyter Notebook (`Python 3`)
