# Proyecto DataSalud Perú - Parte 3: Procesamiento Distribuido y Benchmark (Spark)

Este directorio contiene los entregables técnicos correspondientes a la **Parte 3** del proyecto, centrada en el procesamiento de datos a gran escala mediante **Apache Spark (PySpark)** en Google Colab y la ejecución del benchmark de rendimiento comparado con bases de datos relacionales.

---

## 📂 Estructura de Archivos
* `Spark/`: Contiene el notebook ejecutable (`.ipynb`) con el código fuente del pipeline ETL, transformaciones y consultas SparkSQL.

---

## ⚙️ Descripción del Flujo Técnico (PySpark)

1. **Inicialización del Entorno:** Configuración de la sesión de `SparkSession` optimizada para el análisis de los datasets institucionales.
2. **Carga de Datasets en Bruto:** Ingesta de los archivos fuente de salud (`CRED` e `INEN`) manejando correctamente delimitadores y codificaciones específicas (`iso-8859-1` y `UTF-8`).
3. **Limpieza y Normalización:** 
   * Creación de la columna normalizada `estado_cred_normalizado` a partir de la validación del campo `flag_cnv`.
   * Selección, estandarización y unificación de esquemas para variables críticas (ubicación geográfica, sexo, edad).
4. **Agregación Distribuida (SparkSQL):** Registro de vistas temporales (`vista_cred`, `vista_inen`) para ejecutar agrupamientos masivos (`groupBy` y `agg`) forzando la ejecución en memoria (*in-memory*).

---

## 📊 Resultados del Benchmark de Rendimiento

* **Apache PySpark:** Procesamiento distribuido optimizado para grandes volúmenes de registros.
* **SQL Server:** Motor relacional tradicional utilizado como línea base comparativa (con un tiempo estándar de referencia de `4.2000` segundos).
* **Conclusión Técnica:** La arquitectura de procesamiento en memoria (*in-memory*) de Apache Spark supera al motor relacional tradicional al gestionar volúmenes masivos de datos con menor latencia operativa.
