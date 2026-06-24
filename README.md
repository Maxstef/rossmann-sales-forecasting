# 🏪 Rossmann Sales Forecasting Project

## 1. Problem Description

The goal of this project is to **predict daily sales for Rossmann stores** based on historical sales data and store-specific features.  

Accurate sales forecasting enables Rossmann to:
- 🧾 **Plan inventory** more effectively  
- 👥 **Optimize staffing and logistics**  
- 🎯 **Manage promotions and campaigns** strategically  
- 📉 **Reduce overstock and understock situations**  

By forecasting sales, the project aims to **improve operational efficiency**, **support data-driven decision-making**, and **maximize revenue potential**.

---

## 2. Dataset

This project uses the **Rossmann Store Sales** dataset from Kaggle, with several additional engineered features used for modeling and Streamlit visualization.

- 📦 **Kaggle dataset:** [Rossmann Store Sales on Kaggle](https://www.kaggle.com/c/rossmann-store-sales/data)  
- 🧮 **Preprocessed dataset:** [Rossmann Store Sales (Google Drive)](https://drive.google.com/file/d/1l5ofh6iX6yWtnltgS7nGdH_qks_6O0wA/view?usp=drive_link)

The preprocessed dataset includes:
- Date-based features (`Year`, `Month`, `WeekOfYear`, `IsWeekend`, etc.)
- Competition-related features (`CompetitionDistanceCategory`, `CompetitionMonthsOpen`, etc.)
- Promotion-related features (`Promo2Weeks`, `IsPromoMonth`, etc.)
- Historycal related features (`Sales_Lag1`, `Sales_Lag7`, `Customers_Lag1`, etc.)

---

## 3. Results

Explore the full exploratory data analysis (EDA), data preparation, and modeling workflow here:  
📓 [Rossmann Sales Project Notebook](https://github.com/Maxstef/rossmann-sales-forecasting/blob/main/notebooks/Rossmann_sales_project.ipynb)

Final trained models and preprocessing pipelines are stored under the `/models` directory.  
A fully interactive Streamlit app is deployed here:  
🌐 [Rossmann Sales Forecasting App](https://rossmann-sales-forecasting-app.streamlit.app/)

---

## 4. Run Instructions

### ▶️ Running the Streamlit App Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/Maxstef/rossmann-sales-forecasting.git
   cd rossmann-sales-forecasting
   ```

2. **Create a virtual environment** (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate   # on Windows `venv\Scripts\activate`
   ```
3. **Install packages**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run streamlit app**
   ```bash
    streamlit run app.py
    ```
Once launched, the app will be available at: 👉 `http://localhost:8501`.

### 🧠 Training a New Model

1. Open `notebooks/Train_model.ipynb`
2. Upload the data file to the appropriate folder (`data/raw/rossman_prepared.csv` by default)
3. (Optional) Modify:
   - `filename_to_save` — change the name for the saved model  
   - Model type or hyperparameters  
   - Data preparation parameters in `prepare_data()`  
4. Run all cells in the notebook  
5. The trained model will be saved under the `models/` directory

---

### 🧩 Generating Streamlit Data Files

If you want to update the Streamlit app (e.g., to modify user input fields or refresh summary statistics):

1. Open `notebooks/Streamlit_data_creation.ipynb`
2. Upload your dataset (`data/raw/rossman_prepared.csv`)
3. (Optional) Modify:
   - `statistic_setups` variable (controls summary statistics generation)  
   - `user_inpute_cols` variable (controls form inputs for prediction)  
4. Run all notebook cells  
5. The new data files will be generated in the `data/streamlit/` directory

---

## 5. Conclusions

The Rossmann Sales Forecasting project demonstrates how **machine learning** and **feature engineering** can provide tangible business value in the retail domain.

### ✅ Key Insights:
- The models successfully capture **seasonal patterns**, **promotional impact**, and **competition effects**.  
- Models like **DecisionTreeRegressor** and **RandomForestRegressor** deliver significantly better accuracy than linear regression.  
- Engineered features — such as `WeekOfYear`, `CompetitionDistanceCategory`, `Sales_Lag1`, etc — strongly improve predictive performance.

---

## 6. Future Improvements

Potential directions for extending and improving this project include:

- 🧩 **Improved Field Dependencies**
  - Automatically link `PromoInterval`, `Promo2SinceWeek`, and `Promo2SinceYear` to the `Promo2` field.  
  - Make `CompetitionOpenSinceMonth`, `CompetitionOpenSinceYear`, and `CompetitionDistance` conditional and optional.  
  - Merge `Promo2SinceWeek` + `Promo2SinceYear` into a single date-based input field.

- 🎨 **Enhanced Streamlit UI/UX**
  - Add dynamic visualizations and richer feedback (charts, color indicators).  
  - Organize fields more intuitively, improve layout responsiveness.

- 🧠 **Feature Engineering**
  - Improve handling of `DaysBeforeHoliday`, `DaysAfterHoliday` features
  - Incorporate new features like weather data, or local event data.  
  - Explore trend decomposition or feature selection to improve generalization.

- 📅 **Extended Forecasting**
  - Enable prediction for custom time periods — weekly, monthly, or multi-store forecasts.  
  - Add batch prediction capability for planning and simulations.

---

💡 **Author:** [Maksym Stefanko](https://github.com/Maxstef)  
📂 **Repository:** [Rossmann Sales Project](https://github.com/Maxstef/rossmann-sales-forecasting)
