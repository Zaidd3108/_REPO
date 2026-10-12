🏥 DataSalud Perú - Executive Analytics & Data Warehouse Solution

Bienvenido al repositorio oficial del proyecto DataSalud Perú. Esta solución integra arquitectura de datos avanzada, ETL/ELT con PySpark, modelado dimensional en SQL Server y un dashboard ejecutivo interactivo en Power BI para el análisis consolidado de atenciones sanitarias a nivel nacional, combinando los flujos del INEN (Lima) y CRED (Junín).

🗂️ Estructura del Repositorio

La arquitectura de carpetas está organizada según los estándares del ciclo de vida de Business Intelligence y Data Analytics:

.
├── Spark/
│   └── PySpark.ipynb             # Scripts ETL y procesamiento distribuido de datos masivos.
├── docs/
│   ├── Esquema Constelación.png  # Diagrama de modelo de datos avanzado (Constelación).
│   ├── INFORME.pdf               # Informe técnico completo del proyecto.
│   ├── Modelo Copo de Nieve.png  # Arquitectura del modelo multidimensional (Snowflake).
│   └── PRESENTACIÓN.pdf          # Slides ejecutivas de la solución.
├── powerbi/
│   └── DataSaludPeru_Reporte.pbix # Dashboard interactivo ejecutivo en Power BI.
├── sql/
│   └── DataSaludPeru_DW.bak      # Backup completo del Data Warehouse (SQL Server).
└── README.md                     # Documentación principal del repositorio.


🚀 Componentes de la Solución

1. 🐍 Procesamiento de Datos (Spark)

Spark/PySpark.ipynb: Cuaderno de Jupyter que ejecuta la extracción, limpieza, normalización y transformación de datasets heterogéneos de salud pública (atenciones oncológicas INEN y controles de desarrollo infantil CRED) mediante PySpark.

2. 🗄️ Data Warehouse & Modelado Dimensional (SQL)

sql/DataSaludPeru_DW.bak: Copia de seguridad del Data Warehouse en SQL Server.

Contiene el esquema estrella/constelación compuesto por:

Tabla de Hechos Consolidada: Fact_AtencionesSanitarias (medida central CantidadAtenciones).

Tablas de Hechos Específicas: Fact_Paciente (INEN) y Fact_CRED (Junín).

Tablas de Dimensión: Dim_Ubigeo, Dim_Tiempo, Dim_ServicioSalud, Dim_Paciente.

3. 📊 Dashboard Ejecutivo (Power BI)

powerbi/DataSaludPeru_Reporte.pbix: Dashboard analítico interactivo diseñado para la toma de decisiones gerenciales.

Características principales:

KPIs Consolidados: Visualización a nivel entero de atenciones generales, INEN y CRED.

Segmentación Dinámica: Botonera interactiva tipo Mosaico (Tile) para alternar al instante entre sedes (LIMA vs. JUNÍN).

Analítica Visual: Gráficos de barra por especialidad, anillo demográfico por sexo, tendencia temporal y análisis de distribución por provincias.

4. 📄 Documentación y Reportes

docs/: Incluye los informes en PDF y los diagramas esquemáticos que respaldan el diseño del Data Warehouse y la presentación técnica ante los directivos.

🛠️ Requisitos e Instalación

Base de Datos:

Restaurar el archivo DataSaludPeru_DW.bak en SQL Server 2019 o superior.

Entorno PySpark:

Apache Spark 3.x, Python 3.8+ y Jupyter Notebook.

Power BI Desktop:

Abrir DataSaludPeru_Reporte.pbix con la versión más reciente de Power BI Desktop.

Reconfigurar la cadena de conexión de origen de datos apuntando al servidor SQL donde se restauró la base de datos.

👨‍💻 Autor y Licencia

Desarrollado para la optimización de la gestión de información y toma de decisiones en el sector salud del Perú.

## 👥 Integrantes
- Kenneth Zaidd Machacuay Maldonado
- Yef Meylin Puntillo Calsin
- Jairo Joao Baltodano Avelino