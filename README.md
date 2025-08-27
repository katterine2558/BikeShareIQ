# 🚴‍♀️ CycleCast — Bike-Share Demand Forecasting (EDA → PolyReg → Lasso)

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-orange)
![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-9cf)
![License](https://img.shields.io/badge/License-MIT-green)

> Predicción **interpretable** de la demanda de bicicletas compartidas a partir de clima, calendario y hora del día. Pipeline completo: **EDA → limpieza → modelado (Regresión Polinómica grado 3 & Lasso) → evaluación → interpretabilidad**.

---

## ✨ TL;DR
- Dos enfoques de regresión (Polinómica g3 y Lasso) para estimar la variable objetivo `cnt` (demanda).  
- Incluye reporte de EDA, división reproducible train/test, métricas (RMSE/MAE/R²) y análisis de coeficientes para explicar los factores que más pesan en la predicción.

---

## 🧠 ¿Qué hay aquí?
- **EDA**: perfilamiento con reporte HTML; duplicados, correlaciones (`temp`↔`atemp`), valores atípicos en `hum` y chequeo de categorías (`weekday`, `weathersit`).  
- **Preprocesamiento**: eliminación de duplicados, dummies para categóricas, features de **franja horaria** (`time_of_day`), etc.
- **Modelos**: 
  - **Regresión Polinómica (grado 3)** como baseline no lineal.
  - **Lasso** para regularizar y **seleccionar variables** (coeficientes exactos en cero).
- **Evaluación**: RMSE / MAE / R² (tabla comparativa).
- **Interpretabilidad (Lasso)**: importancia de `temp`/`atemp`, efecto negativo de `hum`, categorías útiles en `weathersit`, y propuesta de simplificar `weekday` a **fin de semana vs. día hábil**.

---

## 📂 Estructura sugerida

```text
cyclecast/
├─ data/                     # dataset (no incluido)
├─ notebooks/
│  └─ PML-Proyecto-PT1_V2.ipynb
├─ reports/
│  └─ PML-Proyecto-PT1_V2.html
├─ src/
│  ├─ features.py
│  ├─ train_lasso.py
│  └─ train_poly.py
├─ requirements.txt
└─ README.md
````
## ⚙️ Reproducir

> Requisitos: **Python 3.10+** y `git`. El dataset no está incluido.

1) **Clona el repo**
```bash
git clone https://github.com/<tu-usuario>/<tu-repo>.git
cd <tu-repo>
```
2) **Crea y activa un entorno virtual**
```bash
python -m venv .venv
source .venv/bin/activate
```
3) **Instala dependencias**
```bash
pip install -r requirements.txt
# Si no tienes requirements.txt, usa:
# pip install pandas scikit-learn matplotlib seaborn ydata-profiling
```
4) **Ubica el dataset**
``` bash
Coloca tu CSV en data/ (por ejemplo: data/bike_sharing.csv).
```
5) **Ejecuta el notebook**

```bash
python -m notebook
```
