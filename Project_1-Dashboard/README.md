# Excel Salary Dashboard

## Introducción

Desarrollé este dashboard interactivo de salarios en el mercado de datos con el objetivo de analizar la relación entre roles, ubicaciones geográficas y remuneración, ayudando a profesionales a evaluar si su compensación está alineada con el mercado actual.

Este proyecto fue realizado como parte de la certificación de Excel de **Luke Barousse**, donde apliqué herramientas clave para el análisis dinámico de datos. El dataset contiene información detallada sobre títulos de puestos, salarios, ubicaciones y habilidades requeridas en la industria.

### Archivo del Dashboard
Podés explorar el archivo ejecutable del proyecto en: [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Habilidades de Excel Aplicadas

Durante el desarrollo del análisis utilicé las siguientes herramientas de Excel:

- **📉 Gráficos dinámicos e interactivos**
- **🧮 Fórmulas y Funciones complejas**
- **❎ Validación de Datos avanzada**

### Dataset de Empleos en Datos

El conjunto de datos utilizado incluye ofertas de trabajo reales del sector de Data Science en 2023, provisto durante la certificación. Contiene información clave sobre:

- **👨‍💼 Títulos de puestos**
- **💰 Salarios anuales**
- **📍 Ubicación geográfica**
- **🛠️ Habilidades técnicas**

## Construcción del Dashboard

### 📉 Gráficos

#### 📊 Salarios por Rol en Data Science - Gráfico de Barras

- 🛠️ **Funcionalidades de Excel:** Implementación de gráficos de barras con formato personalizado de valores salariales y optimización de diseño para lectura rápida.
- 🎨 **Decisión de Diseño:** Gráfico de barras horizontal para facilitar la comparación visual entre las medianas salariales.
- 📉 **Organización de Datos:** Ordenamiento descendente de los puestos según remuneración para mejorar la legibilidad.
- 💡 **Insights:** Permite detectar rápidamente tendencias salariales, destacando que los roles Senior y de Ingeniería superan ampliamente la compensación de los puestos de Análisis.

#### 🗺️ Mediana Salarial por País - Gráfico de Mapa

- 🛠️ **Funcionalidades de Excel:** Uso del gráfico de mapa de Excel para proyectar las medianas salariales a nivel global.
- 🎨 **Decisión de Diseño:** Mapa con escala de color para diferenciar visualmente los niveles de ingresos entre regiones.
- 📊 **Representación de Datos:** Mapeo de la mediana salarial para cada país con datos disponibles.
- 👁️ **Mejora Visual:** Interpretación inmediata de las brechas geográficas en la industria tecnológica.
- 💡 **Insights:** Facilita la comprensión de la disparidad salarial global, identificando zonas de alta y baja remuneración.

### 🧮 Fórmulas y Funciones

#### 💰 Mediana Salarial según Título del Puesto

    =MEDIAN(
    IF(
        (jobs[job_title_short]=A2)*
        (jobs[job_country]=country)*
        (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
        (jobs[salary_year_avg]<>0),
        jobs[salary_year_avg]
    )
    )

- 🔍 **Filtrado Multicriterio:** Evalúa simultáneamente el título del puesto, el país y el tipo de jornada, excluyendo registros sin salario reportado.
- 📊 **Fórmula Matricial:** Aplica `MEDIAN()` combinada con la función `IF()` anidada para procesar matrices de datos.
- 🎯 **Insights a Medida:** Genera métricas salariales precisas ajustadas según el tipo de contratación y región.
- **🔢 Propósito de la Fórmula:** Esta fórmula alimenta la tabla base, devolviendo la mediana salarial en función del puesto, país y jornada seleccionados.

#### ⏰ Conteo por Tipo de Jornada Laboral

    =FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))

- 🔍 **Generación de Listas Únicas:** Utiliza la función `FILTER()` para limpiar la lista eliminando registros compuestos (con "and" o comas) y valores nulos.
- **🔢 Propósito de la Fórmula:** Poblar la lista desplegable del dashboard con tipos de jornada limpios y sin duplicados.

### ❎ Validación de Datos

#### 🔍 Listas Filtradas Dinámicas

- 🔒 **Validación Avanzada:** Implementación de reglas de validación en los filtros de `Job Title`, `Country` y `Type` desde la solapa Datos:
    - 🎯 Restringe la entrada de usuario a valores validados y predefinidos.
    - 🚫 Previene errores o inconsistencias en el filtrado del dashboard.
    - 👥 Optimiza la usabilidad y la experiencia de usuario (UX).

## Conclusión

Desarrollé este dashboard para exponer insights concretos sobre la estructura salarial en el mercado de datos. Aplicando lo aprendido en la certificación con Luke Barousse, creé una herramienta orientada a la toma de decisiones profesionales, permitiendo analizar de manera directa cómo influyen la ubicación y el tipo de puesto en la remuneración.
