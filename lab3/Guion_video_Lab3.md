# Guion del video - Laboratorio 3 (Ruta Alpes)

Duración objetivo: menos de 3 minutos (unas 406 palabras narradas, entre 2:45 y 2:55 a ritmo normal). Cada bloque indica quién habla y qué mostrar en pantalla. Si se pasan del tiempo, lo primero que se puede recortar es el bloque 3.

**1. El problema (0:00 - 0:20)** · Juan Felipe
*En pantalla: título del notebook y gráfico de distribución de `acepta_cupon`.*

"Hola, somos Juan Felipe Sáenz y Tomás Aguilera. Ruta Alpes quiere predecir cuándo un conductor va a aceptar un cupón de Cafetería o de Restaurante de menos de 20 dólares, para no mandarle la misma oferta a todos. Lo planteamos como dos problemas de clasificación binaria, con un modelo por cupón."

**2. Datos y preparación (0:20 - 0:55)** · Tomás
*En pantalla: tabla de calidad por dimensión y tabla de decisiones de limpieza.*

"Cafetería tiene unos 4000 escenarios y está balanceado. Restaurante tiene 2800 y el 71% acepta, así que la clase minoritaria es el rechazo. En calidad encontramos vehículo con 99% de faltantes, una columna constante, duplicados y variables redundantes, como misma dirección y dirección opuesta, que son exactamente contrarias. Las transformaciones fila a fila van antes del split, y la imputación, la codificación ordinal y one-hot y el escalado van dentro del pipeline, para no tener fuga de información en la validación cruzada."

**3. Métrica y modelos (0:55 - 1:35)** · Juan Felipe
*En pantalla: celda de la línea base "siempre Sí" y curvas de complejidad del árbol y del Random Forest.*

"La métrica fue clave. En Restaurante, decir Sí a todo ya da un F1 de 0.83, entonces escogimos hiperparámetros con F1 macro y validación cruzada estratificada de 5 folds. En la logística exploramos L1, L2 y elastic net con distintos solvers y valores de C. En el árbol, profundidad, mínimo de muestras por hoja y criterio, y ahí se ve el trade-off sesgo varianza: en Cafetería el mejor punto es profundidad 5. El Random Forest casi memoriza el entrenamiento, pero al promediar árboles distintos baja la varianza y es el que mejor generaliza."

**4. Resultados y SMOTE (1:35 - 2:15)** · Tomás
*En pantalla: tabla comparativa en test, tabla de SMOTE y matrices de confusión.*

"En test, Random Forest gana en los dos cupones. En Cafetería tiene F1 de 0.78 y se equivoca parecido en las dos clases. En Restaurante el problema es el rechazo: solo detecta el 40%. Probamos SMOTE dentro de un pipeline de imblearn, para que solo actúe sobre los folds de entrenamiento. Con Random Forest sube el recall del rechazo a 43% y el F1 macro queda en 0.687, el mejor, a cambio de perder algo de recall en el Sí. Lo recomendamos porque para Ruta Alpes un cupón irrelevante molesta al conductor. Con el árbol, en cambio, SMOTE empeoró el modelo."

**5. Variables relevantes (2:15 - 2:35)** · Juan Felipe
*En pantalla: importancia por permutación y coeficientes de la regresión logística.*

"Con importancia por permutación vimos que en Cafetería domina el hábito: quien nunca va a cafeterías acepta solo el 19% de las veces. En Restaurante pesa más el contexto: la vigencia del cupón, el destino y la hora."

**6. Riesgos y cierre (2:35 - 3:00)** · Tomás
*En pantalla: tabla de desempeño por grupo de edad.*

"Pero el error no se reparte igual: en Restaurante el recall del rechazo va de 0.20 a 0.56 según la edad. Recomendamos priorizar variables de contexto, auditar el modelo por grupo demográfico y no usar este perfilamiento para precios dinámicos. Gracias."
