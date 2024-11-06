# Breast Cancer Prediction Model

This project implements a **Breast Cancer Prediction Model** that classifies whether breast cancer is **Malignant** or **Benign**. The model was trained on a dataset containing various features related to cell nuclei characteristics, using feature scaling and label encoding to improve performance and accuracy.

---

## Dataset Overview

The dataset contains several key measurements of cell nuclei features extracted from breast cancer biopsies. The target variable `diagnosis` indicates the type of cancer:
- **M** for Malignant
- **B** for Benign

Only relevant features were used, and `diagnosis` was label-encoded as follows:
- **1** for Malignant
- **0** for Benign

### Example of Dataset Structure:
| ID     | Diagnosis | Radius Mean | Texture Mean | Perimeter Mean | Area Mean | Smoothness Mean | ... |
|--------|-----------|-------------|--------------|----------------|-----------|-----------------|-----|
| 842302 | M         | 17.99       | 10.38       | 122.8         | 1001      | 0.1184          | ... |

---

## Preprocessing Steps

1. **Label Encoding**: Transformed the `diagnosis` column into numerical values (1 for Malignant, 0 for Benign).
2. **Feature Scaling**: Scaled all feature columns to a standardized range to ensure uniformity and improve the model's performance.

---

## Model Usage

This model can predict if a breast cancer diagnosis is Malignant or Benign based on input features related to cell nuclei. To use the model, enter a set of measurements as input, and the model will output the prediction.

### Example Code:

```python
import numpy as np

# Sample input data
input_data = [17.99,10.38,122.8,1001,0.1184,0.2776,0.3001,0.1471,0.2419,0.07871,1.095,0.9053,
              8.589,153.4,0.006399,0.04904,0.05373,0.01587,0.03003,0.006193,25.38,17.33,184.6,
              2019,0.1622,0.6656,0.7119,0.2654,0.4601,0.1189]

# Convert input to numpy array
data_as_array = np.asarray(input_data)

# Reshape data to match the model's expected input shape
data_reshaped = data_as_array.reshape(1, -1)

# Scale input data
data_reshaped = scaler.transform(data_reshaped)

# Make prediction
prediction = model.predict(data_reshaped)

# Interpret prediction
if prediction == 1:
    print('The breast cancer is Malignant')
else:
    print('The breast cancer is Benign')
```
