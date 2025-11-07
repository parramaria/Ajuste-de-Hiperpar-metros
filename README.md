# Ajuste de Hiperparametros
Trabajo N°4
## Autora: Maria Paula Sánchez Parra


#  **Ajuste y Optimización de Hiperparámetros en Modelos de Aprendizaje Automático**

Este proyecto tiene como objetivo **aplicar técnicas avanzadas de ajuste y optimización de hiperparámetros** en modelos de aprendizaje automático, con el propósito de **mejorar la capacidad predictiva y la eficiencia del modelado estadístico**.  
Para el análisis, se utilizó un conjunto de datos global sobre **esperanza de vida**, que integra variables **socioeconómicas, sanitarias y demográficas**.  
El enfoque se centra en comparar el desempeño de diferentes métodos de optimización —**búsqueda aleatoria (Randomized Search)** y **optimización bayesiana (Optuna)**— y evaluar su impacto sobre modelos de regresión en términos de precisión, estabilidad y capacidad explicativa.


##  **Conjunto de Datos**

El dataset contiene información **por país y año**, e incorpora variables asociadas con:

- **Condiciones sanitarias:** tasas de inmunización, mortalidad infantil, prevalencia de enfermedades transmisibles.  
- **Indicadores económicos:** PIB per cápita, gasto público y privado en salud.  
- **Factores sociales:** nivel de escolaridad promedio, consumo de alcohol, densidad poblacional.  
- **Medidas de salud pública:** acceso a vacunas, cobertura sanitaria, gasto gubernamental en bienestar.

Este conjunto multidimensional ofrece un marco adecuado para **analizar la interacción entre desarrollo económico y resultados en salud**, y cómo los modelos predictivos pueden capturar dichas relaciones complejas.


##  **Metodología**

### **1. Limpieza y Preprocesamiento**
- Imputación de valores faltantes mediante técnicas estadísticas.  
- Codificación de variables categóricas mediante *One-Hot Encoding*.  
- Escalamiento de variables numéricas para homogeneizar magnitudes.  

### **2. División del Conjunto de Datos**
- División **entrenamiento/prueba (80/20)**, garantizando representatividad temporal y geográfica.  

### **3. Modelos Evaluados**
- **Ridge Regression** (*modelo base lineal*).  
- **Random Forest** con búsqueda aleatoria de hiperparámetros mediante `RandomizedSearchCV`.  
- **Random Forest** con **optimización bayesiana** implementada en **Optuna**.

### **4. Métrica de Evaluación**
- **RMSE (Raíz del Error Cuadrático Medio):** mide la desviación promedio entre los valores predichos y observados, siendo una referencia directa de precisión predictiva.


##  **Resultados Comparativos**

| **Modelo**                              | **RMSE** |
|-----------------------------------------|-----------|
| **Ridge Regression (baseline)**         | 3.9952    |
| **Random Forest + Randomized SearchCV** | 1.7132    |
| **Random Forest + Optuna**              | **1.6886** |

Los resultados muestran una **mejoría sustancial en la precisión** al pasar de modelos lineales a no lineales. La **optimización bayesiana** superó a la búsqueda aleatoria al explorar el espacio de hiperparámetros de forma más eficiente y con menor costo computacional.


##  **Análisis Económico y Econométrico**

Desde una perspectiva econométrica, los resultados evidencian que los determinantes estructurales de la **esperanza de vida** responden a una **relación no lineal multivariable**, donde las interacciones entre variables económicas y sanitarias no pueden ser adecuadamente captadas por modelos lineales tradicionales.

Entre las variables con mayor impacto predictivo destacan:
- **Escolaridad promedio**, como indicador del capital humano y su efecto sobre la salud poblacional.  
- **Inmunización (Hepatitis B y Polio)**, reflejo de la inversión pública en prevención.  
- **PIB per cápita y gasto total en salud**, que evidencian la capacidad económica de los Estados para sostener sistemas sanitarios eficientes.

Estos resultados confirman la relevancia de considerar **efectos no lineales y heterogeneidad estructural** en el análisis econométrico aplicado a la salud pública.

##  **Conclusiones Finales**

- El modelo base **Ridge Regression** presentó un error de predicción relativamente alto, al no capturar las interacciones no lineales entre variables económicas y sanitarias.  
- La introducción del **Random Forest** redujo el RMSE en más de un 50%, demostrando la capacidad de los modelos no paramétricos para **captar relaciones complejas y efectos marginales heterogéneos**.  
- La **optimización bayesiana mediante Optuna** logró el mejor desempeño general, validando su eficiencia en la exploración del espacio de hiperparámetros y su utilidad para obtener configuraciones más robustas y precisas.  
- El análisis reafirma la importancia de la **optimización de hiperparámetros como componente esencial del modelado econométrico moderno**, permitiendo alcanzar un equilibrio óptimo entre complejidad, interpretabilidad y desempeño predictivo.

### **Reflexión Final**

Este estudio demuestra que la aplicación de **técnicas avanzadas de aprendizaje automático y optimización estadística** constituye un instrumento poderoso en el campo de la **econometría aplicada y la política pública**.  
La combinación de modelos no lineales con metodologías de ajuste inteligente, como la optimización bayesiana, permite **elevar el rigor predictivo y analítico** de los estudios empíricos, fortaleciendo la capacidad de los economistas para **formular políticas basadas en evidencia cuantitativa y modelación científica del comportamiento social y económico**.
