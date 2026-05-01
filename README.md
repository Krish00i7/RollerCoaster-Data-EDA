# 🎢 RollerCoaster Data — Exploratory Data Analysis

A comprehensive Exploratory Data Analysis (EDA) of a global roller coaster dataset, uncovering trends in speed, design, inversions, and park locations using Python's data science stack.

---

## 📌 Project Overview

This project dives into a rich dataset of roller coasters from around the world to explore how coaster design has evolved over time, which locations have the fastest rides, and what relationships exist between speed, inversions, coaster type, and geography.

---

## 📁 Repository Structure

```
RollerCoaster-Data-EDA/
│
├── RollerCoaster_EDA.ipynb   # Main Jupyter Notebook with full analysis
├── coaster_db.csv            # Raw roller coaster dataset
├── README.md                 # Project documentation
└── LICENSE                   # License file
```

---

## 📊 Dataset

**File:** `coaster_db.csv`

The dataset contains detailed records of roller coasters from across the globe, spanning over a century of coaster history. Key columns used in the analysis include:

| Column | Description |
|---|---|
| `coaster_name` | Name of the roller coaster |
| `location` | Park/location of the coaster |
| `status` | Current status (Operating, Removed, Closed, etc.) |
| `manufacturer` | Manufacturer of the coaster |
| `type_main` | Type of coaster (Wood / Steel) |
| `year_introduced` | Year the coaster first opened |
| `opening_date_clean` | Cleaned opening date |
| `speed_mph` | Top speed in miles per hour |
| `inversions_clean` | Number of inversions |
| `latitude` / `longitude` | Geographic coordinates |

---

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** — Data loading, cleaning, and transformation
- **NumPy** — Numerical operations
- **Matplotlib** — Base visualizations
- **Seaborn** — Statistical plots and styled visuals
- **SciPy** — KDE plots and statistical analysis
- **Jupyter Notebook** — Interactive analysis environment

---

## 🔍 Analysis Workflow

### 1. Data Loading & Initial Inspection
- Loaded `coaster_db.csv` with Pandas
- Inspected shape, dtypes, and column inventory
- Selected relevant columns for analysis

### 2. Data Cleaning
- Parsed and standardized `opening_date_clean` to datetime
- Lowercased all column names for consistency
- Removed duplicate coasters based on `(coaster_name, location, opening_date_clean)`
- Dropped high-null columns (`height_ft`, `gforce_clean`)
- Filled missing values:
  - `manufacturer` and `status` → `"Unknown"`
  - `speed_mph` → filled with median speed
- Dropped rows missing `latitude` / `longitude`

### 3. Feature Understanding
- **Top 10 years** with the most coasters introduced (bar chart)
- **Speed distribution** — histogram and KDE plot of `speed_mph`

### 4. Feature Relationships
- **Scatter plot:** Year introduced vs. Speed (mph) using Matplotlib and Seaborn (colored by coaster type)
- **Pair plot:** Multi-variable relationships across `year_introduced`, `speed_mph`, `inversions_clean`, `latitude`, and `longitude` — hued by `type_main`
- **Bar chart:** Average coaster speed by location (filtered to locations with 10+ coasters)

---

## 📈 Key Visualizations

| Visualization | Insight |
|---|---|
| Top 10 Years Coasters Introduced | Identifies the boom periods in coaster construction |
| Coaster Speed Histogram & KDE | Shows the speed distribution across all coasters |
| Year vs. Speed Scatter Plot | Highlights how coaster speeds have increased over decades |
| Pairplot by Coaster Type | Reveals correlations between design variables for Wood vs. Steel coasters |
| Average Speed by Location | Compares parks and regions by their mean coaster speed |

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

### Run the Notebook

```bash
git clone https://github.com/Krish00i7/RollerCoaster-Data-EDA.git
cd RollerCoaster-Data-EDA
jupyter notebook RollerCoaster_EDA.ipynb
```

---

## 💡 Key Findings

- **Steel coasters** tend to be significantly faster than wooden ones.
- Coaster speeds have generally **increased over the decades**, reflecting advances in engineering.
- A handful of **locations/parks** consistently outperform others in average top speed.
- **Inversions** are far more common in steel coasters than wooden ones.
- The dataset spans **over 130 years** of coaster history, from the 1880s to the present day.

---

## 📄 License

This project is licensed under the terms of the [LICENSE](LICENSE) file included in this repository.

---

## 🙌 Acknowledgements

- Dataset sourced from a publicly available roller coaster database.
- Inspired by real-world data analysis workflows for theme park enthusiasts and data science learners alike.
