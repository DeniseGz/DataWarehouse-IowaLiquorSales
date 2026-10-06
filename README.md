# 🍹 Data Warehouse & Pipeline ETL – Iowa Liquor Sales 🍸

<p align="center">
  <img src="https://img.shields.io/badge/PYTHON-8E4A23?style=flat&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/PANDAS-6F381B?style=flat&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/GOOGLE%20COLAB-F39C12?style=flat&logo=googlecolab&logoColor=white" />
  <img src="https://img.shields.io/badge/ETL-D35400?style=flat&logoColor=white" />
  <img src="https://img.shields.io/badge/DATA%20WAREHOUSE-B9770E?style=flat&logoColor=white" />
  <img src="https://img.shields.io/badge/DBDIAGRAM.IO-A04000?style=flat&logoColor=white" />
  <img src="https://img.shields.io/badge/GIT-512E5F?style=flat&logo=git&logoColor=white" />
</p>

Repositorio oficial del proyecto de modelado dimensional e ingeniería de datos para el análisis de ventas del estado de Iowa. 🍹

## 🍷 Descripción del Proyecto 🏗️
Este proyecto aborda la ingesta, limpieza, modelado y estructuración de un dataset masivo de más de **593,000 registros (120 MB)** de ventas de licor. El objetivo principal fue transformar datos crudos y desnormalizados en una arquitectura de almacenamiento optimizada para consultas analíticas de alto rendimiento (Business Intelligence).

## 🏛️ Arquitectura: Modelo Estrella (Star Schema) 💫🌟
Se diseñó un esquema lógico relacional enfocado en la separación clara entre las métricas de negocio y su contexto descriptivo, implementado en `dbdiagram.io`:

- **Tabla de Hechos (`hecho_ventas`):** Núcleo transaccional que almacena las métricas clave de cada venta (cantidad vendida, monto total y volumen en litros) junto a las claves foráneas de relación.
- **Dimensiones (`Star Esquinadas`):**
  - `dim_tiempo`: Desglose cronológico de las transacciones (fecha, mes, trimestre, año, día de la semana).
  - `dim_tienda`: Catálogo geográfico y nominal de los puntos de venta (dirección, ciudad, condado).
  - `dim_producto`: Especificaciones y categorización del inventario (artículo, categoría, volumen de botella, precio unitario).
  - `dim_proveedor`: Datos de origen de los fabricantes y distribuidores.

## ⚙️ Ingeniería de Datos & Pipeline ETL
El procesamiento de los datos se desarrolló mediante scripts en **Python (Pandas)** ejecutados en entornos cloud (Google Colab) para garantizar escalabilidad y evitar cuellos de botella locales:
- **Limpieza y Filtrado:** Tratamiento de valores nulos, normalización de cadenas de texto y eliminación de anomalías estructurales en el dataset original.
- **Generación de Catálogos Únicamente Normalizados:** Extracción de entidades maestras (como el mapeo único de las más de 2,000 tiendas y productos) para asegurar la integridad referencial del modelo dimensional.

## 🛠️ Tecnologías y Herramientas Utilizadas
- **Python / Pandas:** Procesamiento y transformación de datos (ETL).
- **Google Colab:** Entorno de ejecución en la nube para manejo eficiente de grandes volúmenes de datos.
- **dbdiagram.io:** Modelado conceptual y lógico de bases de datos.
- **Markdown / Git:** Documentación y versionado del proyecto.
