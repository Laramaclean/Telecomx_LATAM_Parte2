# 📊 Telecom X - Parte 2: Predicción de Cancelación de Clientes

Este proyecto tiene como objetivo **analizar y predecir la cancelación de clientes (churn)** en una empresa de telecomunicaciones, utilizando un conjunto de variables relevantes y aplicando distintos modelos de Machine Learning.  



## 🎯 Objetivo del análisis
- Identificar los **principales factores que influyen en la cancelación** de clientes.  
- Construir y comparar **modelos predictivos** para estimar la probabilidad de churn.  
- Proponer **estrategias de retención** basadas en los resultados obtenidos.


## 📂 Estructura del proyecto

El proyecto contiene los siguientes archivos principales:

TelecomX_LATAM_2

│── TelecomX_LATAM_2.ipynb 

│── telecomX_limpio.csv 

│── README.md 

- 📒 **TelecomX_LATAM_2.ipynb** → cuaderno Jupyter donde se realiza todo el flujo de trabajo: preparación de datos, análisis exploratorio, modelado y conclusiones.  
- 📂 **telecomX_limpio.csv** → archivo con los datos tratados, que se carga directamente en el notebook para análisis y entrenamiento de modelos.  
- 📄 **README.md** → archivo de documentación que explica el propósito del proyecto, la metodología y cómo ejecutarlo.



## 🛠️ Proceso de preparación de datos

1. **Clasificación de variables**  
   - *Categóricas*: tipo de contrato, método de pago, tipo de internet, servicios adicionales, etc.  
   - *Numéricas*: cargos mensuales, cargos totales, antigüedad del cliente, etc.  

2. **Transformaciones aplicadas**  
   - **Codificación One-Hot** para variables categóricas (ej. tipo de contrato, servicio de internet).  
   - **Normalización** de variables numéricas para modelos sensibles a la escala (ej. KNN, SVM, Regresión Logística).  

3. **División del dataset**  
   - Conjunto de **entrenamiento (70%)**.  
   - Conjunto de **prueba (30%)**.  

4. **Justificación de decisiones**  
   - La normalización se aplicó únicamente donde los algoritmos lo requerían.  
   - Se mantuvieron distintas versiones del dataset para comparar modelos con/sin normalización.  
   - El balance de clases fue monitoreado para evitar sesgos en los modelos.  



## 🔎 Análisis exploratorio de datos (EDA)

Durante el EDA se realizaron gráficos y cálculos clave para comprender el comportamiento del churn:

- **Distribución de cancelación por tipo de contrato**: los contratos mes a mes presentan mayor churn.  
- **Relación entre cargos mensuales y cancelación**: a mayor gasto mensual, mayor probabilidad de cancelación.  
- **Impacto de la antigüedad (tenure)**: clientes nuevos presentan tasas más altas de churn.  
- **Servicios adicionales** (ej. *OnlineSecurity*) reducen el riesgo de cancelación.  



## 🤖 Modelos utilizados

Se probaron y compararon distintos modelos:

🔸 Regresión Logística (normalizada) → mejor desempeño, interpretabilidad alta.

🔸 SVM (RBF) → accuracy competitivo, buena captura de relaciones no lineales.

🔸 Random Forest → balance entre performance e interpretabilidad de importancia de variables.

🔸 KNN → menor desempeño, útil como baseline.



## 📌 Principales hallazgos

Variables más influyentes en la cancelación:

🔹 Antigüedad del cliente (tenure).

🔹 Tipo de contrato (mes a mes vs. anual).

🔹 Tipo de internet (fibra óptica con mayor churn).

🔹 Cargos mensuales altos.

🔹 Método de pago (electronic check con más riesgo).

🔹 Servicios adicionales de seguridad reducen la cancelación.



## 🚀 Instrucciones de uso

**1) Clonar repositorio**

git clone https://github.com/usuario/TelecomX_LATAM_2.git
cd TelecomX_LATAM_2


**2) Instalar dependencias**

⚡ Recomendable usar un entorno virtual. Instalar las librerías necesarias con:

! pip install -r requirements.txt


**🔑 Librerías principales:**

⭐ pandas

⭐ numpy

⭐ scikit-learn

⭐ matplotlib

⭐ seaborn


**3) Ejecutar el cuaderno**

Abrir Jupyter Notebook o Google Colab y cargar:

TelecomX_LATAM_2.ipynb


Los datos preprocesados se encuentran en clientes_tratados.csv.



## 📈 Próximos pasos

Implementar técnicas de balanceo de clases (SMOTE, undersampling).

Probar modelos avanzados como XGBoost o LightGBM.

Desplegar un score de churn en producción para campañas de retención.



## 👩‍💻 Autoría

Proyecto desarrollado como parte del análisis de datos de clientes de Telecom X (LATAM).
