# Insurance Cost Prediction using Linear Regression

A Machine Learning project that predicts **medical insurance charges** using Linear Regression.

The project uses the Insurance dataset and explores how factors such as age, BMI, smoking status, number of children, sex, and region can influence insurance charges.

## 📌 Project Overview

The goal of this project is to build a Linear Regression model that can predict an individual's medical insurance cost based on their personal and demographic information.

The project includes:

* Data loading and exploration
* Data visualization
* Data preprocessing
* Categorical variable encoding
* Train-test splitting
* Linear Regression model training
* Insurance charge prediction
* R² score evaluation
* Adjusted R² evaluation
* Feature interaction
* Underfitting and overfitting analysis

## 📊 Dataset

The dataset contains **1,338 records and 7 columns**.

### Features

| Feature    | Description                        |
| ---------- | ---------------------------------- |
| `age`      | Age of the individual              |
| `sex`      | Gender                             |
| `bmi`      | Body Mass Index                    |
| `children` | Number of children                 |
| `smoker`   | Smoking status                     |
| `region`   | Residential region                 |
| `charges`  | Medical insurance charges (target) |

### Target Variable

`charges`

The model attempts to predict the medical insurance charges for an individual.

## 🛠️ Technologies Used

* Python
* Pandas
* Seaborn
* Scikit-learn
* Jupyter Notebook
* Linear Regression

## 🔄 Project Workflow

```text
Dataset
   ↓
Data Exploration
   ↓
Data Visualization
   ↓
Data Preprocessing
   ↓
Feature Encoding
   ↓
Train-Test Split
   ↓
Linear Regression
   ↓
Prediction
   ↓
Model Evaluation
```

## 🧹 Data Preprocessing

Categorical variables were converted into numerical values.

For example:

```python
X["sex"] = X["sex"].map({"female": 1, "male": 0})
X["smoker"] = X["smoker"].map({"yes": 1, "no": 0})
```

The dataset was divided into training and testing sets using an **80/20 split**.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

## 🤖 Model

The project uses:

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()
model.fit(X_train, y_train)
```

Predictions are generated using:

```python
y_pred = model.predict(X_test)
```

## 📈 Model Performance

### Initial Model

The initial model achieved:

* **R² Score:** `0.7811`
* **Adjusted R²:** `0.7770`

### Model with Feature Interactions

Additional interaction features were created:

```python
X["age_smoker"] = X["age"] * X["smoker"]
X["bmi_smoker"] = X["bmi"] * X["smoker"]
```

After adding these features, the model achieved:

* **Test R² Score:** `0.8652`
* **Training R² Score:** `0.8341`

The improved model performed better than the initial model.

## 📂 Project Structure

```text
insurance-cost-prediction-linear-regression/
│
├── linear_regression.ipynb
├── insurance.csv
├── README.md
└── requirements.txt
```

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/insurance-cost-prediction-linear-regression.git
```

### 2. Navigate to the project

```bash
cd insurance-cost-prediction-linear-regression
```

### 3. Install dependencies

```bash
pip install pandas seaborn scikit-learn jupyter
```

Or use:

```bash
pip install -r requirements.txt
```

### 4. Open the notebook

```bash
jupyter notebook linear_regression.ipynb
```

## 💡 Key Learning

Through this project, I practiced:

* Data preprocessing
* Exploratory Data Analysis
* Data visualization
* Feature engineering
* Categorical encoding
* Linear Regression
* Train-test splitting
* Model evaluation
* R² and Adjusted R²
* Feature interaction
* Understanding underfitting and overfitting

## 🔮 Future Improvements

Possible improvements for this project include:

* Comparing Linear Regression with other regression algorithms
* Trying Random Forest Regression
* Trying Gradient Boosting
* Hyperparameter tuning
* Cross-validation
* More detailed exploratory data analysis
* Building a simple web application for predictions

## 👨‍💻 Author

**Your Name**

If you found this project useful, consider giving the repository a ⭐.

---

**Machine Learning | Python | Linear Regression | Data Science**
