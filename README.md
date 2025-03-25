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
- **Performance Metric**:
   - AUC (Area Under the Curve) → Measures how well the model distinguishes between injured and non-injured individuals
   - Recall (Sensitivity) → The proportion of actually injured individuals correctly identified by the model.
   - Precision → The proportion of predicted injured individuals who are actually injured
   - F1-Score → The harmonic mean of Precision and Recall
   - Specificity → The proportion of actually non-injured individuals correctly identified as non-injured by the model.
- **Ensemble Approach**: Models calibrated using `CalibratedClassifierCV`, then combined via probability averaging.

## Results
### Comparison of Feature Sets for XGBoost
<p float="left">
  <img src="https://github.com/user-attachments/assets/a55293a6-6a56-4e3c-9eaa-ecba17f73344" width="300"/>
  <img src="https://github.com/user-attachments/assets/73e88584-1b90-46e5-8f4d-e0436934d915" width="300"/>
  <img src="https://github.com/user-attachments/assets/0c056aee-04f1-47c7-a112-51c5c7ffb103" width="300"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/f0f64f97-7c83-4acb-a2c1-fddc19d4b090" width="300"/>
  <img src="https://github.com/user-attachments/assets/a40b18ce-b4dd-4b36-a051-24fa1e018cdb" width="300"/>
  <img src="https://github.com/user-attachments/assets/0c977844-4c30-4984-8868-0c87291b0726" width="300"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/1c46579d-8525-4934-bdd2-180853034d70" width="300"/>
  <img src="https://github.com/user-attachments/assets/d735d1ce-60a1-4faa-b784-e53db87566d9" width="300"/>
  <img src="https://github.com/user-attachments/assets/1f5cbbef-a224-4eed-b25c-066c515c5077" width="300"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/6bd13ed9-52af-4a10-a238-aba2e33683c2" width="300"/>
  <img src="https://github.com/user-attachments/assets/81024c0d-5d20-4473-b549-aae5ee3a5be4" width="300"/>
  <img src="https://github.com/user-attachments/assets/1b284fdf-2439-4bec-8ad1-3bfd1caa86d0" width="300"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/cec500b2-2f3c-441a-9a51-a6a5561a2c1e" width="300"/>
  <img src="https://github.com/user-attachments/assets/573334a1-f6cf-40c5-ba2c-2de974cf54ff" width="300"/>
  <img src="https://github.com/user-attachments/assets/ba256a2c-6375-403a-916f-ea6bd80fb352" width="300"/>
</p>







### Comparison of Feature Sets for Light GBM
![image](https://github.com/user-attachments/assets/97d309f0-876a-434a-9ed9-cc1215596429)
![image](https://github.com/user-attachments/assets/f8afc667-31a0-49b0-817b-a791db112489)
![image](https://github.com/user-attachments/assets/56e16154-d726-4445-a168-4f826279fa5d)
![image](https://github.com/user-attachments/assets/64f1ba92-dea2-429c-9ca9-942796df7388)
![image](https://github.com/user-attachments/assets/50862c59-ce3e-4107-a4cd-b2517aeef0aa)
![image](https://github.com/user-attachments/assets/89a4cd2a-01bc-42f5-b2a6-8d3d631550b6)
![image](https://github.com/user-attachments/assets/f0161e29-77ae-408b-9e24-6fbe0ec79f0b)
![image](https://github.com/user-attachments/assets/38d56785-0b54-4e8e-aef0-535cd00755ec)
![image](https://github.com/user-attachments/assets/ed7fc479-a340-484c-8243-f3064a820225)
![image](https://github.com/user-attachments/assets/42aadae3-5a35-40c9-8689-d78dc73d45dd)

### Comparison of Feature Sets for CatBoost
![image](https://github.com/user-attachments/assets/836d3e84-7901-4829-af55-2c9950c85dbf)
![image](https://github.com/user-attachments/assets/2bb15d85-c56c-4113-93ae-87b7e4677769)

### Performance of Ensemble Model (ROC Curve)
![image](https://github.com/user-attachments/assets/40796dba-e3b2-449c-9bce-de2a8417f013)



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



