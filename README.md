# Proyecto de Minería de Datos — *Iris*

> **Repositorio:** `Proyecto-mineria-de-datos`

> **URL:** [https://github.com/Marlon271/Proyecto-mineria-de-datos.git](https://github.com/Marlon271/Proyecto-mineria-de-datos.git) 
> **Autores:** Marlon David Romero Trujillo · Jose Leonardo Vargas Herrera

---

## 🎯 Objetivo del proyecto

**Pregunta de investigación:** ¿Es posible **predecir la especie de *Iris*** (*Setosa*, *Versicolor*, *Virginica*) usando las variables numéricas `sepal_length`, `sepal_width`, `petal_length` y `petal_width`?

* **Tipo de tarea:** Clasificación multiclase
* **Variable objetivo:** `species` (codificada en el pipeline)
* **Métricas foco:** F1-macro y accuracy (con matriz de confusión y *classification report*)
* **Validación:** *Hold-out* 80/20 y validación cruzada estratificada (5-fold)
* **Control de fuga:** División de datos **antes** del ajuste y del escalado


---

## 🗂️ Archivos del repositorio (clave)

* `notebooks/1.ipynb` → Notebook principal (versión Colab/Jupyter) con todo el flujo EDA → ML.
* `docs/presentacion/Iris mineria de datos.pptx` → Presentación con imágenes, hallazgos y la pregunta de investigación.
* `data/iris.data` → Dataset original desde UCI ML Repository.
* `data/external/FO-IV-159_COMPLETADO_v2.xlsx` → **Excel de apoyo** usado en el proceso (registro/evidencias/insumos auxiliares).
* `docs/conclusiones/Conclusión del Proyecto de Análisis y Clasificación de Especies de Iris.docx` → **Documento de conclusiones** (lo subirá el autor; ver sección "Entregables").
* `requirements.txt` → Dependencias mínimas para reproducibilidad.


---

## 📊 Datos

* **Fuente (UCI ML Repository)**
  **Dataset:** [https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data](https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data)
  **Documentación:** [https://archive.ics.uci.edu/dataset/53/iris](https://archive.ics.uci.edu/dataset/53/iris)
* **Estructura esperada:** 150 filas × 5 columnas
  **Numéricas:** `sepal_length`, `sepal_width`, `petal_length`, `petal_width`
  **Categórica objetivo:** `species` (tres clases)
* **Convenciones de nombres:** los derivados (normalizados, *splits*, figuras) se guardan en `data/processed/` y `reports/figures/` generados desde el notebook.

---

## 🧪 Metodología (alineada a 11 pasos EDA)

Resumen del flujo implementado en `notebooks/1.ipynb`:

1. **Importar datos** y asignar nombres de columnas.
2. **Revisión de calidad:** tipos, dimensiones, valores faltantes (mapa/tabla) y duplicados.
3. **Limpieza:** criterios explícitos para NaN (si aplica), duplicados y estandarización de categorías.
4. **EDA:** histogramas por variable, boxplots para *outliers*, *scatter* bivariados por especie, matriz de correlación (Spearman).
5. **Conversión/encoding:** `species` → etiquetas numéricas para modelado.
6. **Normalización:** **Min–Max** en predictores numéricos.
7. **Partición** estratificada *train/test*.
8. **Modelado:** *baseline* (Dummy), **Logistic Regression** y **Random Forest** en **pipeline** con escalado.
9. **Evaluación:** F1-macro/accuracy, matriz de confusión, análisis de errores (frontera natural: Versicolor vs Virginica).
10. **Figuras/tablas:** exportadas a `reports/figures/`.
11. **Conclusiones y recomendaciones:** ver `docs/conclusiones/`.


---

## ▶️ Reproducibilidad

### 1) Clonar y preparar entorno

```bash
git clone https://github.com/Marlon271/Proyecto-mineria-de-datos.git
cd Proyecto-mineria-de-datos
pip install -r requirements.txt
```

**`requirements.txt` sugerido:**

```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
scipy
```

### 2) Datos

Por defecto se usa `data/iris.data`. Si no existe, puede descargarse y convertir a CSV desde el notebook.
El **Excel de apoyo** debe ubicarse en: `data/external/FO-IV-159_COMPLETADO_v2.xlsx`.

### 3) Ejecutar

Abra y ejecute **en orden** `notebooks/1.ipynb`.
Las figuras y tablas se guardarán automáticamente (si el notebook lo implementa) en `reports/figures/`.

---

## 📈 Resultados esperados

* Clasificación multiclase con desempeño alto en F1-macro (referencia típica del dataset Iris).
* Matriz de confusión y reporte por clase.
* Análisis breve luego de **cada** gráfica (qué muestra, patrón y su implicación).

> Importante: el dataset **Iris** no suele tener valores faltantes; aun así se documenta la verificación. La normalización **Min–Max** se usa para homogeneizar escalas de predictores.

---

## 🧾 Entregables

* **Presentación**: `docs/presentacion/Iris mineria de datos.pptx` (8 diapositivas con pregunta, EDA y resultados).
* **Notebook**: `notebooks/1.ipynb` (código comentado, 11 pasos EDA y modelado).
* **Excel de apoyo**: `data/external/FO-IV-159_COMPLETADO_v2.xlsx` (insumo adicional del proceso).
* **Conclusiones**: coloque su **Word** en `docs/conclusiones/Conclusión del Proyecto de Análisis y Clasificación de Especies de Iris.docx`.
* **Figuras**: `reports/figures/` (exportadas desde el notebook).

---

## 📚 Referencias

* **Dataset (UCI):** [https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data](https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data)
* **Documentación (UCI):** [https://archive.ics.uci.edu/dataset/53/iris](https://archive.ics.uci.edu/dataset/53/iris)

---

Proyecto académico de Minería de Datos — Universidad CORHUILA.
