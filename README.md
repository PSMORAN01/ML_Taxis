# Predicción de pedidos de taxi por hora 🚕📈

Este proyecto tiene como objetivo predecir cuántos pedidos de taxi se realizarán por hora, utilizando datos históricos de demanda y modelos de aprendizaje supervisado. Se usaron transformaciones de series temporales, variables de fecha y modelos basados en árboles.

---

## 📊 Descripción general

El dataset original `taxi.csv` contiene un registro de pedidos de taxi con marcas de tiempo (`datetime`) y cantidad de pedidos (`num_orders`). Se realizó un remuestreo horario para estructurar los datos como una serie temporal.

El objetivo final fue entrenar un modelo que prediga la cantidad de pedidos para una hora futura, ayudando a optimizar disponibilidad de taxis y recursos logísticos.

---

## ⚙️ Tecnologías utilizadas

- Python 3
- Pandas
- NumPy
- Scikit-learn
- Matplotlib, Seaborn
- CatBoost
- RandomForestRegressor

---

## 🔁 Preprocesamiento y Feature Engineering

1. Conversión de la columna `datetime` a tipo fecha y remuestreo por hora (`resample('1H')`)
2. Visualización de la serie temporal con tendencias y estacionalidad
3. Creación de variables de fecha:
   - Hora del día
   - Día de la semana
   - Día del año
   - Mes
   - Indicador de fin de semana
4. Generación de *lag features*:
   - Valor de la hora anterior (`lag_1`)
   - Valor de hace 24 horas (`lag_24`)

---

## 🤖 Modelos utilizados

### 🌳 Random Forest Regressor
- Entrenamiento sobre datos con características de fecha y *lags*
- Evaluado con RMSE

### 🐈 CatBoost Regressor
- Modelo robusto para trabajar con poca necesidad de normalización
- Mejores resultados en validación, especialmente en predicciones para fines de semana y días con alta varianza

---

## 📈 Resultados

- La serie temporal mostró una clara estacionalidad diaria y semanal.
- La media móvil de 24 horas ayudó a visualizar mejor los patrones de la demanda.
- El modelo final logró un buen RMSE, permitiendo predecir pedidos de taxi con precisión razonable por hora.

---

## 🧠 Lecciones aprendidas

- Las transformaciones temporales son clave en problemas de series temporales.
- Incorporar variables como hora, día o si es fin de semana mejora bastante la predicción.
- Los *lag features* aportan contexto inmediato del comportamiento reciente, y son cruciales en modelos supervisados para datos secuenciales.
- CatBoost funciona muy bien en tareas de regresión con estructuras tabulares.

---

## 👨‍💻 Autor

**Pablo Sebastián Morán**  
📧 psmoran01@gmail.com  
🔗 [GitHub](https://github.com/PSMORAN01)  
