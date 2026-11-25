# 🏠 House Price Prediction using Linear Regression

A supervised machine learning project that predicts house prices from property features (area, bedrooms, bathrooms, amenities, etc.) using **Linear Regression** in Python and scikit-learn. The model is evaluated with **R², MSE, RMSE and MAE**, and its predictions are visualised against actual prices.

> Mini Project 2 · Week 2 – Supervised Learning (Regression)

---

## 📌 Project Overview

| | |
|---|---|
| **Problem type** | Supervised learning – Regression |
| **Target variable** | `price` |
| **Algorithm** | Linear Regression (`sklearn.linear_model.LinearRegression`) |
| **Dataset** | Housing Prices Dataset (Kaggle) – 545 houses, 12 features |
| **Train / test split** | 80% / 20% (`random_state=42`) |
| **Evaluation** | R², MSE, RMSE, MAE, 5-fold cross-validation |

## 📊 Dataset

| Feature | Type | Description |
|---|---|---|
| `price` | numeric | **Target** – house price |
| `area` | numeric | Total area (sq. ft) |
| `bedrooms`, `bathrooms`, `stories` | numeric | Number of bedrooms, bathrooms and floors |
| `parking` | numeric | Number of parking spaces |
| `mainroad` | yes/no | Connected to the main road |
| `guestroom` | yes/no | Has a guest room |
| `basement` | yes/no | Has a basement |
| `hotwaterheating` | yes/no | Has hot-water heating |
| `airconditioning` | yes/no | Has air conditioning |
| `prefarea` | yes/no | Located in a preferred area |
| `furnishingstatus` | categorical | furnished / semi-furnished / unfurnished |

The dataset has **no missing values and no duplicate rows**.

## 🔄 Workflow

1. **Load & inspect** the data
2. **Exploratory Data Analysis** – price distribution, feature vs. price plots, correlation heatmap
3. **Preprocessing** – yes/no columns mapped to 1/0; `furnishingstatus` one-hot encoded (`drop_first=True`)
4. **Train–test split** (80/20)
5. **Train** the Linear Regression model
6. **Predict** prices on unseen test data
7. **Evaluate** with R², MSE, RMSE, MAE
8. **Visualise** predicted vs. actual prices and residuals
9. **Interpret** model coefficients and validate with 5-fold cross-validation

## 📈 Results

| Metric | Train | Test |
|---|---|---|
| **R² Score** | 0.686 | **0.653** |
| RMSE | – | ≈ 1.32 million |
| MAE | – | ≈ 0.97 million |

- The model explains **≈ 65% of the variance** in house prices.
- Train and test scores are close, so the model is **not overfitting**.
- **5-fold cross-validation** (shuffled) gives a mean R² of **0.632 (± 0.074)**, confirming stable performance.
- **Strongest positive drivers of price:** bathrooms, air conditioning, hot-water heating, preferred area and number of stories. Unfurnished houses are priced lower.

### Predicted vs. Actual

![Predicted vs Actual](images/predicted_vs_actual.png)

Points close to the red dashed line are accurate predictions. The model tends to under-predict the most expensive houses.

## 🗂️ Repository Structure

```
├── House_Price_Prediction.ipynb   # Full project notebook (with outputs)
├── Housing.csv                    # Dataset
├── images/
│   └── predicted_vs_actual.png    # Result plot
├── requirements.txt               # Python dependencies
└── README.md
```

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# 2. (Optional) create a virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch the notebook
jupyter notebook House_Price_Prediction.ipynb
```

Then run all cells (**Kernel → Restart & Run All**).

## 🛠️ Tech Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · scikit-learn · Jupyter Notebook

## 🔮 Future Improvements

- Log-transform the target variable to reduce skew
- Add polynomial and interaction features
- Detect and handle outliers
- Try regularised models (Ridge, Lasso)
- Compare with Random Forest and Gradient Boosting

## 🙏 Acknowledgements

Dataset: *Housing Prices Dataset* from [Kaggle](https://www.kaggle.com/).

---

⭐ If you found this project useful, consider giving it a star!
