#  Red Wine Quality — Exploratory Data Analysis

A beginner-friendly EDA project on the [UCI Red Wine Quality dataset](https://archive.ics.uci.edu/ml/datasets/wine+quality), exploring the physicochemical properties of Portuguese *Vinho Verde* red wine and their relationship to quality scores.

---

##  Dataset

| Property | Detail |
|---|---|
| File | `winequality-red.csv` |
| Separator | Semicolon (`;`) |
| Records | 1,599 wine samples |
| Features | 11 physicochemical inputs + 1 quality score |

**Input features:** fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol

**Target:** `quality` — integer score between 0 and 10 (rated by wine experts)

---

##  Notebook Overview

`Red_wine.ipynb` walks through a complete EDA pipeline:

### 1. Data Loading & Basic Inspection
- Load CSV with `pandas`
- Preview rows with `.head()`
- Check shape, dtypes, and index with `.info()`, `.shape`, `.describe()`, `.columns`

### 2. Data Quality Checks
- Null value detection — `df.isnull().sum()`
- Duplicate row detection — `df.duplicated().sum()`
- Drop any unwanted columns

### 3. Statistical Analysis
- Correlation matrix — `df.corr()`
- Distribution of the target variable (`quality`) using `.value_counts()`

### 4. Visualizations
- **Heatmap** — correlation between all features (`seaborn`)
- **Bar chart** — distribution of wine quality scores
- **Histograms with KDE** — distribution of every feature
- **Pairplot** — pairwise relationships across all features
- **Scatter plot** — `alcohol` vs `pH` coloured by `quality`

---

##  Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading and manipulation |
| `matplotlib` | Base plotting |
| `seaborn` | Statistical visualizations |

---

##  Getting Started

### Prerequisites
```bash
pip install pandas matplotlib seaborn
```

### Run the notebook
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```
2. Place the dataset file `winequality-red.csv` in the project root.
3. Launch Jupyter:
   ```bash
   jupyter notebook Red_wine.ipynb
   ```

> **Note:** The dataset uses semicolons (`;`) as delimiters, not commas. Make sure to use `sep=";"` when reading with `pd.read_csv()`.

---

##  Key Insights

- Most wines in the dataset score between **5 and 6** on the quality scale — the distribution is roughly normal and slightly right-skewed.
- **Alcohol** and **sulphates** show a positive correlation with quality.
- **Volatile acidity** is negatively correlated with quality.
- **Density** and **fixed acidity** are highly correlated with each other.

---

##  Project Structure

```
├── Red_wine.ipynb          # Main EDA notebook
├── winequality-red.csv     # Dataset (add manually)
└── README.md
```

---

##  License

This project is for educational purposes. The Wine Quality dataset is publicly available from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/wine+quality).

> P. Cortez, A. Cerdeira, F. Almeida, T. Matos, and J. Reis. *Modeling wine preferences by data mining from physicochemical properties.* Decision Support Systems, 47(4):547–553, 2009.
