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
  <img src="https://github.com/user-attachments/assets/a55293a6-6a56-4e3c-9eaa-ecba17f73344" width="400"/>
  <img src="https://github.com/user-attachments/assets/73e88584-1b90-46e5-8f4d-e0436934d915" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/0c056aee-04f1-47c7-a112-51c5c7ffb103" width="400"/>
  <img src="https://github.com/user-attachments/assets/f0f64f97-7c83-4acb-a2c1-fddc19d4b090" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/a40b18ce-b4dd-4b36-a051-24fa1e018cdb" width="400"/>
  <img src="https://github.com/user-attachments/assets/0c977844-4c30-4984-8868-0c87291b0726" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/1c46579d-8525-4934-bdd2-180853034d70" width="400"/>
  <img src="https://github.com/user-attachments/assets/d735d1ce-60a1-4faa-b784-e53db87566d9" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/1f5cbbef-a224-4eed-b25c-066c515c5077" width="400"/>
  <img src="https://github.com/user-attachments/assets/6bd13ed9-52af-4a10-a238-aba2e33683c2" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/81024c0d-5d20-4473-b549-aae5ee3a5be4" width="400"/>
  <img src="https://github.com/user-attachments/assets/1b284fdf-2439-4bec-8ad1-3bfd1caa86d0" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/cec500b2-2f3c-441a-9a51-a6a5561a2c1e" width="400"/>
  <img src="https://github.com/user-attachments/assets/573334a1-f6cf-40c5-ba2c-2de974cf54ff" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/ba256a2c-6375-403a-916f-ea6bd80fb352" width="400"/>
</p>








### Comparison of Feature Sets for Light GBM
### Comparison of Feature Sets for LightGBM

<p float="left">
  <img src="https://github.com/user-attachments/assets/e18f43e0-b4bb-4204-9dde-4da89179b286" width="400"/>
  <img src="https://github.com/user-attachments/assets/04c8870a-da57-481f-a443-b905bc520faa" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/329f80bd-fb55-46d9-9b0f-a8a2c4b844ce" width="400"/>
  <img src="https://github.com/user-attachments/assets/047abfe7-6ff4-4184-ab33-b74ef807d5b7" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/5584cd92-db15-479a-9632-ff3c376bafcf" width="400"/>
  <img src="https://github.com/user-attachments/assets/6b46757c-d227-40c2-96b8-108e1d68b2e2" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/0b7ecddc-0a84-4f5f-85b9-ff92553c41e6" width="400"/>
  <img src="https://github.com/user-attachments/assets/d09db9fd-1c71-4d4b-8f9a-3b113b21492d" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/38d412ed-4766-4a84-b2a4-3ff895b3fee9" width="400"/>
  <img src="https://github.com/user-attachments/assets/43b0a290-fa50-4f97-a756-dc37a787952e" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/7a7101fd-5761-464f-b4eb-c4be13dfff4b" width="400"/>
  <img src="https://github.com/user-attachments/assets/0a5c3866-6b74-4f85-8b04-530346a9f184" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/1abdc871-9ead-4ea1-b4ef-e1eec78ac4a4" width="400"/>
  <img src="https://github.com/user-attachments/assets/b3f10966-017a-4670-8f94-4f30797d9645" width="400"/>
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/efe6b228-ddf9-442b-a7a2-4c096e4f3dda" width="400"/>
</p>




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



