# README: Procesamiento y Análisis de Datos de Ventas de Café

## Descripción del Proyecto
Este proyecto tiene como objetivo la limpieza, análisis exploratorio y modelado predictivo de un conjunto de datos de ventas de café. Se utiliza Python y bibliotecas como `pandas`, `numpy`, `matplotlib` y `sklearn` para preprocesar y analizar los datos.

## Estructura del Pipeline
### 1. Observación Inicial de los Datos
Se cargan y exploran los datos mediante `pandas`, verificando:
- Primeras filas del DataFrame (`head()`)
- Información general (`info()`)
- Estadísticas descriptivas (`describe()`)
- Valores faltantes (`isnull().sum()`)
- Tipos de datos (`dtypes`)

### 2. Limpieza de Datos
Se identifican y corrigen valores faltantes y atípicos:
- Sustitución de valores inválidos (`ERROR`, `UNKNOWN`, `None`, etc.).
- Conversión de datos a los tipos adecuados (`to_numeric`, `to_datetime`).
- Relleno de valores nulos con la moda, mediana o media según corresponda.
- Exportación del DataFrame limpio a `clean_cafe_sales.csv`.

### 3. Análisis Exploratorio de Datos (EDA)
Se visualizan patrones de gasto según:
- Item y método de pago.
- Item y ubicación de compra.
Se usan `matplotlib` y traducciones para mejorar la interpretación.

### 4. Pipeline de Preprocesamiento
Se define un `Pipeline` de `sklearn` para normalizar los datos:
- Variables numéricas:
  - Imputación con la mediana.
  - Escalado con `StandardScaler`.
- Variables categóricas:
  - Imputación con la moda.
  - Codificación `OneHotEncoder`.

### 5. Modelado Predictivo
Se entrena un modelo `RandomForestClassifier` para predecir `Total Spent`:
- Se eliminan filas con valores faltantes en la variable objetivo.
- Se define `X` (variables predictoras) e `y` (variable objetivo).
- Se ajusta el modelo con `RandomForestClassifier(n_estimators=100, random_state=42)`.

## Requisitos de Instalación
Ejecutar en el terminal:
```sh
pip install pandas numpy matplotlib scikit-learn
```

## Uso
Ejecutar el script en un entorno de Python para procesar y analizar los datos:
```sh
python script.py
```
