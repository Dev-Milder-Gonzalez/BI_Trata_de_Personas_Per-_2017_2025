# BI Estratégico: Trata de Personas en el Perú (Enero 2017 – Septiembre 2025)  
**Dirección contra la Trata de Personas y Tráfico Ilícito de Migrantes – DIRCTP-PNP**  
**Ministerio del Interior del Perú**  

**Autor del análisis:**  
**Milder González Dávila**  
Analista de Datos  
Diciembre 2025  

**Fuente oficial:**  
[Portal Nacional de Datos Abiertos – Trata de Personas](https://www.datosabiertos.gob.pe/dataset/trata-de-personas)  
Archivo: `DataSet_trata_personas_enero2017_septiembre2025.xlsx`  

**Repositorio GitHub:**  
https://github.com/Dev-Milder-Gonzalez/BI_Trata_de_Personas_Per-_2017_2025.git

**Versión del proyecto:** v1.0 – Finalizada

---

### Introducción y Objetivo  
Este proyecto presenta un análisis exhaustivo del delito de trata de personas en el Perú, basado en datos oficiales del Ministerio del Interior (MININTER). El objetivo es proporcionar insights accionables para políticas de prevención, mediante:  
- Evolución temporal de casos (por año y mes)  
- Perfil de víctimas (edad, sexo)  
- Medios de captación y explotación  
- Destino de los casos y vínculos con el tratante  
- Tipos de reclutamiento (Nacional y Internacional)

El análisis se enfoca en resultados reales, con visualizaciones claras para facilitar la toma de decisiones en instituciones como la DIRCTP-PNP o el Viceministerio del Interior.  

Todos los cálculos evitan duplicados, usando totales reales del dataset (por ejemplo, C_TOTAL para captación).  

### Requisitos y Ejecución  
- **Ambiente:** Python 3.12+ con librerías en `requirements.txt` (pandas, numpy, matplotlib, seaborn, openpyxl).  
- **Ejecución:**  
  1. Clona el repositorio.  
  2. Instala dependencias: `pip install -r requirements.txt`  
  3. Abre con VS Code (extensión Jupyter) o Jupyter Lab: `jupyter lab`  
  4. Ejecuta los notebooks en orden: 00 → 01 → 02 → 03. Para mostar la → usamos ```Alt + 26```
- **Archivos generados:** Gráficos en `reports/` (subcarpetas por tipo).  

### Estructura del Proyecto  
La estructura está organizada para un flujo de trabajo claro: carga, limpieza, análisis y visualización.  

```
Trata_personas_Enero2017_Septiembre2025/
├── data/
│   ├── processed/
│   │   └── dataset_maestro_wide.xlsx          ← Dataset maestro limpio y pivootedo, listo para el análisis
│   │
│   └── raw/
│       └── DataSet_trata_personas_enero2017_septiembre2025.xlsx  ← DataSet original
│
├── Notebook/
│   ├── 00_Exploracion_Data_Set.ipynb          ← Verificación inicial del dataset
│   ├── 01_ETL_DataSet_Maestro.ipynb           ← Limpieza y creación del dataset maestro
│   ├── 02_Analisis_Descriptivo_General.ipynb  ← Análisis general y series de tiempo
│   └── 03_Analisis_por_categoria.ipynb        ← Análisis detallado por categoría y subcategoría
│
├── reports/
│   ├── Analisis_categoria_subcategoria/       ← Gráficos por subcategorías
│   └── Series_tiempo/                         ← Series temporales
│       └── Porcentaje_de_mujeres_varones_victimas_en_todo_el_periodo.png  ← Análisis de varones y mujeres víctimas
├── README.md                                  ← Este archivo
└── requirements.txt                           ← Dependencias del proyecto
```

### Resultados Clave (Basados en el Dataset Oficial)  
- **Total de víctimas:** 5,058 (sacado de EM_EF_TOTAL_EM_EF_TOTAL).  
- **Víctimas mujeres:**  4,493 → **88.8%** del total.  
- **Víctimas hombres:** 565 → 11.2% del total.  
- **Menores de edad:** Pico de 136 casos en 2018. Tendencia a la baja post-pandemia, pero 2025 ya tiene 31 casos en 9 meses.  
- **Explotación sexual:** 2,877 casos (56.0%). Pico de 504 en 2018; 169 en 2025 hasta septiembre.  
- **Captación por oferta de trabajo falsa:** 3,485 casos (67.8%). Es el método dominante.  
- **Medio empleado por el tratante:** Engaño lidera con 3,016 casos (58.7%).  
- **Destino de los casos:** Fiscalía recibe 2,649 (51.5%); pendiente de investigación: 550.  
- **Vínculo con el tratante:** "Otro (especificar)" es el más común (4,300 casos, 83.6%).  
- **Reclutamiento:** Nacional (3,970 casos, 77.2%) vs Internacional (1,172, 22.8%).  
- **Finalidad del delito:** Explotación sexual domina (2,877); laboral: 1,054; no identificado: 962.  
- **Explotación por tipo:** "Otro especificar" (3,444); prostíbulo: 294; night club: 290.  

### Gráficos Generados (en reports/)  
- **Series_tiempo/**:  
  - Menores de edad por año-mes (pico en 2018).  
  - Víctimas de explotación sexual por año-mes (rebrote post-pandemia).  
  - Explotación por año-mes.  
  - Menores de edad por año.  
  - % Mujeres por año (oscila entre 79% y 92%).  
  - Explotación sexual anual.  

- **Analisis_categoria_subcategoria/**:  
  - Hombres víctimas por grupo de edad (18-29 años: 201 casos).  
  - Medio empleado por el tratante (engaño: 3,016).  
  - Totales por subcategoría de CAPTACIÓN (oferta trabajo: 3,485).  
  - Destino de los delitos (Fiscalía: 2,649).  
  - Cantidad por tipo de vínculos con el tratante ("Otro especificar": 4,300).  
  - Mujeres y hombres víctimas (pie chart: 88.8% mujeres).  
  - Mujeres víctimas por grupos de edad (18-29 años: 2,183).  
  - Internacional vs Nacional (nacional: 3,970).  
  - Finalidad del tipo de delito (sexual: 2,877).  
  - Cantidad por tipo de explotación ("Otro especificar": 3,444).  

### Recomendaciones Estratégicas  
1. **Enfoque de género:** Dado que el 88.8% son mujeres, priorizar programas de prevención para mujeres de 18-29 años.  
2. **Combate a captación:** Campaña contra ofertas falsas de trabajo (67.8% de casos).  
3. **Fortalecimiento judicial:** El 51.5% en Fiscalía – asignar más recursos para agilizar.  
4. **Protección a menores:** Aunque bajaron, los 1,567 casos exigen más educación escolar.  
5. **Presupuesto:** Solicitar S/45 millones para RETA-PNP 2026, enfocado en ciberdelitos.  

Este proyecto está listo para auditoría interna o presentación oficial.  

**Milder González Dávila**  
Diciembre 2025  