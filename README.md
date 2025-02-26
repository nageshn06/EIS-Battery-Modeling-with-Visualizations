# EIS Battery Modeling with Visualizations

## Project Overview
This mini-project focuses on analyzing Li-ion battery aging using Electrochemical Impedance Spectroscopy (EIS) data. The dataset consists of multiple charge/discharge cycle readings and impedance measurements at different operational conditions. The goal is to visualize aging effects, extract key insights, and train a machine learning model to predict battery capacity from EIS signatures.

---

## Dataset Link
The dataset used in this project can be downloaded from Kaggle:  
[**NASA Battery Dataset**](https://www.kaggle.com/datasets/patrickfleith/nasa-battery-dataset/data)

---

## Folder Structure

```
EIS-Battery-Modeling/
│── cleaned_dataset/
│   ├── data           
│   ├── extra_infos
│   ├── metadata.csv
│── notebook/ 
│   ├── Battery-Analysis.ipynb   
│   ├── gradient_boosting_model.pkl  
│── README.txt
```

---

## Dataset Description
A set of Li-ion batteries were run through different operational profiles (charge, discharge, and impedance) at various temperatures. Impedance measurements were carried out using electrochemical impedance spectroscopy (EIS) across different frequencies.

Repeated charge and discharge cycles result in accelerated aging of the batteries, while impedance measurements provide insight into the internal battery parameters that change as aging progresses. The experiments were stopped when the batteries reached end-of-life (EOL) criteria.

These datasets can be used for predicting both:
1. **Remaining charge** (for a given discharge cycle).
2. **Remaining useful life (RUL)** of the battery.

Data are provided in batches of six experiments, stored in CSV or MAT files, with experiment details in an associated `README.txt`.

---

## Implemented Tasks

### 1) 3D Plot for EIS Measurements vs. Aging
- Extract impedance values from EIS measurements.
- Create a 3D visualization where:
  - **X-axis**: Real part of Impedance (R(Z))
  - **Y-axis**: Imaginary part of Impedance (Im(Z))
  - **Z-axis**: Cycle count (Aging indicator)

### 2) Incremental Capacity Analysis (ICA)
Generate two plots:
- **Plot a)** Standard charge/discharge cycle data.
- **Plot b)** Incremental Capacity Analysis (ICA), showing **dQ/dV vs. Voltage**.

ICA helps analyze how the rate of capacity increment changes with respect to voltage as the battery charges or discharges.

#### 2.1) 3D Plot for ICA Peaks vs. Aging
Visualize how ICA peaks shift over cycle life:
- **X-axis**: Voltage (V)
- **Y-axis**: dQ/dV
- **Z-axis**: Cycle count (Aging progression)

### 3) Machine Learning Model for Battery Capacity Prediction
Train a model using EIS data to predict the current capacity of the battery cell.

**Features used may include:**
- Impedance values (**R(Z), Im(Z)**)
- Cycle count
- Other battery characteristics

**Possible models:**
- Random Forest
- Support Vector Machine (SVM)
- Neural Networks

---

## How to Run the Notebook

1. Install dependencies:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn
   ```
2. Load the dataset files into the working directory.
3. Run the Jupyter Notebook (`Battery-Analysis.ipynb`) step by step to visualize results and train models.

---

## Future Enhancements
- Optimize the machine learning model for better predictions.
- Extend the analysis to different battery chemistries.
- Automate data preprocessing for scalability.
