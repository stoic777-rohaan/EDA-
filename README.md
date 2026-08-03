# 💻 Developer Stress — Exploratory Data Analysis (EDA)

An exploratory data analysis (EDA) project investigating what factors might be linked to stress levels among software developers — built while practicing core data cleaning, wrangling, and visualization techniques with Pandas, Matplotlib, and Seaborn.

---

## 📌 Project Overview

This project explores a dataset of 500 developer records capturing daily work habits (hours worked, sleep, coffee intake, meetings, deadlines, code complexity, etc.) and analyzes how these factors relate to reported **stress levels**.

The notebook walks through a complete, beginner-friendly EDA workflow:

1. **Data loading** — importing the dataset directly from Kaggle
2. **Initial inspection** — checking shape, data types, and a preview of the data
3. **Data cleaning**
   - Dropping irrelevant columns (`Interruptions`)
   - Renaming columns for clarity (e.g. `Experience_Years` → `work_experience`, `Deadline_Days` → `Dead_line`, `Coffee_Cups` → `Coffee`)
   - Checking and removing duplicate rows
   - Checking and handling missing values (`dropna`)
4. **Outlier detection** — boxplots for key numeric features (`Stress_Level`, `Dead_line`)
5. **Visual analysis**
   - Distribution of code complexity across projects (bar chart)
   - Correlation heatmap across all numeric features
   - Scatter plot of hours worked vs. stress level

---

## 📊 Dataset

**Source:** [Kaggle — Developer Stress dataset](https://www.kaggle.com/)

The dataset contains **500 rows** and the following features (post-cleaning):

| Column | Description |
|---|---|
| `Hours_Worked` | Number of hours worked in a day |
| `Sleep_Hours` | Hours of sleep the developer got |
| `Bugs` | Number of bugs encountered/reported |
| `Dead_line` | Days remaining until project deadline |
| `Coffee` | Cups of coffee consumed |
| `Meetings` | Number of meetings attended |
| `work_experience` | Developer's years of experience |
| `Code_Complexity` | Categorical complexity level of the codebase/project |
| `Remote_Work` | Whether the developer worked remotely |
| `Stress_Level` | Reported stress level (target variable of interest) |

> Note: the notebook loads the data via a temporary signed Kaggle URL. If you're re-running this, download the dataset from Kaggle directly and load it from a local CSV instead — see [Getting Started](#-getting-started) below.

---

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** — data loading, cleaning, and wrangling
- **NumPy** — numerical operations
- **Matplotlib** — plotting
- **Seaborn** — statistical visualizations (boxplots, heatmaps)

---

## 🔍 Key Steps & Findings

- Verified the dataset had **no duplicate rows** and, after cleaning, **no missing values**.
- Used **boxplots** to visually check for outliers in stress level and deadline pressure.
- Visualized the **distribution of code complexity** across projects to understand the dataset's composition.
- Built a **correlation heatmap** to see which numeric factors (hours worked, sleep, coffee, meetings, deadlines) move together with stress level.
- Plotted **hours worked vs. stress level** to visually inspect whether longer hours trend with higher reported stress.

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn
```

### 3. Get the dataset
Download the dataset from Kaggle and save it locally, e.g. as `developer_stress.csv`, then update the `pd.read_csv(...)` line in the notebook to point to your local file:
```python
df = pd.read_csv("developer_stress.csv")
```

### 4. Run the notebook
```bash
jupyter notebook EDA_keggle.ipynb
```

---

## 🎯 What I Learned

- How to perform a structured, end-to-end EDA on a real-world-style dataset
- Practical data cleaning steps: dropping columns, renaming for clarity, handling duplicates and nulls
- Using boxplots to spot outliers and understand data spread
- Reading and interpreting a correlation heatmap
- Choosing the right chart (bar, box, scatter, heatmap) to answer different questions about the data

---

## 🔮 Future Improvements

- Add statistical tests (e.g. correlation significance) to back up visual observations
- Explore categorical features (`Code_Complexity`, `Remote_Work`) against stress level using group comparisons
- Build a simple regression model to predict stress level from the other features
- Add summary statistics tables alongside the visualizations

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ If you found this project helpful, consider giving it a star!
