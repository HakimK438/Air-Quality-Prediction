# Air Quality Prediction

This project focuses on predicting **air quality levels** using environmental, meteorological, and demographic factors. The objective is to classify air quality into four categories—**Good, Moderate, Poor, and Hazardous**—based on pollutant concentrations and surrounding conditions.

The problem is framed as a **multi-class classification task**, reflecting how air quality is commonly reported and monitored in real-world systems.

# Dataset Overview

The dataset contains **5,000 observations** with the following features:

1. Temperature  
2. Humidity  
3. PM2.5  
4. PM10  
5. NO₂  
6. SO₂  
7. CO  
8. Proximity to Industrial Areas  
9. Population Density  

The target variable, **Air_Quality**, represents categorical air quality levels:
- Good  
- Moderate  
- Poor  
- Hazardous  

Class distribution is imbalanced, with fewer hazardous cases compared to good and moderate levels, which influenced model evaluation and validation strategy.

# Data Preparation

- Column names were standardized for consistency.
- Air quality labels were encoded numerically:
  - Good → 0  
  - Moderate → 1  
  - Poor → 2  
  - Hazardous → 3
- Features were scaled using **StandardScaler** where required.
- Stratified train–test splitting was applied to preserve class proportions.

# Exploratory Analysis

Exploratory visualizations such as **scatter plots** and **pair plots** were used to examine relationships between pollutants, temperature, and humidity across air quality classes. These plots highlighted non-linear separations between categories, suggesting that simple linear models may struggle in some regions of the feature space.

# Modeling Approach

Multiple machine learning models were trained and evaluated:

- **Logistic Regression** was used as a baseline. It performed well overall but struggled to clearly separate higher-risk air quality categories, particularly Poor and Hazardous.

- **K-Nearest Neighbors (KNN)** showed reasonable performance and captured local patterns in the data, but its predictions were sensitive to scaling and parameter choices.

- **Decision Tree** models handled non-linear relationships more effectively and provided clearer decision boundaries. However, their behavior varied depending on the data split, which raised concerns about consistency.

# Evaluation Strategy

Model evaluation did not rely solely on accuracy. Instead, the following were emphasized:

- Confusion matrices to analyze class-wise misclassifications  
- Macro-averaged F1 scores to account for class imbalance  
- Stratified cross-validation to assess robustness and generalization  

This approach ensured that minority classes, especially **Hazardous air quality**, were not overlooked during evaluation.

# Key Takeaways

- Pollutant concentrations (PM2.5, PM10, NO₂) play a dominant role in air quality classification.
- Non-linear models handle class boundaries more effectively than purely linear approaches.
- Confusion matrices are critical for understanding where models fail, especially in imbalanced multi-class problems.
- Evaluation metrics should align with real-world impact, not just overall accuracy.

This project demonstrates an end-to-end machine learning workflow, from data exploration and preprocessing to multi-model comparison and robust evaluation, applied to an environmentally meaningful problem.
