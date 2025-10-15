# 🌍 Global Weather Analysis & Temperature Forecasting

### **Project Overview**
This project performs an **Exploratory Data Analysis (EDA)** and builds a **time series forecasting model** for global temperature prediction using a comprehensive weather dataset. It further explores **ensemble modeling techniques** and analyzes **regional climate variations** across multiple countries.

---

## 🔍 Exploratory Data Analysis (EDA)

**Key Steps:**
- Loaded dataset: `GlobalWeatherRepository.csv`  
- Verified data completeness — no missing values found.  
- Detected and capped outliers in numerical columns (temperature, precipitation, visibility, air quality metrics) using the **IQR method**.  
- Applied **MinMaxScaler** for feature normalization.  
- Visualized distributions of temperature and precipitation metrics using histograms and scatter plots.  
- Identified weak negative correlation between temperature and precipitation.  
- Conducted time series trend analysis for daily mean temperature and precipitation.

**Insights:**  
- Temperature data followed a roughly normal distribution after scaling.  
- Precipitation data was highly skewed toward zero, indicating frequent dry conditions.  
- Seasonal fluctuations in both temperature and precipitation were evident.

---

## 🤖 Model Building: XGBoost Temperature Forecast

**Process:**
- Extracted **time-based features** (year, month, day, hour) from timestamps.  
- Split dataset chronologically (80% train, 20% test).  
- Trained an **XGBoost regressor** to predict `temperature_celsius`.  

**Model Performance:**
- **MSE:** 0.027  
- **RMSE:** 0.165  
- **MAE:** 0.127  

**Results:**  
The model showed strong predictive accuracy with tight alignment between predicted and actual temperature values.

---

## 🧠 Advanced Assessment: Ensemble Modeling

To improve forecasting accuracy, multiple models were compared and combined:

**Individual Models**
| Model | MSE | RMSE | MAE |
|-------|------|------|------|
| Linear Regression | 0.0379 | 0.1948 | 0.1630 |
| Random Forest | 0.0299 | 0.1728 | 0.1345 |
| ARIMA | 0.0369 | 0.1921 | 0.1448 |
| Prophet | 0.0462 | 0.2151 | 0.1653 |

**Ensemble Model (Averaged Predictions):**
- **MSE:** 0.0284  
- **RMSE:** 0.1684  
- **MAE:** 0.1370  

**Conclusion:**  
The ensemble model outperformed all individual models in MSE and RMSE, confirming the benefit of combining multiple algorithms for time series forecasting.

---

## 🌎 Regional Climate Variation Analysis

**Regions Studied:** United States, India, China, Brazil, Germany  

**Approach:**
- Aggregated mean temperature and precipitation by **country** and **month**.  
- Generated **line plots** to visualize long-term trends and seasonal differences.  

**Findings:**  
- Each country exhibited distinct seasonal cycles and variability.  
- Regional comparison highlighted significant contrasts in precipitation intensity and temperature fluctuation patterns.

---

## 📈 Key Takeaways

✅ Data successfully cleaned, preprocessed, and visualized.  
✅ Developed and evaluated both **XGBoost** and **ensemble models** for accurate temperature prediction.  
✅ Ensemble modeling demonstrated superior forecasting accuracy.  
✅ Regional analysis revealed clear climate variations across countries.

---

## 🚀 Next Steps

- Explore **weighted or stacked ensembles** for enhanced performance.  
- Incorporate **seasonal and external climate indices** into future models.  
- Conduct deeper **statistical analysis** on regional climate differences.  
- Extend forecasting to **precipitation and other climate variables**.

---

## 🧰 Tech Stack
- **Languages:** Python  
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost, Statsmodels, Prophet  
- **Environment:** Jupyter Notebook  

---
