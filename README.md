# 🚗 Car Price Prediction using Machine Learning

This project aims to predict the **selling price of used cars** using various regression models, including **Linear Regression** and **Random Forest Regressor**. The dataset contains attributes such as mileage, power, engine capacity, ownership type, and more.

---

## 📁 Dataset

The dataset (`dataset.csv`) contains information about used cars with the following features:

- `Name`
- `Year`
- `Kilometers_Driven`
- `Fuel_Type`
- `Transmission`
- `Owner_Type`
- `Mileage`
- `Engine`
- `Power`
- `Seats`
- `New_Price` *(mostly null, dropped during preprocessing)*
- `Price` *(target variable)*

---

## 🧪 Workflow

### 1. **Importing Libraries**
Standard Python libraries used include:
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `sklearn` modules (for preprocessing, training, and evaluation)

### 2. **Data Preprocessing**
- Extracted `Manufacturer` from `Name`
- Removed units from `Mileage`, `Engine`, and `Power` (e.g., "kmpl", "cc", "bhp")
- Handled missing values using **mean imputation**
- Dropped `New_Price` column due to excessive null values
- Applied **one-hot encoding** to categorical columns: `Manufacturer`, `Fuel_Type`, `Transmission`, `Owner_Type`
- Standardized features using `StandardScaler`

### 3. **Model Training and Evaluation**
- **Linear Regression**
  - `R² Score`: ~0.701
- **Random Forest Regressor**
  - `R² Score`: higher than linear regression (exact score printed in output)

---

## 📊 Visualization

Plotted the distribution of cars by manufacturer using Seaborn’s `countplot`, giving insight into the most popular brands in the dataset.

---

## ✅ Requirements

Install dependencies using pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
