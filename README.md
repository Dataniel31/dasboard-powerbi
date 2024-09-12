# Dashboard de Análisis de Ingresos, Costos y Utilidades de Productos

## Descripción General:
Este dashboard ha sido desarrollado en Power BI con el objetivo de proporcionar una **visión integral** del rendimiento financiero de una serie de productos, detallando los **ingresos, costos y utilidades** asociados a cada uno. A través de este análisis visual e interactivo, los usuarios pueden explorar las tendencias de los datos en el tiempo, facilitando la **toma de decisiones estratégicas** basadas en datos reales.

## Objetivo del Dashboard:
El dashboard sirve para:
- Analizar los **ingresos, costos y utilidades** de productos.
- Comparar el desempeño financiero mes a mes y año a año.
- Identificar productos más o menos rentables a lo largo del tiempo.
- Proporcionar una vista consolidada que permita optimizar la gestión de costos y ventas.

## Funcionalidades Clave:
- **Tarjetas de Resumen:** Muestran métricas clave como costo total, ingreso total, gasto total y utilidad neta.
- **Gráficos de Tendencias:** Muestran las tendencias de ingresos y costos por mes y año, lo que permite analizar el comportamiento estacional o patrones.
- **Análisis de Utilidad:** Desglosa la utilidad por producto, mostrando la diferencia entre ingresos y costos, incluyendo los gastos generales.
- **Desglose por Producto:** Tabla detallada que ofrece una visión específica de cada producto, comparando sus costos, ingresos y utilidades.

---

## Componentes Utilizados:

### 1. **Tablas de Datos:**
- **Fact_Costos:** Contiene los datos de costos de los productos. Se duplicó para formar la tabla **Productos Costos**, donde se eliminaron las columnas innecesarias, manteniendo únicamente la columna de productos.
- **Fact_Ingresos:** Contiene los datos de ingresos por producto. También se duplicó para crear la tabla **Productos Ingresos**, con un tratamiento similar.
- **Productos:** Resultado de la unión de las tablas **Productos Costos** y **Productos Ingresos**, eliminando duplicados y quedando con una lista única de productos para relacionar con las tablas de costos e ingresos.
- **Calendario:** Generada con la función `CALENDARAUTO()`, utilizada para gestionar las fechas clave como la fecha de ingreso, venta, presupuesto y gastos.

### 2. **Relaciones:**
Las relaciones entre las tablas son fundamentales para que el análisis funcione correctamente. La tabla **Calendario** se relaciona con las fechas de las tablas de facturación, ingresos y gastos, lo que permite filtrar los datos por periodos de tiempo específicos.
