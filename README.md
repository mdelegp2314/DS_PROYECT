# Proyecto Data Science 
## Integrantes: Sebastian Tapia, Mathias Deleg, Alejandro Peña 

# Proyecto EDEMNU, 

### Descripción del proyecto

- ### Objetivo

El objetivo principal de este proyecto es analizar la relación entre diversos factores socioeconómicos y la satisfacción laboral de las personas en Ecuador, utilizando los datos de la Encuesta Nacional de Empleo, Desempleo y Subempleo (ENEMDU) realizada por el Instituto Nacional de Estadística y Censos (INEC) de Ecuador. A si como analizar las diferencias con el sector del empleo formal y si este subconjunto presenta diferencias significativas con la muestra en general. 

### Metodología

- ### Obtención y preparación de los datos:
Se utilizaron la bases dadas al inicio del curso. Se cargan los conjuntos de datos de la ENEMDU correspondientes a diferentes períodos del año 2020 y 2021, 1 año de datos en total desde septiembre de 2020 hasta septiembre de 2021. 

- ### Limpieza y transformación de datos:
Se realiza un preprocesamiento de los datos, incluyendo el manejo de valores faltantes, codificación de variables categóricas y la creación de nuevas variables. Adicionalmente, dada la extensa cantidad de información unimos todas las bases en un documento llamado filename.csv que es la base principal que se utilizara a lo largo de la investigación. Tambien, Se separa esta base en df1 que engloba toda la muestra y en df_trabajo_formal que engloba unicamente a las observaciones que pertenecen a trabajo formal. Se realiza balanceo de la base eliminando missing values y dejando observaciones con información completa. 

- ### Análisis exploratorio de datos:
Se llevan a cabo análisis descriptivos y visualizaciones para comprender mejor las características de los datos. Especificamente se analizan visualmente las relaciones entre ingreso laboral, satisfaccion laboral, años de educación, nivel de educación, tipo de contrato, estado civil, entre otras. Se generaron gráficos de barras para variables como género, estado civil, categoría de ocupación, tipo de contrato y nivel de satisfacción laboral. Estos gráficos permiten visualizar la distribución de frecuencias de cada categoría dentro de esas variables. Por ejemplo, se observó que la mayoría de las personas en la muestra completa están casadas o solteras, mientras que en el subconjunto de trabajo formal, la mayoría están casadas. Estos análisis brindan una comprensión inicial de las características demográficas y laborales de la población estudiada. Se utilizaron gráficos de dispersión (scatter plots) y gráficos de regresión lineal para explorar las relaciones entre variables numéricas. Por ejemplo, se analizó la relación entre edad e ingresos laborales, años de educación e ingresos, y horas de trabajo semanales e ingresos. Estos análisis revelaron relaciones positivas entre estas variables, lo que sugiere que a mayor edad, mayor nivel educativo y más horas de trabajo, mayores son los ingresos laborales. Sin embargo, también se observó una gran dispersión en los datos, indicando la presencia de otros factores que influyen en los ingresos. Se exploraron las relaciones entre la satisfacción laboral y otras variables como el nivel de instrucción y el tipo de contrato. Se utilizaron gráficos de dispersión y diagramas de caja y bigotes (box plots) para visualizar estas relaciones. Los resultados sugieren que, en general, a mayor nivel de instrucción, mayor es la satisfacción laboral. Además, las personas con contratos permanentes tienden a estar más satisfechas en comparación con aquellas con contratos temporales.Se realizaron tareas de limpieza y transformación de datos, como el manejo de valores faltantes, la codificación de variables categóricas y la creación de nuevas variables. Se eliminaron los valores atípicos (outliers) en variables como ingresos laborales y horas de trabajo semanales para evitar que influyan de manera desproporcionada en los análisis posteriores.

- ### Modelado:
Se utiliza un modelo de OPROBIT para examinar la relación entre la satisfacción laboral y variables explicativas como ingresos, educación, edad, horas de trabajo y estado civil. El modelo probit ordenado es una técnica estadística utilizada para analizar datos con una variable dependiente ordinal, es decir, una variable que toma valores en categorías ordenadas (por ejemplo, bajo, medio, alto). La ecuación del modelo es:

y*_i = β_0 + β_1x_i1 + β_2x_i2 + ... + β_kx_ik + ε_i

donde y*_i es una variable latente continua subyacente, x_ij son las variables independientes, β_j son los coeficientes a estimar y ε_i es el término de error. La variable dependiente observada y_i se relaciona con la variable latente y*_i mediante umbrales desconocidos:

y_i = 1 si y*_i ≤ α_1, 2 si α_1 < y*_i ≤ α_2, ..., J si α_{J-1} < y*_i

donde J es el número de categorías ordenadas y α_j son los umbrales a estimar. El modelo probit ordenado utiliza la función de distribución acumulada normal para estimar la probabilidad de que una observación pertenezca a cada categoría. La implementación típica del modelo implica el uso de paquetes o bibliotecas estadísticas (como MASS o ordinal en R, o statsmodels o mord en Python) que proporcionan funciones para ajustar el modelo y evaluar su ajuste mediante métricas como pseudo R-cuadrados y pruebas de razón de verosimilitud. Las predicciones se pueden generar utilizando el modelo ajustado, y es importante considerar las limitaciones y supuestos del modelo, así como posibles extensiones o modelos alternativos. Se elegio este modelo porque en este caso porque la variable dependiente (satisfacción laboral) es una variable categórica ordenada. Es decir, las categorías de satisfacción laboral tienen un orden natural. El modelo probit ordenado permite modelar adecuadamente este tipo de variables dependientes ordinales, a diferencia de los modelos lineales que asumen una variable dependiente continua. Debido a la exploración de datoss determinamos que este modelo seria el que mejor se adaptaria al formato de los datos. 

### Hallazgos principales

- Los ingresos laborales, el nivel educativo y las horas de trabajo semanales tienen un impacto positivo en la satisfacción laboral.
  
- La edad tiene un efecto negativo en la satisfacción laboral, pero este efecto disminuye a medida que aumenta la edad (relación cuadrática).

- Estar casado o divorciado tiene un impacto significativo en la satisfacción laboral en comparación con ser soltero.

- Las personas con contratos permanentes tienden a estar más satisfechas en su trabajo en comparación con aquellas con contratos temporales.

- Se observa una distribución relativamente equilibrada entre hombres y mujeres tanto en la muestra completa como en el subconjunto de personas con trabajo formal.
  
- En la muestra completa, la mayoría de las personas están casadas o solteras, mientras que en el subconjunto de trabajo formal, la mayoría están casadas.
  
- En la muestra completa, la categoría más común es "empleado privado", seguida de "cuenta propia". En el subconjunto de trabajo formal, la categoría predominante es "empleado privado".
  
- En la muestra completa, la mayoría de las personas tienen contratos temporales o permanentes. En el subconjunto de trabajo formal, la mayoría tiene contratos permanentes.
  
- Tanto en la muestra completa como en el subconjunto de trabajo formal, la mayoría de las personas se encuentran "contentas" en su trabajo.
  
- Se observa una relación positiva entre la edad y los ingresos laborales, aunque con una gran dispersión.
  
- Existe una relación positiva entre los años de educación y los ingresos laborales.
  
- Se aprecia una relación positiva entre las horas de trabajo semanales y los ingresos laborales.
  
- En general, a mayor nivel de instrucción, mayor satisfacción laboral.

- Relación entre tipo de contrato y satisfacción laboral: Las personas con contratos permanentes tienden a estar más satisfechas en comparación con aquellas con contratos temporales.

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
