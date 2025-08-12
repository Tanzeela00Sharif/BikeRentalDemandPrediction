# BikeRentalDemandPrediction

# 🚲 Bike Rental Demand Prediction

## 📌 Overview
This project predicts **bike rental demand** using historical data containing time, weather, and calendar features.  
The model uses **Decision Tree Regression** and **Linear Regression** to estimate the number of bikes rented at a given time.

---

## 🎯 Problem Statement
Bike-sharing companies need to forecast the demand for bikes to:
- Ensure enough bikes are available at each station
- Reduce shortages and over-supply
- Optimize staff scheduling for bike redistribution
- Improve customer satisfaction

This is a **supervised regression problem**, where the target variable is the **count** of bikes rented.

---

## 📂 Dataset
The dataset contains:
- **datetime**: Date and time of the record
- **season**: Season (1: spring, 2: summer, 3: fall, 4: winter)
- **holiday**: Whether the day is a holiday (1) or not (0)
- **workingday**: Whether it’s a working day (1) or weekend/holiday (0)
- **weather**: Weather condition category
- **temp**: Temperature in Celsius
- **atemp**: "Feels like" temperature
- **humidity**: Relative humidity
- **windspeed**: Wind speed
- **count**: Total number of bike rentals (target variable)

---

## 🛠 Data Preprocessing
1. Converted `datetime` to a proper datetime type.
2. Extracted additional time-based features:
   - `hour`
   - `day`
   - `month`
   - `year`
   - `dayofweek`
3. Dropped unnecessary columns:
   - `casual`
   - `registered`
4. Split data into **train** and **test** sets.

---

## 🤖 Models Used
- **Decision Tree Regressor**
- **Linear Regression**

---

## 📊 Model Evaluation
Metrics used:
- **R² Score** (explains variance)
- **MAE** (Mean Absolute Error)
- **MSE** (Mean Squared Error)
- **RMSE** (Root Mean Squared Error)

**Results:**
| Model                   | R² Score (Single Split) | R² Score (Cross-Validation) |
|-------------------------|-------------------------|-----------------------------|
| Decision Tree Regressor | 0.8905                  | 0.5950                      |
| Linear Regression       | 0.3593                  | ~0.35                       |


| Model                   | mean_squared_error      | root_mean_squared_error 144.89 |
|-------------------------|-------------------------|--------------------------------|
| Decision Tree Regressor | 3587.421                | 59.89                          |
| Linear Regression       | 20994.7                 | 144.89                         |

---

## ⚠ Observations
- **Decision Tree** performs much better than Linear Regression for this dataset because it captures **non-linear relationships**.
- Cross-validation shows lower performance than a single split → possible **overfitting**.
- Model tuning (e.g., `max_depth`, `min_samples_split`) can help improve generalization.

---

## 🚀 How to Run
```bash
# Clone this repository
git clone https://github.com/https://github.com/Tanzeela00Sharif/bike-rental-prediction.git

# Navigate into the project directory
cd bike-rental-prediction

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook bike_rental_prediction.ipynb
