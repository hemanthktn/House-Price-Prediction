# 🏠 House Price Prediction — Data Science Project (EPBL)

A complete, end-to-end data science project that predicts house sale prices from structural, locational, and quality features, and identifies the key drivers of price. Built as an EPBL (Experiential/Project-Based Learning) certification project.

## 📌 Problem Statement

Given details about a house (area, bedrooms, location, age, amenities, condition, etc.), predict its market **sale price**. This is framed as a **supervised regression** problem, with the secondary goal of interpreting *which* features most influence price so the insights can support real business decisions (pricing, renovation advice, targeting).

## 📂 Project Structure

```
.
├── House_Price_Prediction_EPBL_Project.ipynb   # Main notebook (fully executed, with outputs/plots)
├── house_prices.csv                            # Dataset used (2,000 records, synthetic but realistic)
├── best_house_price_model.pkl                  # Trained best-performing model (saved with joblib)
├── requirements.txt                            # Python dependencies
└── README.md                                   # Project documentation (this file)
```

## 🗂️ Dataset

The notebook generates a **realistic synthetic housing dataset** (2,000 rows) so it runs fully offline and reproducibly, with no external download step. It mimics the structure of real-world datasets like the Ames Housing dataset or Kaggle's House Prices dataset.

**Features:**
| Feature | Description |
|---|---|
| `area_sqft` | Living area in square feet |
| `bedrooms`, `bathrooms`, `stories` | Structural counts |
| `garage_spaces` | Number of garage spaces |
| `age_years` | Age of the house |
| `distance_to_city_km` | Distance from city center |
| `school_rating` | Nearby school rating (1–10) |
| `crime_rate` | Local crime index (0–10, higher = worse) |
| `location` | Urban / Suburban / Rural |
| `condition` | Poor / Fair / Good / Excellent |
| `has_pool`, `has_garden` | Amenity flags |
| `price` | **Target** — sale price (USD) |

> 💡 To use a real dataset instead, replace the data-generation cell with `pd.read_csv("your_file.csv")`, keeping the same column names (or adjusting `feature_cols` accordingly).

## 🔬 Project Pipeline

1. **Problem Definition** — framing the regression task and business goal
2. **Data Generation/Loading** — synthetic dataset creation
3. **Data Cleaning** — missing value imputation, duplicate checks
4. **Exploratory Data Analysis (EDA)** — distribution plots, scatter plots, boxplots by category, correlation heatmap
5. **Feature Engineering** — derived features (`price_per_sqft`, `age_group`) for insight; categorical encoding for modeling
6. **Model Building** — Linear Regression, Ridge Regression, Random Forest, XGBoost
7. **Model Evaluation** — MAE, RMSE, R² comparison across models
8. **Feature Importance** — interpreting which features drive price
9. **Conclusions & Business Recommendations**

## 🛠️ Tools & Libraries

- **Language:** Python 3
- **Environment:** Jupyter Notebook
- **Data handling:** pandas, numpy
- **Visualization:** matplotlib, seaborn
- **Modeling:** scikit-learn (Linear Regression, Ridge, Random Forest), XGBoost
- **Model persistence:** joblib

## 📊 Results (Summary)

Tree-based ensemble models (Random Forest, XGBoost) outperformed linear models, indicating non-linear relationships and feature interactions matter for pricing. `area_sqft`, `location`, `condition`, and `age_years` emerged as the strongest price drivers. Full metrics and comparison charts are in the notebook (Sections 9–11).

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-folder>
   ```
2. (Recommended) Create a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook House_Price_Prediction_EPBL_Project.ipynb
   ```
5. Run all cells (`Kernel > Restart & Run All`).

## 🚀 Future Improvements

- Validate on a real-world dataset (Ames Housing / Kaggle House Prices)
- Hyperparameter tuning via GridSearchCV / RandomizedSearchCV with cross-validation
- Add SHAP values for row-level model explainability
- Deploy as a Streamlit app for interactive price estimation

## 📄 License

This project is open for educational and certification purposes.
