# 🏎️ Formula 1 – Historical Driver Analysis

This project explores the career paths of Formula 1 drivers using data analysis techniques in Python, SQL, and Power BI. It was originally developed as a final assignment for the Data Analysis course at UTN – FRC.

The goal was to clean, explore, and visualize historical data to understand how drivers perform over time, what metrics correlate with success, and how exclusive the world of F1 really is.

## 📁 Project Structure

```
├── data/
│   ├── raw_data.csv          # Original dataset from Kaggle
│   └── clean_data.csv        # Cleaned dataset used in analysis & Power BI
├── notebooks/
│   └── f1_analysis.ipynb     # Google Colab notebook (Python + SQL + Visualizations)
├── powerbi/
│   └── f1_dashboard.pbix     # Interactive Power BI dashboard
├── presentation/
│   └── resumen_f1_analysis.pdf # Summary presentation with findings
```

## 📊 Dataset Overview

- **Source:** [Kaggle – Formula 1 Drivers Dataset](https://www.kaggle.com/datasets/dubradave/formula-1-drivers-dataset)
- **Based on:** Wikipedia data, accurate as of the 2023 Bahrain GP
- **Scope:** Only includes officially entered drivers (excluding Friday practice)

### Key Variables
- Driver name, nationality
- Years active, championships
- Race entries, starts, wins, podiums
- Pole positions, fastest laps, total points

## 🧰 Tools & Technologies

- **Python** (Google Colab): `pandas`, `seaborn`, `matplotlib`, `numpy`
- **SQL** (`sqlite3`): basic aggregations and filtering
- **Power BI**: interactive dashboard with slicers by driver and nationality
- **Canva**: presentation design
- **GitHub / Notion**: project and portfolio management

## 🧹 Data Preparation Highlights

Basic preprocessing steps included:

```python
f1_df.info()
f1_df.isnull().sum()
f1_df.duplicated().sum()
f1_df.describe()
```

Most fields were clean, with very few nulls or inconsistencies. Data was exported as `clean_data.csv` for use in Power BI and SQL.

## 🔍 Sample SQL Queries

```sql
-- Top 10 drivers by race wins
SELECT * FROM f1_dataset 
ORDER BY Race_Wins DESC 
LIMIT 10;

-- Top 5 drivers by championships
SELECT Driver, SUM(Championships) AS Total_Championships
FROM f1_dataset
GROUP BY Driver
ORDER BY Total_Championships DESC
LIMIT 5;

-- Most common nationalities
SELECT Nationality, COUNT(*) AS Total
FROM f1_dataset
GROUP BY Nationality
ORDER BY Total DESC
LIMIT 10;
```

## 📈 Exploratory Analysis (Python)

Using Seaborn and Matplotlib, the analysis included:

- Histogram of career length (most drivers lasted ≤1 year)
- Scatter plot of active years vs. race starts (linear relationship)
- Correlation heatmap across numerical features (e.g. wins, poles, podiums)

```python
sns.heatmap(f1_df.corr(), annot=True, cmap='coolwarm')
```

## 📊 Power BI Dashboard

A simple dashboard was created to summarize driver performance metrics. Includes slicers for driver and nationality, showing key stats like race starts, podiums, wins, poles, and titles.

## 🧠 Key Insights

- **Hamilton leads across the board:** wins, points per race, and consistency
- **Strong correlation** between pole positions, wins, and podiums
- **F1 is highly exclusive:** most drivers never win, and average careers are short (1–2 seasons)
- **Nationality distribution** is dominated by a few key countries

## 💬 Lessons Learned

This project helped solidify key skills in the end-to-end data analysis pipeline:

- **Exploratory Data Analysis:** framing meaningful questions and translating them into code and visuals
- **SQL for summarization:** quick profiling of key trends (wins, nationalities, etc.)
- **Storytelling:** combining visuals and insights to explain patterns clearly
- **Technical fluency:** integrating multiple tools (Python, SQL, Power BI) into a single workflow

## 👤 About Me

**Joaquín Ferrer**  
Industrial Engineer · Data Analyst · Power BI · SQL

- 🔗 [LinkedIn](https://linkedin.com/in/joaquin-ferrer)
- 📘 [Notion Portfolio](https://notion.so/joaquin-ferrer)
- 💻 [GitHub](https://github.com/joaquin-ferrer)

## 📌 Notes

This project was developed in collaboration with **Matías Bianco** and **Joaquín Cerdan** as part of a final assignment for the Data Analysis course at UTN (Argentina).

All data and visualizations were originally developed in Spanish. This documentation is provided in English for accessibility.
