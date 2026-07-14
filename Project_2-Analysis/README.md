# Análisis del Mercado Laboral en Data Science

## Introducción

Como profesional orientado al análisis de datos y en constante búsqueda de crecimiento laboral, siempre me llamó la atención la falta de claridad respecto a qué habilidades generan un verdadero impacto en la remuneración dentro del mercado de Data Science. Con este proyecto me propuse analizar qué tecnologías demandan las empresas líderes y cómo orientarse hacia puestos mejor pagos.

Este trabajo forma parte de los proyectos prácticos realizados dentro de la certificación de Excel de **Luke Barousse**.

### Preguntas Clave del Análisis

Para entender la dinámica del mercado laboral, planteé las siguientes preguntas:

1. **¿Sumar más habilidades garantiza un mejor salario?**
2. **¿Cómo varía la remuneración de los roles de datos según la región geográfica?**
3. **¿Cuáles son las habilidades más demandadas por las empresas?**
4. **¿Cuánto pagan las 10 habilidades más requeridas?**

### Habilidades de Excel Aplicadas

Para este desarrollo utilicé técnicas avanzadas de procesamiento y modelado:

- **📊 Tablas Dinámicas (Pivot Tables)**
- **📈 Gráficos Dinámicos (Pivot Charts)**
- **🧮 Lenguaje DAX (Data Analysis Expressions)**
- **🔍 Power Query (ETL)**
- **💪 Power Pivot (Modelado Relacional)**

### Dataset Utilizado

El dataset incluye ofertas laborales reales del sector de Data Science obtenidas durante 2023, provisto en la certificación de Luke Barousse. Incluye campos detallados como:

- **👨‍💼 Títulos de puestos**
- **💰 Salarios anuales**
- **📍 Ubicación geográfica**
- **🛠️ Habilidades técnicas asociadas**

## 1️⃣ ¿Sumar más habilidades garantiza un mejor salario?

### 🔍 Herramienta: Power Query (ETL)

#### 📥 Extracción

- Utilicé Power Query para extraer los datos originales del archivo (`data_salary_all.xlsx`) y estructurar dos consultas independientes:
    - 🗃️ Primera consulta con la totalidad de los datos de las ofertas laborales.
    - 🔧 Segunda consulta asociando las habilidades específicas (`skills`) a cada ID de puesto.

#### 🔄 Transformación

- Transformé ambas consultas ajustando tipos de datos, eliminando columnas innecesarias, aplicando limpieza de texto para remover palabras específicas y eliminando espacios en blanco sobrantes.

#### 🔗 Carga

- Cargué ambas consultas transformadas directamente al Modelo de Datos, dejando la estructura lista para el análisis relacional.

### 📊 Análisis

#### 💡 Insights

- 📈 Existe una correlación positiva entre la cantidad de habilidades requeridas en una oferta y la mediana salarial, especialmente en roles avanzados como Senior Data Engineer y Data Scientist.
- 💼 Puestos con requerimientos técnicos más acotados, como Business Analyst, registran medianas salariales más bajas, demostrando que la especialización técnica incrementa el valor de mercado del profesional.

#### 🤔 Diagnóstico / Conclusión Práctica

- Esta tendencia confirma la importancia estratégica de incorporar habilidades técnicas clave si el objetivo es acceder a posiciones de alta remuneración.

## 2️⃣ ¿Cómo varía la remuneración de los roles de datos según la región geográfica?

### 🧮 Herramientas: Tablas Dinámicas & DAX

#### 📈 Tabla Dinámica

- Construí una Tabla Dinámica conectada directamente al Modelo de Datos de Power Pivot.
- Ubiqué la columna `job_title_short` en las filas y el campo `salary_year_avg` en los valores.
- Creé una medida en DAX para calcular la mediana salarial específica de las ofertas dentro de Estados Unidos:

    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States"
    )

#### 🧮 DAX

- Para obtener la mediana salarial global utilicé la siguiente medida:

    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])

### 📊 Análisis

#### 💡 Insights

- 💼 Roles como Senior Data Engineer y Data Scientist mantienen las medianas salariales más altas tanto en EE. UU. como a nivel internacional, reflejando la fuerte demanda global de perfiles senior.
- 💰 La brecha salarial entre Estados Unidos y el resto del mundo es considerablemente marcada en puestos de tecnología avanzada, influenciada por la concentración de empresas tech en dicho mercado.

#### 🤔 Diagnóstico / Conclusión Práctica

- Estos datos son clave al momento de evaluar propuestas laborales, negociar salarios o definir objetivos de carrera con proyección internacional.

## 3️⃣ ¿Cuáles son las habilidades más demandadas por las empresas?

### 🔧 Herramienta: Power Pivot

#### 💪 Power Pivot

- Integré las tablas `data_jobs_all` y `data_jobs_skills` dentro de un mismo Modelo de Datos relacional.
- Al contar con datos limpios desde Power Query, establecí las relaciones necesarias entre ambas tablas sin redundancias.

#### 🔗 Modelo de Datos

- Vinculé ambas tablas mediante la clave primaria/foránea del campo `job_id` para permitir análisis multidimensionales.

#### 📃 Menú de Power Pivot

- Utilicé la interfaz de Power Pivot para administrar el modelo, definir jerarquías y calcular medidas personalizadas con DAX.

### 📊 Análisis

#### 💡 Insights

- 💻 SQL y Python lideran de manera absoluta como los requisitos más solicitados, consolidándose como los cimientos técnicos indispensables para el análisis y procesamiento de datos.
- ☁️ Tecnologías Cloud como AWS y Azure muestran una presencia cada vez mayor, evidenciando la migración del mercado hacia arquitecturas en la nube y Big Data.

#### 🤔 Diagnóstico / Conclusión Práctica

- Identificar el stack tecnológico dominante permite priorizar el aprendizaje de las herramientas con mayor retorno sobre la inversión de tiempo y estudio.

## 4️⃣ ¿Cuánto pagan las 10 habilidades más requeridas?

### 📊 Herramienta: Gráficos Dinámicos Avanzados (Pivot Chart)

#### 📈 Pivot Chart Combinado

- Creé un gráfico combinado para contrastar la mediana salarial frente al porcentaje de presencia de cada habilidad:
    - 🪙 **Eje Principal:** Mediana Salarial (Gráfico de Columnas Agrupadas)
    - 👍 **Eje Secundario:** Porcentaje de Frecuencia de la Habilidad (Línea con Marcadores)
- Personalicé el gráfico ajustando títulos de ejes, limpiando líneas de cuadrícula y destacando los marcadores clave.

### 📊 Análisis

#### 💡 Insights

- 💰 Las medianas salariales más elevadas están directamente asociadas al dominio de herramientas como Python, Oracle y SQL.
- 📉 Herramientas de ofimática tradicional como PowerPoint o Word presentan la menor frecuencia y las medianas salariales más bajas, confirmando que no aportan diferencial en roles analíticos de alto nivel.

### 🤔 Diagnóstico / Conclusión Práctica

- El gráfico demuestra visualmente que enfocar la capacitación en tecnologías avanzadas (Python, SQL, Cloud) impacta de manera directa en las aspiraciones salariales dentro de la industria tech.

## Conclusión

Desarrollé este proyecto analítico aplicando las herramientas avanzadas de Excel aprendidas en la certificación con Luke Barousse. A partir de datos reales del mercado laboral de Data Science, logré identificar patrones claros sobre qué tecnologías y niveles de especialización impulsan las mejores oportunidades salariales. Este trabajo refleja mi capacidad para transformar datos crudos en información estratégica para la toma de decisiones.
