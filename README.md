# crop_yield_prediction_using_ML
 Machine Learning model to predict crop yields based on climate, soil, and regional data (Telangana)



Project Overview: Agricultural Yield & Revenue Prediction

we are building a machine learning system that:
- Predicts **Kharif yield**, **Rabi yield**, and **Average Market Price** for crops.
- Estimates seasonal **revenue** based on those predictions and user land size.
- Gives **crop recommendations** based on predicted revenue potential.
- Aims to be used via a **user-friendly UI**, especially for educational purposes.

---

  Completed So Far

 1. **Data Preparation**
-  Cleaned agricultural data (crops, yield, market price, etc.).
-  Integrated **weather data** like rainfall and temperature.
-  Finalized **important input features** (e.g., Zone, District, Year, Soil Type, Irrigation, Rainfall, Temperature).
-  Selected 3 output targets:
  - `Kharif_Yield_(Tonne/Hectare)`
  - `Rabi_Yield_(Tonne/Hectare)`
  - `Average_Market_Price`

---

 2. **Feature Encoding**
-  Categorical features were encoded:
  - One-hot encoding (e.g., for Zone, Irrigation)
  - Multi-label or special handling for `Soil_Type`
-  Saved encoded input data into separate CSV files:
  - `final_input_features.csv`
  - `target_kharif_yield.csv`
  - `target_rabi_yield.csv`
  - `target_market_price.csv`

---

### 3. **Model Training**
You trained and saved **2 sets of models** for each output target:

Random Forest Regressors
- Trained and tested models for:
  - Kharif Yield
  - Rabi Yield
  - Market Price

XGBoost Regressors
- Trained on the same targets.
- Saved models for reuse (e.g., `xgb_kharif.pkl`, `xgb_rabi.pkl`, `xgb_price.pkl`)

---

### 4. **Model Evaluation**
- Compared models using:
  - R² Score (Accuracy)
  - RMSE (Error)
- Identified **XGBoost and Random Forest** as top performers.
- Chose to use them for predictions moving forward.

---

Remaining Work / Next Steps

1. Prediction Function for Multiple Crops
- We're building a function that takes user inputs and predicts:
  - Yield, Market Price
  - Revenue for Kharif/Rabi
  - Best crop based on revenue
- This function will use the **saved models** and apply **same encoding** as training.

2. Crop Recommendation Engine
- After predicting for all crops, rank them by `Total Estimated Revenue`.
- Recommend top crops for user-specific inputs (zone, soil, irrigation, etc.).

3. Confidence Levels & Justification
- Add **confidence scores** (from model performance or uncertainty estimation).
- Explain reasoning in simple language (like rainfall influence, soil matching, etc.).

4. Visual + Educational UI
- Build a **front-end interface** (web UI or Jupyter form) to:
  - Accept user inputs
  - Show crop images + predicted results
  - Display graphs, confidence levels, and explanations

---
