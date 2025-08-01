# 🚘 Car Price Prediction using Machine Learning

This project demonstrates a complete end-to-end **machine learning pipeline** to predict the **selling price of used cars** based on various features like mileage, engine capacity, power, manufacturer, etc. The project leverages both **Linear Regression** and **Random Forest Regressor** for prediction and compares their performance.

---

## 📈 Problem Statement

The goal is to **predict the price of a used car** based on a variety of parameters such as:

* Brand and model
* Year of manufacture
* Kilometers driven
* Fuel type
* Transmission type
* Ownership history
* Engine size and power
* Mileage
* Number of seats

---

## 📁 Dataset Overview

The dataset used in this project was sourced as a `.csv` file. It includes 12 attributes, with the target variable being the `Price` of the car.

| Feature            | Description                                      |
| ------------------ | ------------------------------------------------ |
| Name               | Full name of the car (Make + Model)              |
| Year               | Manufacturing year                               |
| Kilometers\_Driven | Distance driven in kilometers                    |
| Fuel\_Type         | Fuel category (Petrol, Diesel, etc.)             |
| Transmission       | Type of transmission (Manual/Automatic)          |
| Owner\_Type        | Indicates the ownership level (First, Second...) |
| Mileage            | Mileage in kmpl or km/kg                         |
| Engine             | Engine capacity in cc                            |
| Power              | Power output in bhp                              |
| Seats              | Number of seats                                  |
| New\_Price         | Price of the new car (mostly missing, dropped)   |
| Price              | **Selling price** of the used car (**Target**)   |

---

## 🧪 Project Workflow

### 📌 1. Data Loading

The dataset is loaded using `pandas.read_csv()`.

### 📌 2. Exploratory Data Analysis (EDA)

* Visualized the distribution of manufacturers using Seaborn’s `countplot`.
* Explored relationships between features and checked for missing values.

### 📌 3. Data Preprocessing

#### 🔹 Feature Engineering

* Extracted `Manufacturer` from the `Name` column by splitting the string.
* Dropped the original `Name` column after extracting useful information.

#### 🔹 Data Cleaning

* Removed non-numeric units from `Mileage`, `Engine`, and `Power` using `.str.split()` and `pd.to_numeric()`.
* Handled missing values using **mean imputation** for `Mileage`, `Engine`, `Power`, and `Seats`.
* Dropped `New_Price` due to excessive missing data.

#### 🔹 Encoding

* Used **One-Hot Encoding** (`pd.get_dummies`) for categorical columns:

  * `Manufacturer`
  * `Fuel_Type`
  * `Transmission`
  * `Owner_Type`

#### 🔹 Standardization

* Applied `StandardScaler` to standardize the dataset, ensuring all features are on the same scale.

### 📌 4. Model Building

Two regression models were trained:

#### 🔸 Linear Regression

* Baseline model for price prediction.
* Achieved an **R² Score** of approximately `0.701`.

#### 🔸 Random Forest Regressor

* Ensemble learning model for better accuracy.
* Trained with 100 estimators.
* Achieved higher **R² Score** than linear regression (exact score printed during execution).

---

## 📈 Results

| Model                   | R² Score            |
| ----------------------- | ------------------- |
| Linear Regression       | 0.701               |
| Random Forest Regressor | **> 0.75** (approx) |

* **Random Forest** outperforms Linear Regression by capturing non-linear relationships and being more robust to outliers and missing patterns.

---

## 📊 Visualizations

A count plot was created to visualize the number of cars per manufacturer:

```python
sns.countplot(x='Manufacturer', data=X_train)
plt.xticks(rotation=90)
```

This helps understand brand distribution and potential imbalance in the dataset.

---

## 🛠️ Technologies Used

* **Python 3.11**
* **Pandas** – for data manipulation
* **NumPy** – for numerical operations
* **Matplotlib & Seaborn** – for visualization
* **Scikit-learn** – for model building, scaling, training/testing

---

## 🧐 Concepts Demonstrated

* Data Wrangling and Cleaning
* Feature Engineering
* Handling Missing Data
* One-Hot Encoding for Categorical Variables
* Feature Scaling
* Regression Modeling (Linear & Ensemble)
* Model Evaluation using R² Score

---

## 🔍 How to Use

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/car-price-prediction.git
   ```

2. Navigate to the project folder:

   ```bash
   cd car-price-prediction
   ```

3. Install required libraries:

   ```bash
   pip install -r requirements.txt
   ```

4. Make sure your dataset is placed at:

   ```
   C:/Users/aqeel/OneDrive/Documents/dataset.csv
   ```

   *(Or update the path in the script)*

5. Run the notebook or script:

   ```bash
   jupyter notebook model_training.ipynb
   ```

---

## 📂 Project Structure

```
car-price-prediction/
│
├── dataset.csv
├── model_training.ipynb
├── README.md
└── requirements.txt
```

---

## 📾 Sample Output

```python
Linear Regression R² Score: 0.7008
Random Forest R² Score: 0.78 (approx)
```

---

## 🙋‍♂️ Author

**Aqeel Mohamed**
B.Tech Graduate | AI & ML Enthusiast | Aspiring Data Scientist
📍 Kozhikode, Kerala, India

---

## 🌟 Acknowledgements

* Dataset format inspired by online used car listings.
* This project is educational and serves as an example of applied ML techniques in real-world domains.

---

## 📌 Disclaimer

* The dataset and model are not production-ready.
* For commercial or high-accuracy use cases, further data cleaning, hyperparameter tuning, and validation are necessary.

---
