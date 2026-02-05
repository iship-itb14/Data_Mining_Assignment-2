# Automated Exploratory Data Analysis (EDA) System

To open the google colab file, use URL: https://colab.research.google.com/drive/1vHhIRr8UckjHswS72zH6adtnRPwBcRk6#scrollTo=EeAVXxSkie97

Both Datasets are available in the "data" folder.

## Project Overview
This project implements a generalized, automated Exploratory Data Analysis (EDA) system in Python that can analyze any user-provided CSV dataset and generate meaningful, reproducible insights.

The system mirrors and extends the in-class “getting to know your data” workflow by automatically:
- Inspecting dataset structure and quality  
- Computing descriptive statistics  
- Generating informative visualizations  
- Producing human-readable insights  
- Identifying limitations and potential bias  

The system is designed to work with or without a schema/data dictionary and to generalize across datasets with very different structures.

---

## Objectives
- Build an end-to-end EDA pipeline that works on unseen datasets  
- Ensure correctness, interpretability, and reproducibility  
- Combine traditional data analysis with GenAI-assisted insight generation  
- Produce clean, report-ready outputs (plots and text)  

---

---

## Datasets Used

### Spotify Dataset (Development Dataset)
- Source: Kaggle (public, non-sensitive)
- Size: 85,000 rows × 19 columns
- Type: Music streaming and audio feature data
- Mix of numerical and categorical variables

### Anime Dataset (Unseen Dataset)
- Source: Public Kaggle dataset
- Type: Media metadata and ratings
- Used to demonstrate generalization to a new dataset

---

## Features Implemented

### Dataset Overview
- Dataset shape (rows and columns)
- Column names and inferred data types
- Missing value summary
- Duplicate row detection
- Detection of constant or near-constant columns
- High-missingness warnings

---

### Descriptive Statistics

#### Numerical Features
- Minimum and maximum values  
- Mean, median, and mode  
- Standard deviation  
- Interquartile range (IQR)  
- Outlier detection using the 1.5 × IQR rule  

#### Categorical Features
- Frequency counts  
- Percentage distributions  
- Detection of dominant or imbalanced categories  

---

### Visualizations
A minimum of five plots are generated per dataset. All plots include titles, labeled axes, and a consistent color palette.

Visualization types include:
- Histogram  
- Boxplot  
- Bar chart  
- Scatter plot  
- Correlation heatmap  

---

### Human-Readable Insights
Insights are generated automatically and are data-driven rather than generic. They reference specific columns, distributions, correlations, and anomalies.

Insights are generated using:
```python
generate_insights(df, dataset_name)
```
Limitations and Bias Analysis
Potential limitations are identified automatically, including:
Missing data issues
Class imbalance
Presence of outliers
Observational data constraints
Limited generalizability beyond the dataset scope

Limitations are generated using:
```python
generate_limitations(df, dataset_name)
```


### Reproducibility
The project runs end-to-end without manual intervention
Results are deterministic
The same inputs produce the same outputs
The system generalizes to unseen datasets
Key Takeaways
The system performs automated EDA on heterogeneous datasets
Insights are statistically grounded and interpretable
A verification layer ensures correctness when using GenAI
The pipeline emphasizes transparency, reproducibility, and trust


### Acknowledgments
All datasets used are public and non-sensitive, sourced from Kaggle for educational purposes.
