# Dashboard de Salarios en Data Jobs

## Introducción

Este dashboard de salarios fue desarrollado como parte del proyecto práctico del curso de **Luke Barousse**. Su objetivo es brindar a quienes buscan trabajo en el área de datos una herramienta clara para investigar salarios según el rol deseado y comparar la compensación en el mercado actual.

El análisis utiliza información detallada sobre títulos de puestos, salarios, ubicaciones y habilidades técnicas esenciales.

### Archivo del Proyecto
Puedes explorar el dashboard final aquí: [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Habilidades de Excel Aplicadas

Para este desarrollo, utilicé las siguientes funcionalidades de Excel:

- **📉 Gráficos Dinámicos:** Visualización optimizada para comparación de salarios.
- **🧮 Fórmulas y Funciones Avanzadas:** Lógica compleja para filtrado de datos.
- **❎ Validación de Datos:** Creación de listas desplegables para una experiencia de usuario interactiva.

---

## Desarrollo del Dashboard

### 📉 Gráficos
Se implementaron gráficos de barras horizontales (para comparar salarios medianos por puesto) y mapas de calor (para identificar disparidades salariales geográficas). Todo el análisis es interactivo.

### 🧮 Fórmulas Clave
- **Mediana por Puesto:** Utilizando `MEDIAN` combinado con `IF` para excluir valores nulos y filtrar por país y tipo de jornada.
- **Listado Único de Jornadas:** Empleé la función `FILTER` para limpiar la lista de tipos de trabajo.

### ❎ Validación de Datos
Configuré menús desplegables en `Job Title`, `Country` y `Type` para asegurar la integridad de los datos y mejorar la usabilidad.

## Conclusión
Este dashboard demuestra cómo transformar datos brutos en decisiones informadas. Te invito a explorar el archivo de Excel para ver todo el proceso analítico detallado.
