# California Housing Prices Prediction

## Project Overview
This project aims to **predict house prices in California** using machine learning techniques. We explore **Linear Regression** and **Random Forest Regressor** models to predict the median house value based on various features such as location, number of rooms, population, and income.  

The project includes:  
- **Data preprocessing** (handling missing values, logarithmic transformation for skewed features)  
- **Feature engineering** (creating new features like bedroom ratio and rooms per household)  
- **Model training and evaluation**  
- **Hyperparameter tuning** using GridSearchCV  

---

## Dataset
The dataset used is the **California Housing dataset**, which contains **20,640 entries** and **10 features**:  

| Feature | Description |
|---------|-------------|
| longitude | House longitude |
| latitude | House latitude |
| housing_median_age | Median age of houses in the block |
| total_rooms | Total number of rooms in the block |
| total_bedrooms | Total number of bedrooms in the block |
| population | Population of the block |
| households | Number of households in the block |
| median_income | Median income of the block |
| median_house_value | Target variable: median house value |
| ocean_proximity | Categorical variable: proximity to the ocean |

---

## Data Preprocessing
1. **Handling missing values**: Rows with missing `total_bedrooms` were removed.  
2. **Log transformation**: Features `total_rooms`, `total_bedrooms`, `population`, and `households` were log-transformed to reduce skewness.  
3. **One-hot encoding**: The categorical feature `ocean_proximity` was converted to numerical dummy variables.  
4. **Feature engineering**:  
   - `bedroom_ratio` = total_bedrooms / total_rooms  
   - `household_rooms` = total_rooms / households  

---

## Exploratory Data Analysis

### Distribution of House Prices
We analyze the distribution of house prices using a histogram to better understand the data spread and detect skewness.

<img src="images/histogramme - Copie.png" alt="House Prices Histogram" width="600">

---

### Correlation Matrix
A correlation matrix is used to identify relationships between numerical features and the target variable.

<img src="images/correlation tab - Copie.png" alt="Correlation Matrix" width="600">

---

### Scatter Plot Analysis
Scatter plots help visualize relationships between house prices and key features such as location and population.

<img src="images/coast - Copie.png" alt="Scatter Plot of House Prices" width="600">


---

## Models Used

### 1. Linear Regression
- Trained on the processed dataset.  
- Achieved **R² score ≈ 0.65–0.68** on the test set.  

### 2. Random Forest Regressor
- Trained with default parameters first: **R² score ≈ 0.81**  
- Hyperparameter tuning using **GridSearchCV** (parameters tested: `n_estimators`, `max_features`)  
- Best model after tuning: **R² score ≈ 0.80**  

> Note: Further tuning or more complex ensemble methods could improve accuracy.  

---
## Conclusion

This project demonstrates a full ML pipeline: from preprocessing raw data to model evaluation and tuning. Random Forest outperformed Linear Regression due to its ability to capture nonlinear relationships.

