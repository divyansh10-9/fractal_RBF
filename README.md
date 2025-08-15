# Fractal RBF Neural Network for Ground Water Level Prediction

## 📌 Overview
This project demonstrates the prediction of **groundwater levels** using:
1. A **Traditional Gaussian RBF Neural Network**
2. A **Fractalized RBF Neural Network** (proposed variant)

The fractalized RBF kernel is designed to enhance the feature mapping by incorporating a **fractal interpolation function**, leading to **lower prediction error** compared to the standard Gaussian RBF.

---

## 📊 Dataset
The dataset used contains:
- **Data Time**: Date of groundwater measurement
- **Data Value**: Groundwater level in meters

The raw file (`Ground Water Level_Wasahermenpet.xlsx`) was downloaded from the **India-WRIS** portal.

---

## 🛠 Steps in the Pipeline
1. **Data Cleaning**
   - Removal of irrelevant columns
   - Handling missing values
   - Date parsing & type conversion
2. **Outlier Handling**
   - Used Interquartile Range (IQR) filtering
3. **Feature Engineering**
   - Created rolling window sequences for time series forecasting
4. **Data Scaling**
   - Standardized using `StandardScaler`
5. **Model Implementation**
   - **Traditional Gaussian RBF Network** (custom implementation)
   - **Fractalized RBF Network** using a fractal function `phi_alpha`
6. **Evaluation**
   - Mean Squared Error (MSE) comparison

---

## 📐 Model Details

### Traditional Gaussian RBF Network
- Hidden layer: **RBF neurons** with Gaussian kernel  
- Parameters:
  - Neurons: `96`
  - Gamma: `0.5`
  - Learning Rate: `0.2`
  - Epochs: `200`

### Fractalized RBF Network
- Same architecture as Gaussian RBF  
- Replaces the Gaussian kernel with **fractal-interpolated kernel**:
 
## 📈 Results

| Model Type               | Test MSE |
|--------------------------|----------|
| Traditional Gaussian RBF | **0.1140** |
| Fractalized RBF          | **0.0997** |

**✅ Error Reduction:**  
The fractalized RBF reduced the Mean Squared Error by: approx 12.54



---

## 🚀 How to Run
Install dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn scipy openpyxl