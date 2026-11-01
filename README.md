# 🌬️ Wind Power Forecasting & Active Power Prediction

An end-to-end Machine Learning system that predicts active wind turbine power output from SCADA operational telemetry (wind speed, rotor RPM, reactive power, blade pitch angle, etc.) paired with an interactive **Streamlit** web application for real-time inference and historical analytics.

---

## 📌 Project Overview
Accurate forecasting of wind power generation is critical for modern power grid stability, energy trading, and maintenance planning. This project uses real-world turbine sensor data to evaluate multiple regression algorithms and identify the highest-accuracy model for power output prediction.

### 🌟 Key Features
- **Data Preprocessing & Cleaning**:
  - Handles missing values using forward and backward imputation.
  - Detects and removes sensor outliers via the Interquartile Range (IQR) technique.
  - Multi-feature normalization and scaling.
- **Multi-Model Benchmarking**:
  - Compares 6 regression architectures: Linear Regression, Ridge, Lasso, Decision Trees, Gradient Boosting, and K-Nearest Neighbors (KNN).
  - Evaluates models on Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and $R^2$ Score.
  - Selected **KNN Regressor** as the top-performing model with an **$R^2$ score of 0.9922**.
- **Interactive Streamlit Web Dashboard**:
  - User authentication (login & registration).
  - Single-point interactive prediction interface with input sliders and fields.
  - Real-time power output calculation and operational status alerts.
  - History log tracking for historical predictions.

---

## 📊 Model Performance Comparison

| Model | MAE | MSE | $R^2$ Score |
| :--- | :---: | :---: | :---: |
| **K-Nearest Neighbors (KNN)** 🏆 | **16.13** | **3,052.21** | **0.9922** |
| Decision Tree | 16.58 | 3,150.73 | 0.9919 |
| Gradient Boosting | 31.59 | 3,708.74 | 0.9905 |
| Ridge Regression | 137.38 | 35,972.52 | 0.9077 |
| Linear Regression | 137.38 | 35,972.68 | 0.9077 |
| Lasso Regression | 142.16 | 36,689.08 | 0.9058 |

---

## 🗂️ Project Structure

```text
├── app.py                         # Streamlit interactive web application
├── model training.py             # Model training, validation & serialization pipeline
├── wind power.ipynb              # Exploratory Data Analysis (EDA) & experimentation notebook
├── best_knn_model.pkl            # Pre-trained KNN model serialized with Joblib
├── model_comparison_report.csv   # Benchmark results of all tested models
├── Wind_Power_Forecasting_PPT.key# Project presentation slides
├── requirements.txt              # Project Python dependencies
├── users.example.json            # Example credential template for authentication
└── README.md                     # Documentation
```

---

## 🚀 Getting Started

### 1. Prerequisites
Ensure you have **Python 3.9+** installed on your system.

### 2. Clone the Repository
```bash
git clone https://github.com/Yashu0809/wind-power-forecasting.git
cd wind-power-forecasting
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Setup Authentication (Optional)
Copy `users.example.json` to `users.json`:
```bash
cp users.example.json users.json
```
*(Or create a new account directly from the app interface).*

### 5. Run the Streamlit Application
```bash
streamlit run app.py
```
Open your browser at `http://localhost:8501`.

---

## 🛠️ Tech Stack
- **Language**: Python
- **Machine Learning**: Scikit-Learn, Joblib, NumPy, Pandas
- **Visualization**: Matplotlib, Seaborn, Plotly
- **Web Interface**: Streamlit, Streamlit Option Menu

---

## 👤 Author
**Yashwanth Jillella**
- GitHub: [@Yashu0809](https://github.com/Yashu0809)
