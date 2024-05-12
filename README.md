# Proyecto Data Science 
## Integrantes: Sebastian Tapia, Mathias Deleg, Alejandro Peña 

# Proyecto EDEMNU, 

### Descripción del proyecto

- ### Objetivo

El objetivo principal de este proyecto es analizar la relación entre diversos factores socioeconómicos y la satisfacción laboral de las personas en Ecuador, utilizando los datos de la Encuesta Nacional de Empleo, Desempleo y Subempleo (ENEMDU) realizada por el Instituto Nacional de Estadística y Censos (INEC) de Ecuador.

### Metodología

- ### Obtención y preparación de los datos:
Se cargan los conjuntos de datos de la ENEMDU correspondientes a diferentes períodos del año 2020 y 2021.

- ### Limpieza y transformación de datos:
Se realiza un preprocesamiento de los datos, incluyendo el manejo de valores faltantes, codificación de variables categóricas y la creación de nuevas variables.

- ### Análisis exploratorio de datos:
Se llevan a cabo análisis descriptivos y visualizaciones para comprender mejor las características de los datos.

- ### Modelado:
Se utiliza un modelo de regresión logística ordenada (Ordered Logistic Regression) para examinar la relación entre la satisfacción laboral y variables explicativas como ingresos, educación, edad, horas de trabajo y estado civil. Utilizamos el modelo de regresión logística ordenada ya que es una técnica estadística utilizada para analizar datos con una variable dependiente ordinal, es decir, una variable que toma valores en categorías ordenadas (por ejemplo, bajo, medio, alto). La ecuación del modelo es: 

logit[P(Y ≤ j)] = αj - (β1X1 + β2X2 + ... + βkXk)

donde Y es la variable dependiente ordinal, j representa las categorías ordenadas de Y, α_j son los puntos de corte (thresholds) a estimar, X_i son las variables independientes y β_i son los coeficientes a estimar. Los coeficientes β_i se interpretan como el cambio en el logit de las odds acumuladas para un incremento unitario en la variable independiente correspondiente. El modelo se basa en el supuesto de líneas paralelas, que implica que los coeficientes β_i son los mismos para todas las categorías de la variable dependiente. Se utiliza la función de enlace logit para estimar la probabilidad de que una observación pertenezca a cada categoría. La implementación típica del modelo implica el uso de paquetes o bibliotecas estadísticas (como MASS o ordinal en R, o statsmodels o mord en Python) que proporcionan funciones para ajustar el modelo y evaluar su ajuste mediante métricas como pseudo R-cuadrados y pruebas de razón de verosimilitud. Las predicciones se pueden generar utilizando el modelo ajustado. Siendo este el que mejor se acopla al análisis ya que se tienen varias variables categóricas. 

### Hallazgos principales

- Los ingresos laborales, el nivel educativo y las horas de trabajo semanales tienen un impacto positivo en la satisfacción laboral.
  
- La edad tiene un efecto negativo en la satisfacción laboral, pero este efecto disminuye a medida que aumenta la edad (relación cuadrática).

- Estar casado o divorciado tiene un impacto significativo en la satisfacción laboral en comparación con ser soltero.

- Las personas con contratos permanentes tienden a estar más satisfechas en su trabajo en comparación con aquellas con contratos temporales.

### Bases de datos utilizadas
Las bases de datos utilizadas en este proyecto provienen de la Encuesta Nacional de Empleo, Desempleo y Subempleo (ENEMDU) realizada por el Instituto Nacional de Estadística y Censos (INEC) de Ecuador. Se trabajó con las siguientes bases de datos:

inec_enemdu_personas_2020_septiembre.csv: Contiene datos de las personas encuestadas en septiembre de 2020.
inec_enemdu_persona_2020_diciembre.csv: Contiene datos de las personas encuestadas en diciembre de 2020.
inec_enemdu_persona_2021_enero.csv: Contiene datos de las personas encuestadas en enero de 2021.
inec_enemdu_persona_2021_febrero.csv: Contiene datos de las personas encuestadas en febrero de 2021.
inec_enemdu_persona_2021_marzo.csv: Contiene datos de las personas encuestadas en marzo de 2021.
inec_enemdu_persona_2021_abril.csv: Contiene datos de las personas encuestadas en abril de 2021.
inec_enemdu_persona_2021_mayo.csv: Contiene datos de las personas encuestadas en mayo de 2021.
inec_enemdu_persona_2021_junio.csv: Contiene datos de las personas encuestadas en junio de 2021.
inec_enemdu_persona_2021_julio.csv: Contiene datos de las personas encuestadas en julio de 2021.
inec_enemdu_persona_2021_agosto.csv: Contiene datos de las personas encuestadas en agosto de 2021.
inec_enemdu_persona_2021_septiembre.csv: Contiene datos de las personas encuestadas en septiembre de 2021.

Estas bases de datos contienen información sobre características demográficas, nivel educativo, situación laboral, ingresos, satisfacción laboral, entre otras variables relevantes para el análisis. Se realizó un proceso de limpieza, transformación y combinación de estas bases de datos para obtener un conjunto de datos consolidado para el análisis.

### Instrucciones de instalación y ejecución

Clona este repositorio en tu máquina local.
Asegúrate de tener instalado Python 3.x y las siguientes librerías:

- pandas
- numpy
- seaborn
- matplotlib
- scipy
- statsmodels


Coloca los archivos de datos de la ENEMDU en la carpeta "bases" dentro del directorio del proyecto.
Ejecuta el script EDEMNU.py en tu entorno de desarrollo de Python.

### Dependencias y librerías

- pandas: Para la manipulación y análisis de datos.

- numpy: Para operaciones numéricas.

- seaborn: Para visualización de datos estadísticos.

- matplotlib: Para crear gráficos y visualizaciones.
- scipy: Para funciones científicas y de estadística.
- statsmodels: Para modelos estadísticos y econométricos.
