# Dashboard de Análisis de Ingresos, Costos y Utilidades

## Descripción:
Este dashboard tiene como objetivo proporcionar una visión clara y detallada de los ingresos, costos y utilidades de una empresa, desglosados por producto y período de tiempo. Es una herramienta útil para analizar el rendimiento financiero de cada producto, identificar tendencias de ingresos y costos, y calcular la utilidad neta. Está diseñado para ayudar a gerentes y analistas a tomar decisiones basadas en datos que optimicen la rentabilidad.

## Elementos del Dashboard:

### 1. **Datos Utilizados:**

- **Fact_Costos:** Contiene información sobre el costo total por producto.
- **Fact_Ingresos:** Contiene datos de las cantidades vendidas y el precio unitario de venta.
- **Fact_Gastos:** Contiene el total de gastos generales relacionados con los productos.

### 2. **Tablas y Transformaciones:**

- Se crearon dos copias de las tablas `Fact_Costos` y `Fact_Ingresos`, llamadas `Productos_Costos` y `Productos_Ingresos`.
- Se eliminaron todas las columnas innecesarias de las tablas duplicadas, dejando solo la columna de productos.
- Estas tablas fueron combinadas en una nueva tabla llamada `Productos`, donde se eliminaron los duplicados de la columna `productos`.
- Se deshabilitó la carga de las tablas `Productos_Costos` y `Productos_Ingresos` para optimizar el rendimiento.
- Finalmente, se creó una tabla que contiene los productos sin duplicar, con el propósito de relacionar las facturas de costos y de ingresos.

### 3. **Medidas DAX Utilizadas:**

- **Ingreso:**
  ```DAX
  Ingreso = SUMX(Fact_Ingresos, Fact_Ingresos[Cantidades] * Fact_Ingresos[Venta Unit])
