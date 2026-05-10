# Data Science

Repositorio de trabajos y ejercicios de ciencia de datos, con un proyecto principal centrado en el analisis de factores que influyen en la decision de compra de vivienda a nivel internacional.

## Proyecto principal

**Analisis de los factores que influyen en la decision de compra de vivienda a nivel internacional**  
Autores: Ander Castro y Lucas Martinez

El estudio utiliza el dataset **Global House Purchase Decision Dataset**, obtenido de Kaggle, con 200.000 observaciones y 25 variables sobre propiedades, compradores, financiacion, entorno y decision final de compra.

El objetivo es entender que factores explican el precio de una vivienda y que variables influyen en la aprobacion o rechazo de una compra/hipoteca. El trabajo combina analisis exploratorio, estadistica inferencial, reduccion de dimensionalidad y modelos predictivos.

## Preguntas de analisis

- Que variables explican mejor el precio de una vivienda.
- Como influyen pais, tipo de propiedad, tamano, salario, pago inicial y nivel de criminalidad.
- Que factores determinan la variable objetivo `decision`.
- Si existen diferencias significativas entre paises o ciudades.
- Si el conjunto de variables puede resumirse mediante componentes principales.
- Que patrones aparecen en el perfil financiero y subjetivo del comprador.

## Metodologia

El proyecto sigue este flujo de trabajo:

1. Importacion y revision del dataset.
2. Resumen estadistico y analisis exploratorio.
3. Visualizacion de distribuciones y relaciones bivariantes.
4. Contrastes de hipotesis e inferencia estadistica.
5. PCA para reduccion de dimensionalidad.
6. Modelos de machine learning para predecir `decision`.
7. Interpretacion de resultados, conclusiones y limitaciones.

## Tecnicas utilizadas

- Analisis exploratorio de datos con `dplyr`, `tidyr` y `ggplot2`.
- Visualizacion de correlaciones con `corrplot`.
- Contrastes estadisticos: Shapiro-Wilk, Levene, ANOVA, Tukey, Wilcoxon y Chi-cuadrado.
- PCA para identificar componentes principales.
- Regresion logistica con regularizacion Lasso y validacion cruzada.
- XGBoost con validacion cruzada y busqueda de hiperparametros.
- Evaluacion mediante matriz de confusion, curva ROC y AUC.

## Resultados destacados

- La variable `decision` esta desbalanceada: la mayoria de observaciones corresponden a no compra.
- El precio presenta una distribucion asimetrica a la derecha, por lo que se utiliza `log_price` para mejorar el analisis.
- El pais tiene un efecto significativo en el precio de la vivienda.
- La presencia de jardin no muestra diferencias significativas en el precio dentro del dataset.
- El tipo de propiedad y la disponibilidad de garaje presentan asociacion estadistica.
- La decision de compra esta influida principalmente por precio, pais y nivel de satisfaccion.
- El modelo XGBoost alcanza un AUC aproximado de 0.95 en el conjunto de test.
- Las variables de satisfaccion y ratio EMI/ingresos destacan como factores relevantes para explicar el comportamiento de compra.

## Estructura del repositorio

```text
.
|-- group_12.Rmd                         # Informe principal en R Markdown
|-- group_12.html                        # Informe renderizado
|-- global_house_purchase_dataset.csv    # Dataset de compra de vivienda
|-- model_lasso_cv.rds                   # Modelo Lasso entrenado
|-- xgb_model_final.rds                  # Modelo XGBoost entrenado
|-- portada.png                          # Imagen de portada del informe
|-- Preguntas y Metodologia.docx         # Documento de planteamiento del trabajo
|-- Data-Science.Rproj                   # Proyecto de RStudio
`-- Ejemplo/
    |-- TRABAJO FINAL NBA.ipynb          # Notebook complementario
    |-- TRABAJO FINAL NBA.html           # Version renderizada del notebook
    `-- nba_2017_nba_players_with_salary.csv
```

## Requisitos

El proyecto principal esta desarrollado en R/RStudio. Los paquetes usados incluyen:

- `dplyr`
- `ggplot2`
- `tidyr`
- `corrplot`
- `scales`
- `broom`
- `car`
- `caret`
- `xgboost`
- `glmnet`
- `pROC`
- `cleanrmd`

Para instalar los paquetes principales:

```r
install.packages(c(
  "dplyr", "ggplot2", "tidyr", "corrplot", "scales", "broom",
  "car", "caret", "xgboost", "glmnet", "pROC", "cleanrmd"
))
```

## Como reproducir el analisis

1. Clona el repositorio:

```bash
git clone https://github.com/lucasmartinez16/Data-Science.git
cd Data-Science
```

2. Abre `Data-Science.Rproj` en RStudio.
3. Instala los paquetes necesarios si no estan disponibles.
4. Ejecuta o renderiza `group_12.Rmd`.

El repositorio ya incluye modelos entrenados en formato `.rds`, por lo que algunas secciones del informe cargan esos objetos directamente para evitar reentrenamientos largos.

## Nota sobre los datos

El dataset usado es amplio y de origen sintetico. Por tanto, los resultados deben interpretarse como un ejercicio academico de analisis, modelado e interpretacion, no como conclusiones directamente generalizables al mercado inmobiliario real.

## Ejemplo complementario

La carpeta `Ejemplo/` contiene un notebook sobre datos de jugadores de la NBA 2017 y salarios. Sirve como material adicional de practica en analisis exploratorio y presentacion de resultados con notebooks.
