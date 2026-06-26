# 📊 Data Profiling Project

A complete data profiling and exploratory data analysis (EDA) project using the **California Housing Dataset**. This notebook covers data loading, cleaning, univariate, bivariate, and multivariate analysis with visualizations.

---

## 📁 Project Structure

```
Data_Profilers.ipynb   # Main notebook with full analysis
housing.csv            # Primary dataset (CSV format)
housing.json           # Dataset in JSON format
housing.db             # Dataset in SQLite format
README.md              # Project documentation
```

---

## 🛠️ Libraries Used

| Library | Purpose |
|--------|---------|
| `numpy` | Numerical computations |
| `pandas` | Data manipulation and analysis |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical data visualization |
| `scipy` | Statistical tests |
| `sqlite3` | SQL database connection |

---

## 📦 Data Loading

Data is loaded from three different sources:

- **CSV** — `pd.read_csv("housing.csv")`
- **JSON** — `pd.read_json("housing.json")`
- **SQL** — `pd.read_sql(query, sqlite3.connect("housing.db"))`
- **API** — `requests.get(url).json()` (via JSONPlaceholder)

---

## 🔍 Data Cleaning & Preprocessing

| Step | Method |
|------|--------|
| Preview data | `df.head()`, `df.tail()` |
| Statistical summary | `df.describe()` |
| Check missing values | `df.isnull().sum()` |
| Fill missing values | `df["total_bedrooms"].fillna(median)` |
| Check data types | `df.dtypes` |
| Convert data types | `.astype("int64")`, `.astype("category")` |
| Check duplicates | `df.duplicated().sum()` |

---

## 📘 Univariate Analysis

Analyzing a single variable — its central tendency, spread, and shape.

| Metric | Method |
|--------|--------|
| Mean | `df["population"].mean()` |
| Median | `df["population"].median()` |
| Mode | `df["population"].mode()` |
| Kurtosis | `df["median_house_value"].kurtosis()` |
| Skewness | `df["median_house_value"].skew()` |
| Variance | `df["median_income"].var()` |
| Std Dev | `df["median_income"].std()` |
| Range | `max() - min()` |
| IQR | `Q3 - Q1` (outlier detection) |
| Value Counts | `df["population"].value_counts(normalize=True)` |
| Unique Values | `df["ocean_proximity"].unique()` |

### 📊 Univariate Charts

- **Histplot** — Distribution of Median Income
- **Boxplot** — House Value Spread (Outliers)
- **Countplot** — Ocean Proximity Distribution
- **Bar Chart** — Ocean Proximity Frequency
- **Pie Chart** — Ocean Proximity Proportions

---

## 📘 Bivariate Analysis

Analyzing the relationship between two variables.

### Numerical vs Numerical
- **Scatter Plot** — Median Income vs Median House Value

### Categorical vs Numerical
- **Boxplot** — Ocean Proximity vs House Value
- **Barplot** — Average House Value by Ocean Proximity
- **Violinplot** — Distribution of House Value by Ocean Proximity

### Categorical vs Categorical
> ⚠️ **Note:** This dataset does not have two categorical columns, so a Categorical vs Categorical chart was not possible.

---

## 📘 Multivariate Analysis

Analyzing three or more variables together to reveal complex patterns.

| Chart | Variables Used |
|-------|---------------|
| Correlation Heatmap | All numerical columns |
| Pairplot | `median_income`, `median_house_value`, `housing_median_age` |
| Multivariate Scatter | Income vs House Value + `ocean_proximity` (hue) + `total_rooms` (size) |
| FacetGrid | `median_house_value` distribution per `ocean_proximity` category |

---

## 📌 Dataset Columns

| Column | Type | Description |
|--------|------|-------------|
| `longitude` | float | Geographic longitude |
| `latitude` | float | Geographic latitude |
| `housing_median_age` | int | Median age of houses |
| `total_rooms` | int | Total rooms in block |
| `total_bedrooms` | int | Total bedrooms in block |
| `population` | int | Block population |
| `households` | int | Number of households |
| `median_income` | float | Median household income |
| `median_house_value` | float | Median house value |
| `ocean_proximity` | category | Distance from ocean |

---

## ▶️ How to Run

1. Clone or download this project
2. Make sure `housing.csv` is in the same folder as the notebook
3. Install required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn scipy
   ```
4. Open and run `Data_Profilers.ipynb` in Jupyter Notebook or JupyterLab

---

## 👤 Author

**Data Profiling Project** — Built for learning and practicing EDA techniques with real-world housing data.
