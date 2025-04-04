# Principal Component Analysis (PCA) on Smoking & Heart Disease Data

This project contains a comprehensive analysis of **Principal Component Analysis (PCA)** using both theoretical understanding and practical application across two real-world datasets: **UK Smoking Survey** and **Heart Disease Patient Records**.

The analysis was conducted as part of **Homework 2** for a data visualization course. All visualizations and analysis are presented in an R Markdown document and output as both HTML and PDF formats.

---

## 👨‍🔬 Author

**Sushrut Gaikwad**  

---

## 🧠 What I Did

### ✅ Part 1: PCA vs. Linear Regression (6 points)

- Compared PCA and linear regression using a toy dataset of height and weight.
- Explained the difference in optimization:  
  - Linear regression minimizes **vertical distances** (residuals).  
  - PCA minimizes **perpendicular distances** from the principal axis.
- Demonstrated both concepts using annotated plots.
- Concluded that PCA and regression solve different problems — hence not equivalent.

---

### ✅ Part 2: PCA on UK Smoking Survey Dataset (27 points)

#### 🔹 Step 1: Load and Clean the Data

- Loaded the dataset from `smoking.rda`.
- Selected a subset of relevant variables: `smoke`, `gender`, `age`, `marital_status`, `highest_qualification`, and `gross_income`.
- Removed incomplete records using `na.omit()`.

#### 🔹 Step 2: Preprocessing

- **Binary Encoding**: Converted `gender` and `smoke` into binary numeric format.
- **One-Hot Encoding**: Converted `marital_status` into five binary columns.
- **Ordinal Encoding**:
  - `highest_qualification` and `gross_income` were encoded using meaningful, ordered factor levels.
  
#### 🔹 Step 3: PCA Implementation

- Standardized the features and applied `prcomp()`.
- Analyzed variance using:
  - **Scree Plot** (explained variance)
  - **Cumulative Variance Plot**

#### 🔹 Step 4: Biplot and Interpretation

- Created a biplot using `ggbiplot` colored by `smoke` status.
- Interpreted principal components by examining loading vectors.
- Assigned descriptive names to each PC (e.g., “Socioeconomic & Marital Status”).

#### 🔹 Step 5: Feature Engineering Improvements

- Proposed and implemented better encoding by:
  - Grouping similar education/income categories.
  - Removing "Refused" and "Unknown" responses from `gross_income`.
- Re-ran PCA and visualizations to reflect improved feature engineering.

---

### ✅ Part 3: PCA on Heart Disease Dataset (27 points)

#### 🔹 Step 1: Load and Inspect Data

- Loaded `heart.csv` containing 14 clinical attributes.
- Inspected data types and structure using `spec()`.

#### 🔹 Step 2: Preprocessing

- **Binary Encoding**: Converted `Sex` and `ExerciseAngina` to 0/1.
- **Ordinal Encoding**:
  - `ChestPainType`, `RestingECG`, and `ST_Slope` were encoded with domain knowledge.
- Ensured all features (except target) were numeric.

#### 🔹 Step 3: PCA and Visualization

- Standardized the data and applied PCA.
- Created both:
  - **Scree Plot** for variance distribution
  - **Biplot** colored by `HeartDisease` status

#### 🔹 Step 4: Interpretation

- Analyzed which principal components separate heart disease patients from healthy ones.
- Highlighted which variables (e.g., Age, MaxHR, Chest Pain Type) were most influential in separation.
- Suggested dimension reduction to 4–7 PCs based on variance explained.

---

## 🖼 Visual Outputs

- PCA Scree Plots
- Cumulative Variance Plots
- PCA Biplots with group coloring
- Custom plots illustrating regression residuals vs. PCA projections

---

## 📁 Project Structure

```{r}
pca-smoking-heart-analysis/
├── data/
│   ├── smoking.rda                     # UK smoking survey dataset
│   └── heart.csv                       # Heart disease dataset
├── scripts/
│   └── analysis_pca.Rmd                # R Markdown with full PCA analysis
├── output/
│   ├── analysis_pca.html               # Rendered interactive report
│   └── analysis_pca.pdf                # PDF version
├── README.md                           # This file
├── LICENSE                             # Project license (MIT)
├── .gitignore                          # Git ignore rules
└── pca-smoking-heart-analysis.Rproj    # RStudio project file
```

---

## 🛠 Requirements

- R (version ≥ 4.0)
- RStudio
- R packages:
  - `tidyverse`
  - `ggbiplot`
  - `gridExtra`
  - `knitr`

---

## 🧪 How to Run

1. Clone or download this repository
2. Open `pca-smoking-heart-analysis.Rproj` in RStudio
3. Open `scripts/analysis_pca.Rmd`
4. Click **Knit** to generate HTML/PDF
5. View visualizations and interpret PCA results

---

## 🧾 License

This project is licensed under the [MIT License](LICENSE).
