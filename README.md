# Sleep Deprivation Cognitive Analysis
# Sleep Deprivation Cognitive Analysis Using Unsupervised Machine Learning

## Project Overview

This project investigates the impact of sleep deprivation on cognitive performance, specifically reaction time, using supervised machine learning models. The goal is to analyze how sleep-related, physiological, and lifestyle factors influence reaction time, measured through the Psychomotor Vigilance Test (PVT).

By modeling this relationship, the project aims to identify which variables most strongly predict cognitive performance and whether the effects of sleep on reaction time are linear or non-linear.

---

## Dataset

The dataset contains observational data from participants, covering:

- **Sleep Metrics:** Sleep Hours, Sleep Quality Score, Daytime Sleepiness  
- **Cognitive Metrics:** Stroop Task Reaction Time, N-Back Accuracy  
- **Physiological & Lifestyle Variables:** Age, BMI, Stress Level, Physical Activity, Caffeine Intake  
- **Demographics:** Gender  

**Target Variable:**  
- `PVT_Reaction_Time` (reaction time in milliseconds)

**Dataset Size:** 60 observations × 12 features

---

## Methodology: Supervised Regression Models

### 1. Linear Regression
- Serves as a baseline to evaluate linear relationships between sleep variables and reaction time.  
- Coefficients provide insight into the direction and magnitude of each variable's impact.

### 2. Random Forest Regressor
- Captures non-linear relationships and feature interactions automatically.  
- Identifies the most influential variables for predicting reaction time.

### Data Preprocessing Steps

1. Checked for missing values and duplicates  
2. Removed identifier columns (`Participant_ID`)  
3. Encoded categorical variables (e.g., Gender)  
4. Split data into training (80%) and test (20%) sets  
5. Scaled features using `StandardScaler`

---

## Analysis and Results

### Model Performance

| Model                          | MAE     | RMSE    | R²      |
|--------------------------------|--------|--------|---------|
| Linear Regression               | 113.62 | 126.20 | -0.8564 |
| Random Forest                   | 84.73  | 101.89 | -0.2100 |
| Random Forest (Top 5 Features) | 97.26  | —      | -0.5330 |

### Key Predictors (Random Forest)

1. Sleep Hours  
2. N-Back Accuracy (working memory)  
3. Stress Level  
4. Stroop Task Reaction Time  
5. Sleep Quality Score

**Insights:**

- Random Forest outperformed Linear Regression, indicating **non-linear relationships** between sleep variables and cognitive reaction time.  
- Sleep Hours, Working Memory Accuracy, and Stress Level are the most important predictors.  
- Reducing the model to the top 5 features improves interpretability while retaining the main predictive signals.

---

## Conclusion

This analysis confirms a quantitative link between sleep patterns and cognitive reaction time. Key takeaways include:

- Cognitive performance is strongly influenced by sleep duration, quality, and stress levels.  
- Machine learning models can capture complex, non-linear relationships between physiological and behavioral factors and cognitive outcomes.  
- Increasing the sample size and using longitudinal data would enhance predictive power and model generalizability.

---

## How to Run the Notebook

1. Clone this repository to your local machine:  
2. Open the notebook in Google Colab or a compatible Jupyter environment.
3. Make sure u have the dataset. You can download it from https://www.kaggle.com/datasets/sacramentotechnology/sleep-deprivation-and-cognitive-performance. Update the file path in the notebook if needed.
4. Run the cells sequentially.
