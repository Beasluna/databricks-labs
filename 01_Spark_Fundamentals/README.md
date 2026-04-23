#  01. Introducció a Databricks | Databricks Introduction

> **[EN]** Setting up the Databricks workspace and basic data ingestion.
> **[ES]** Configuración del entorno Databricks e ingesta básica de datos.

---

##  Descripción | Description

| Aspect | Details |
| :--- | :--- |
| **Objective** | Workspace setup, Volumes & Tables ingestion. |
| **Tools** | Databricks, PySpark, Unity Catalog. |
| **Language** | PySpark & SQL. |

> **[EN]** This practice covers the foundation of Databricks, exploring architecture and loading datasets into the Lakehouse.
> **[ES]** Esta práctica cubre los fundamentos de Databricks, explorando la arquitectura y cargando datasets en el Lakehouse.

---

##  Apuntes Teóricos | Theoretical Notes

###  Arquitectura de Plataforma | Platform Architecture
* **Control Plane:** The administrative brain. | *El cerebro administrativo.*
* **Data Plane:** The processing engine. | *El motor de procesamiento.*

---

##  Guía Práctica | Practical Guide

###  Ingesta desde Volúmenes | Ingestion from Volumes

```python
# Carga del dataset WorldHits | Loading the WorldHits dataset
df = spark.read.csv(
    "/Volumes/workspace/default/world_hits/WorldHits.csv", 
    header=True, 
    inferSchema=True
)
display(df.limit(20))
```

> [!NOTE]
> [EN] Volumes allow file management without immediate conversion to Hive tables.
> [ES] La estructura de Volumes permite gestionar archivos sin necesidad de convertirlos inmediatamente a tablas de Hive.

> [!TIP]
> [EN] Remember you can switch between %python and %sql for greater flexibility.
> [ES] Recuerda que puedes alternar entre %python y %sql en tus celdas para mayor flexibilidad.

> [!IMPORTANT]
> [EN] Ensure the cluster is "Running" before executing ingestion cells.
> [ES] Asegúrate de que el clúster esté en estado "Running" antes de ejecutar las celdas de ingesta.

> [!WARNING]
> [EN] If the CSV is not uploaded correctly, spark.read.csv will return a "Path not found" error.
> [ES] Si el archivo CSV no se ha subido correctamente, el comando spark.read.csv devolverá un error de "Path not found".

> [!CAUTION]
> [EN] Do not delete the volume while Spark is reading data from it.
> [ES] No elimines el volumen mientras haya procesos de Spark leyendo datos de él.

---

## 🛠️ Cómo ejecutar | How to run

| Paso | Acción (EN) | Acción (ES) |
| :--- | :--- | :--- |
| **1. ☁️ Upload** | Ensure the CSV is in `/Volumes/workspace/default/world_hits/`. | Asegúrate de que el CSV esté en la ruta indicada. |
| **2. 🔗 Attach** | Link the `.ipynb` notebook to your Databricks Cluster. | Vincula el notebook a tu clúster. |
| **3. ▶️ Run** | Execute the cells sequentially. | Ejecuta las celdas de forma secuencial. |

---

## 📂 Archivos | Files

* 📓 `Notebook_introducctorio_BSuarez.ipynb`
* 📄 `Titanic-Dataset.csv`
* 📄 `WorldHits.csv`
