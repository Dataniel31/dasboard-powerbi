# Dashboard de Análisis de Ingresos, Costos y Utilidades
![Captura de pantalla](https://i.ibb.co/DQCQzWt/Captura-de-pantalla-2024-09-11-235157.png)

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

  Costo = SUM(Fact_Costos[Total])

  Utilidad Costo Ingreso = [Ingreso] - [Costo]

  Gasto = SUM(Fact_Gastos[Total])

  Utilidad = [Ingreso] - [Costo] - [Gasto]


### 4. Visualizaciones Utilizadas:
- **Tarjetas**: Para mostrar las métricas clave como ingreso total, costo total, gasto total y utilidad total.
- **Gráficos de Líneas**: Utilizados para mostrar la evolución de los ingresos, costos y utilidad a lo largo del tiempo, permitiendo identificar tendencias y patrones.
- **Gráfico Circular**: Para visualizar la proporción entre ingresos, costos y gastos en términos globales.
- **Tabla Detallada**: Muestra el rendimiento financiero de cada producto individual, lo que permite identificar rápidamente los productos más y menos rentables.

### 5. Instrucciones para Usar el Dashboard:
- **Filtrar por Producto**: Usa el filtro de producto en la esquina superior derecha para analizar los ingresos, costos y utilidades de un producto en particular.
- **Analizar Tendencias**: Explora los gráficos de líneas para observar cómo se han comportado los ingresos y costos a lo largo del tiempo. Los gráficos te permitirán ver patrones estacionales o identificar períodos de alto/bajo rendimiento.
- **Revisar el Desglose por Producto**: La tabla detallada te ofrece una visión clara de cuánto ha generado cada producto en términos de ingresos, cuál fue su costo, y cuál fue su utilidad neta. Útil para la planificación de inventario y ventas.

### 6. Requisitos:
- **Power BI Desktop**: Para visualizar y personalizar el dashboard.
- **Fuente de Datos**: El dashboard está diseñado para usar datos de ingresos, costos y gastos con fechas y productos como atributos clave.

### 7. Conclusiones:
Este dashboard es una herramienta poderosa para optimizar la gestión financiera de productos, brindando una visión completa de los costos, ingresos y utilidades. Los gerentes y analistas de negocio pueden usar esta herramienta para tomar decisiones más informadas, maximizando la rentabilidad y ajustando la estrategia según los datos.

