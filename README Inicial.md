# RetailPro | Proyecto de análisis de ventas

## Descripción

RetailPro es un proyecto académico de análisis de ventas que integra una base de datos relacional en **Microsoft SQL Server**, consultas de negocio en **SQL** y un modelo de análisis en **Power BI**. El objetivo es organizar información de ventas, clientes, productos y categorías, y facilitar la exploración de indicadores comerciales.

## Herramientas utilizadas

- **Microsoft SQL Server**: almacenamiento y relaciones de la base de datos.
- **SQL Server Management Studio (SSMS)**: ejecución y revisión de scripts T-SQL.
- **SQL (T-SQL)**: creación de tablas, carga de registros, consultas de agregación y `JOIN`.
- **Power BI Desktop**: transformación, modelado, medidas DAX y visualización de datos.
- **Power Query**: limpieza y preparación de datos para el modelo analítico.
- **GitHub**: versionado y publicación de entregables.
- **IA generativa (ChatGPT)**: apoyo en la revisión de consultas y documentación, sujeto a validación manual.

## Modelo de datos SQL

La base de datos se llama **`Ventas_Tech_DB`** y contiene cuatro tablas:

| Tabla | Contenido |
| --- | --- |
| `clientes` | Datos de clientes y fecha de registro |
| `categorias` | Categorías de productos |
| `productos` | Catálogo de productos, precios, stock y categoría |
| `ventas` | Operaciones de venta, cantidades, precios unitarios y fechas |

Las tablas se relacionan mediante claves primarias y foráneas. El script de inicialización incluye registros de ejemplo para practicar las consultas.

## Scripts SQL

| Archivo | Función |
| --- | --- |
| `ventas_tech_db.sql` | Crea `Ventas_Tech_DB`, define las cuatro tablas, carga datos de ejemplo y ejecuta consultas básicas de validación. |
| `m4_consultas_negocio.sql` | Analiza facturación mensual, productos destacados, clientes recurrentes y meses respecto del promedio de facturación. |
| `m5_consultas_joins.sql` | Incluye una vista base con `INNER JOIN` entre cuatro tablas, búsquedas con `LEFT JOIN` y un consolidado con `UNION ALL`. |

> **Nota:** Los nombres anteriores corresponden a los scripts revisados para esta documentación. Si en GitHub se encuentran dentro de carpetas, es necesario abrir la carpeta correspondiente antes de ejecutarlos.

## Cómo ejecutar los scripts SQL

### Requisitos

1. Tener una instancia accesible de **Microsoft SQL Server**.
2. Tener instalado **SQL Server Management Studio (SSMS)** o una herramienta compatible con T-SQL y separadores `GO`.
3. Contar con permisos para crear una base de datos y sus tablas.

### Orden de ejecución

1. Abrir **SSMS** y conectarse a la instancia de SQL Server.
2. Abrir `ventas_tech_db.sql` desde **Archivo > Abrir > Archivo**.
3. Revisar el script y ejecutarlo con **Ejecutar** o **F5**. Se creará o reutilizará `Ventas_Tech_DB`, se definirán las tablas y se insertarán los datos de ejemplo.
4. Abrir `m4_consultas_negocio.sql` y ejecutarlo. Revisar los resultados de las cuatro consultas comerciales.
5. Abrir `m5_consultas_joins.sql` y ejecutarlo. Revisar los resultados de las consultas con relaciones y consolidaciones.

**Advertencia importante:** `ventas_tech_db.sql` contiene instrucciones `DROP TABLE IF EXISTS`. **Al volver a ejecutarlo se eliminan y recrean las tablas del proyecto**, por lo que se perderán los datos que se hubieran agregado posteriormente. Usarlo únicamente en una base de práctica o después de realizar un respaldo.

Los scripts de los Módulos 4 y 5 comienzan con `USE Ventas_Tech_DB;` y consultan los datos sin modificar las tablas.

### Verificación básica

El script inicial contiene consultas `SELECT *` para revisar la carga. Con los datos de ejemplo incluidos, se esperan **4 categorías, 5 clientes, 6 productos y 10 ventas**. Estos recuentos corresponden al script de práctica, no necesariamente al conjunto de datos utilizado posteriormente en Power BI.

## Trabajo en Power BI

En Power BI se desarrolló un modelo analítico con tablas de clientes, productos, categorías, ventas y calendario (`Dim_Fechas`), relaciones de filtro en una sola dirección y medidas DAX organizadas en `_Medidas`.

Entre las medidas utilizadas se encuentran:

- `Total Ventas`
- `Ventas YTD`
- `Ventas LY`
- `% Crecimiento Anual`
- `Ventas Online`

El modelo incluye una matriz de validación por mes y año. El archivo de la preentrega del Módulo 8 está disponible en [Pacio_Claudio_Checkpoint2.pbix](https://github.com/cpacio24-cell/Modulo-8/blob/main/Pacio_Claudio_Checkpoint2.pbix).

**Importante:** el conjunto de datos del modelo de Power BI puede diferir de los diez registros de ejemplo del script SQL inicial. No se deben comparar los totales de ambos entornos sin verificar antes sus fuentes y períodos.

## Uso responsable de IA

La IA se utiliza como asistente para proponer mejoras de SQL, resumir resultados y redactar documentación. Las propuestas requieren revisión técnica: validar sintaxis, contrastar cifras con los resultados de SQL Server y verificar que las recomendaciones tengan sentido para el negocio. La responsabilidad final del análisis corresponde a quien lo presenta.

## Autor

Claudio Pacio — proyecto académico RetailPro.
