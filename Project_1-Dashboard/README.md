# Dashboard de Salarios en Data Jobs

## Introducción
Dashboard interactivo desarrollado para analizar la relación entre roles, ubicación y remuneración en el mercado de Data Science. Este proyecto surge como parte del curso de **Luke Barousse**, con el objetivo de dotar a profesionales de datos de una herramienta para auditar su propia compensación basada en el mercado actual.

## Funcionalidades Técnicas
El dashboard utiliza fórmulas avanzadas para permitir la selección de múltiples criterios dinámicos sin necesidad de macros.

### Lógica de Filtrado (Excel Formula)
Para el cálculo de la mediana bajo condiciones complejas, se implementó:
=MEDIAN(
    IF(
        (jobs[job_title_short]=A2)*
        (jobs[job_country]=country)*
        (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
        (jobs[salary_year_avg]<>0),
        jobs[salary_year_avg]
    )
)

### Gestión de Listas Únicas
Uso de la función FILTER para extraer tipos de jornada dinámicos, eliminando ruido (valores nulos o términos duplicados):
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))

## Tecnologías y Habilidades Aplicadas
* **Excel:** Funciones matriciales (Array Formulas), Validación de datos (Dropdowns), Mapas de calor y Gráficos interactivos.
* **Data Viz:** Gráficos de barras optimizados para lectura rápida de medianas salariales.
* **UI/UX:** Interfaz de usuario intuitiva mediante listas de validación conectadas dinámicamente al backend de datos.

## Archivo del Proyecto
Puedes explorar el análisis completo en: 1_Salary_Dashboard.xlsx
