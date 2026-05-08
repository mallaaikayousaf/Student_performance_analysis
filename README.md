# 📊 Student Performance Analysis

A data analysis project that explores how demographic and socioeconomic factors — such as gender, parental education level, lunch type, and test preparation — influence student exam scores in math, reading, and writing.

---

## 📁 Project Structure

```
Student_Performance_Analysis/
│
├── .gitignore
├── README.md
│
├── Data/
│   ├── StudentsPerformance.csv          # Original raw dataset (from Kaggle)
│   ├── messy_students.csv               # Artificially corrupted dataset (for cleaning demo)
│   ├── cleaned_students.csv             # Final cleaned dataset
│   └── descriptive_statistics.csv       # Exported summary statistics
│
├── notebooks/
│   ├── dataLoading.ipynb                # Dataset loading & initial exploration
│   ├── descriptiveStatistics.ipynb      # Mean, median, mode, std, groupby analysis
│   ├── dataCleaning.ipynb               # Handling missing values, duplicates & outliers
│   ├── EDAandCorrelation.ipynb          # Groupby EDA + correlation matrix & heatmap
│   └── dataVisualization.ipynb          # All final plots and dashboard
│
└── plots/
    ├── plot1_histogram_math.png
    ├── plot2_boxplot_math_gender.png
    ├── plot3_scatter_reading_writing.png
    ├── plot4_barchart_parent_education.png
    ├── correlation_heatmap.png
    ├── pairplot_scores.png
    └── best_visualization.png
```

---

## 📋 Dataset

- **Source:** [Kaggle – Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
- **Records:** 1,000 students
- **Features:**

| Column | Description |
|---|---|
| `gender` | Student gender (male / female) |
| `race/ethnicity` | Ethnic group (Group A–E) |
| `parental level of education` | Highest education level of parent |
| `lunch` | Lunch type (standard / free or reduced) |
| `test preparation course` | Whether student completed prep course |
| `math score` | Math exam score (0–100) |
| `reading score` | Reading exam score (0–100) |
| `writing score` | Writing exam score (0–100) |

---

## 🔬 Analysis Overview

### 1. `dataLoading.ipynb` — Data Loading & Exploration
- Loads the raw dataset and inspects its shape, types, and basic info
- Checks for missing values and reviews unique values in categorical columns
- Computes initial summary statistics

### 2. `descriptiveStatistics.ipynb` — Descriptive Statistics
- Calculates mean, median, mode, standard deviation, min, and max for all three subjects
- Compares mean vs. median to assess score distribution skewness
- Performs groupby analysis across gender, parental education, test prep, lunch type, and race/ethnicity
- Exports results to `Data/descriptive_statistics.csv`

### 3. `dataCleaning.ipynb` — Data Cleaning
- Artificially introduces problems into the dataset (missing values, duplicates, outliers, invalid categories) to simulate real-world messy data
- Documents all problems found and applies a step-by-step cleaning process:
  - Removes duplicate rows
  - Fills missing numeric values with column medians
  - Fills missing categorical values with column modes
  - Clips outlier scores to the valid 0–100 range
  - Fixes invalid gender/category values
- Produces a before vs. after comparison and saves the result as `Data/cleaned_students.csv`

### 4. `EDAandCorrelation.ipynb` — EDA & Correlation Analysis
- Performs grouped analysis across all demographic variables
- Investigates the interaction between gender and test preparation
- Computes the Pearson correlation matrix for math, reading, and writing scores
- Generates and saves:
  - `plots/correlation_heatmap.png`
  - `plots/pairplot_scores.png`

### 5. `dataVisualization.ipynb` — Data Visualization
- Produces 5 individual charts and 1 combined dashboard figure:
  - Histogram of math score distribution with KDE, mean, and median lines
  - Boxplot of math scores by gender
  - Scatter plot of reading vs. writing scores (coloured by gender)
  - Horizontal bar chart of average math score by parental education level
  - 2×2 dashboard combining score distributions, test prep comparison, correlation heatmap, and parental education breakdown
- All plots saved to the `plots/` folder

---

## 📈 Key Findings

- **Gender:** Female students score higher in reading (+5.5 pts) and writing (+5.8 pts); male students score marginally higher in math (+2.3 pts).
- **Parental Education:** Students with master's-degree parents score ~19 points higher in math than those whose parents completed only high school — the single strongest predictor of performance.
- **Test Preparation:** Completing the prep course improves scores by an average of 7 points across all subjects, with equal benefit for both genders.
- **Score Correlations:** Reading and writing are very strongly correlated (r ≈ 0.942). Math has a moderate correlation with both language subjects (r ≈ 0.76–0.78).
- **Lunch Type:** Students with standard lunch consistently outscore free/reduced lunch peers by 15–20 points, reflecting broader socioeconomic influence.
- **Race/Ethnicity:** Group E students average ~76 across subjects while Group A averages ~64, an 11.8-point gap.

---

## 🛠️ Technologies Used

| Tool | Purpose |
|---|---|
| Python 3.x | Core programming language |
| Pandas | Data loading, cleaning, and analysis |
| NumPy | Numerical operations |
| Matplotlib | Plotting and figure customization |
| Seaborn | Statistical visualizations |
| Jupyter Notebook | Interactive development environment |
| Git & GitHub | Version control |

---

## ⚙️ How to Run

**1. Clone the repository**
```bash
git clone https://github.com/mallaaikayousaf/Student_performance_analysis.git
cd Student_performance_analysis
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

Or install from the requirements file if present:
```bash
pip install -r requirements.txt
```

**3. Download the dataset**

Download `StudentsPerformance.csv` from [Kaggle](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams) and place it in the `Data/` folder.

**4. Run notebooks in order**
```
1. dataLoading.ipynb
2. descriptiveStatistics.ipynb
3. dataCleaning.ipynb
4. EDAandCorrelation.ipynb
5. dataVisualization.ipynb
```

> ⚠️ `dataCleaning.ipynb` must be run before the EDA and visualization notebooks, as it generates `cleaned_students.csv` which the later notebooks depend on.

---

## 📊 Sample Visualizations

| Plot | Description |
|---|---|
| `plot1_histogram_math.png` | Math score distribution with KDE curve |
| `plot2_boxplot_math_gender.png` | Math score spread by gender |
| `plot3_scatter_reading_writing.png` | Reading vs. writing score relationship |
| `plot4_barchart_parent_education.png` | Average math score by parental education |
| `correlation_heatmap.png` | Heatmap of inter-subject correlations |
| `pairplot_scores.png` | Pairwise score distributions |
| `best_visualization.png` | Combined 2×2 analysis dashboard |

---

## 👤 Author

**Mallaika Yousaf**  

---

## 📄 License

This project is for educational purposes. Dataset credit goes to the original uploader on [Kaggle](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams).