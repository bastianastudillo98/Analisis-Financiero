# Analísis Financiero en R

### ![AMAZON](https://github.com/bastianastudillo98/Analisis-Financiero/blob/main/Amazon%20Financial%20Analysis/AMZN.pdf) 
Se realiza un analisis y predicción al mercado de AMAZON desde el año 2020 hasta 2021. Lo que se encontrara dentro de este contenido con sus respectivos analísis es:
* Amazon Historico y Grafico Entrenamiento y Test separados por colores
* Modelos de Predicción 
  1. ARIMA(7,1,3)
  2. ARIMA(1,0,0) 
* Modelo Suavizamiento Exponencial 
  1. Simple,
  2. tendencia lineal con Holt
  3. Holt con correción a la deriva (Sin estacionalidad)
  4. ETS  
* Modelo Red Neuronal tipo Feed Forward Neural
  1. NNAR(12,6)
  2. NNAR(7,4)
  
Y para escoger el mejor modelo para el mercado de Amazon se realizo de la siguiente manera:
####  Medidas de no linealidad y entropía calculadas a partir de los datos de entrenamiento (entrenamiento) utilizados en el análisis.
La medida de no linealidad es 0.0835. Esta medida indica el nivel de no linealidad presente en losdatos.  Valores cercanos a cero indican una tendencia más lineal, mientras que valores más altosindican más no linealidad en los datos. En este caso, el valor 0,0835 indica cierta no linealidad en losdatos de entrenamiento, pero no es muy pronunciada

La entropía es 0.716. una distribución más ordenada y predecible, mientras que un valor más alto indicauna distribución más caótica o impredecible. En este caso, un valor de 0.716 indica que los datos deentrenamiento tienen algún grado de desorden o variación, pero no son extremadamente caóticos.

Los resultados sugieren que los datos de entrenamiento exhiben cierto grado deno linealidad y variabilidad, aunque no hay una fuerte no linealidad ni caos.
#### RMSE | MAPE Modelos 
Modelo         RMSE    MAPE

ARIMA(7,1,3)   1.86    0.01022

AR(3)          4.26    0.02388

ses            1.69    0.00912

holt           1.64    0.00860

HW             1.57    0.00789

ets            1.70    0.00914

nnetar(12,6)   7.28    0.03978

nnetar(7,4)    5.87    0.03200

#### CONCLUSIÓN DE MODELOS
Con base en los resultados de las métricas de error (RMSE y MAPE) para varios modelos,podemos concluir que:
• El modelo ARIMA(7,1,3) tiene los errores más pequeños para RMSE (1,86) y MAPE (0,01022), lo queindica que es el modelo más preciso para predecir los precios de Amazon en este caso.
• Los modelos AR(3), ses, holt, HW y ets también tienen relativamente pocos errores en comparación con otros modelos. Estos modelos tradicionales basados en métodos estadísticos clásicos también puedenconsiderarse buenas opciones para la previsión de precios
* Los modelos de redes neuronales feedforward, los modelos nnetar(12,6) y nnetar(7,4) , tienen errores másgrandes en comparación con los modelos tradicionales.  El modelo nnetar(12,6) muestra un RMSE de10,32 y un MAPE de 0,05613, mientras que el modelo nnetar(7,4) muestra un RMSE de 5,27 y un MAPE de 0,03074. Esto muestra que estos modelos de redes neuronales pueden no ser muy precisos en esta situación particular.

Recomendación: la serie de datos presenta características no lineales, el modelo ARIMA(7,1,3) puede ser una buena elección. Este modelo combina componentes de autorregresión, diferen-ciación y promedio móvil para capturar la autocorrelación, eliminar la tendencia no lineal ymodelar los errores pasados. Al seleccionar este modelo, es importante considerar las métricas de error de pronóstico, como el RMSE y el MAPE, para evaluar su ajuste y precisión enrelación con los datos observados.
