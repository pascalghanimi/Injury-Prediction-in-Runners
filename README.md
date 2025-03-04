# Injury-Prediction-in-Runners

## Injury Prediction in Competitive Runners With Machine Learning

### Overview
This project focuses on predicting injuries in athletes using machine learning models. The goal is to compare different boosting algorithms—**XGBoost, LightGBM, and CatBoost**—and evaluate their performance across different feature sets. Additionally, an **ensemble approach** is implemented to combine the strengths of multiple models for improved prediction accuracy.

## Models Implemented

### 1. XGBoost
- Utilized for binary classification.
- Hyperparameter tuning performed with **Optuna**.
- Model trained on various feature subsets.

### 2. LightGBM
- Faster than XGBoost with large datasets.
- Uses histogram-based learning for better efficiency.
- Optimized with **Optuna** to maximize AUC score.

### 3. CatBoost
- Handles categorical features efficiently.
- Uses **Oblivious Trees** for balanced splits.
- Optimized with **Optuna** to maximize AUC score.

## Feature Sets
To analyze model performance, five different feature sets were used:

1. **All Features** – Combination of all feature categories.
2. **Days Features** – Data collected on a daily basis.
3. **Weeks Features** – Aggregated weekly data.
4. **Objective Features** – Metrics derived from measurable performance.
5. **Subjective Features** – Data based on athlete-reported conditions.

## Training and Evaluation

- **Data Handling**: Features and labels are stored as `.pkl` files.
- **Data Splitting**: Standard **train-validation-test** split (70%-15%-15%).
- **Batch Sampling**: Balanced mini-batches created to handle class imbalance (2048 samples in total, 50% injured & 50% healthy event)
- **Performance Metric**: **AUC (Area Under the Curve)** used for evaluation.
- **Ensemble Approach**: Models calibrated using `CalibratedClassifierCV`, then combined via probability averaging.

## Results
### Comparison of Feature Sets for XGBoost
![image](https://github.com/user-attachments/assets/6aa49380-a628-4a3e-9c22-fbcace9e5600)
![image](https://github.com/user-attachments/assets/f3e30661-d617-4292-8a2e-c3f9d6709b4c)



### Comparison of Feature Sets for Light GBM
![image](https://github.com/user-attachments/assets/413ae1f2-3566-4da0-b239-b6e46d8daaca)
![image](https://github.com/user-attachments/assets/9a0ada1c-b0c1-4329-a63b-9b45e9cbccbb)

### Comparison of Feature Sets for CatBoost
![image](https://github.com/user-attachments/assets/836d3e84-7901-4829-af55-2c9950c85dbf)
![image](https://github.com/user-attachments/assets/2bb15d85-c56c-4113-93ae-87b7e4677769)



## Usage

### Running in Google Colab

1. Open the Colab notebook in your browser.
2. Upload the required `.pkl` files containing the dataset.
3. Run the notebook cells to train and evaluate the models.

### Running Locally (Optional)

1. Clone the repository:
   ```bash
   git clone https://github.com/pascalghanimi/Injury-Prediction-in-Runners.git
   cd injury-prediction
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Modify the notebook or create Python scripts for local execution.



## Future Improvements
- **Feature Engineering**: Experiment with additional metrics.
- **Hyperparameter Optimization**: Further fine-tuning with more trials and especially fine-tuning for each individual feature set (e.g. days, weeks, objective and subjective features)
- **Deployment**: Convert the best model into a web-based API for real-time predictions.

---
**Author:** Pascal Ghanimi
**GitHub Repository:** https://github.com/pascalghanimi/Injury-Prediction-in-Runners.git



