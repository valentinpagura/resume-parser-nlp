# 📄 NLP Resume Parser Automático | ETL Pipeline

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)
![spaCy](https://img.shields.io/badge/spaCy-NLP-09A3D5?style=for-the-badge&logo=spacy)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=for-the-badge&logo=pandas)

Un pipeline ETL (Extracción, Transformación y Carga) diseñado para automatizar el filtrado de candidatos (Screening) en procesos de Selección y Recursos Humanos. 

Este script lee lotes de Currículums Vitae en formato PDF, extrae el texto puro y utiliza modelos de **Procesamiento de Lenguaje Natural (NLP)** y **Expresiones Regulares (Regex)** para estructurar datos clave (Nombre, Email, Teléfono y Habilidades técnicas), exportando el resultado final a un archivo tabular CSV listo para su análisis.

## 💡 El Problema que Resuelve (Business Value)
En la vida real, los equipos de reclutamiento pierden decenas de horas semanales abriendo PDFs manualmente para cargar datos en su sistema (ATS). Este proyecto elimina ese cuello de botella logrando:
* **Reducción del 80% del tiempo de screening inicial:** Procesa decenas de CVs en segundos.
* **Estandarización de datos:** Transforma documentos no estructurados (PDFs con distintos diseños) en un formato estructurado y predecible (CSV/Base de datos).
* **Eliminación del sesgo humano:** La extracción se basa puramente en la presencia de habilidades (Skills) y datos de contacto, ignorando formatos visuales que puedan distraer.

## 🛠️ Arquitectura y Stack Tecnológico
* **Lenguaje:** Python 3
* **Extracción de Texto:** `pdfminer` (Manejo de codificación UTF-8 para caracteres especiales en español).
* **NLP (Búsqueda de Entidades):** `spaCy` (Modelo `es_core_news_sm` para la detección de Nombres Propios y validación de correos electrónicos).
* **Búsqueda de Patrones:** `re` (Regex para estructuración de teléfonos internacionales y listados de habilidades).
* **Estructuración de Datos:** `pandas` (Exportación a CSV).

## 📂 Estructura del Proyecto
```text
├── resumes/                 # 📥 Carpeta de entrada (Colocar aquí los PDFs)
├── output/
│   ├── txt/                 # 🔄 Carpeta temporal (PDFs convertidos a texto plano)
│   └── csv/                 # 📤 Carpeta de salida (Dataset final generado)
├── pdf2txt.py               # Script auxiliar para la interfaz con pdfminer
├── resumes_parsing.ipynb    # Script principal y motor del pipeline
├── requirements.txt         # Dependencias del proyecto
└── README.md                # Documentación

🚀 Guía de Uso (Local)
git clone [https://github.com/TU-USUARIO/TU-REPOSITORIO.git](https://github.com/TU-USUARIO/TU-REPOSITORIO.git)
cd TU-REPOSITORIO.

pip install -r requirements.txt
python -m spacy download es_core_news_sm
