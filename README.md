# Injury-Prediction-in-Runners

## Injury Prediction in Competitive Runners With Machine Learning

### Overview
This project focuses on predicting injuries in athletes using machine learning models. The goal is to compare different boosting algorithms—**XGBoost, LightGBM, and CatBoost**—and evaluate their performance across different feature sets. Additionally, an **ensemble approach** is implemented to combine the strengths of multiple models for improved prediction accuracy.

### Purpose
To build on previous work in injury prediction, this project aimed not only to replicate but also to improve existing models by systematically comparing different boosting algorithms and feature sets. Special attention was given to evaluating the predictive value of subjective (self-reported) versus objective (measured) training features, as well as exploring how different temporal resolutions (daily vs. weekly data) affect model performance.


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

1. **All Features** – Combination of all feature categories (139 Features in Total)
2. **Days Features** – Data collected on a daily basis (70 Features in Total)
3. **Weeks Features** – Aggregated weekly data (69 Features in Total)
4. **Objective Features** – Metrics derived from measurable performance (91 Features in Total)
5. **Subjective Features** – Data based on athlete-reported conditions (48 Features in Total)

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
<p float="left">
  <img src="https://github.com/user-attachments/assets/dca17c69-5991-4c94-be36-898a685da34d" width="400"/>
  <img src="https://github.com/user-attachments/assets/67ef225f-872a-405d-a0f1-170a7e9fc421" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/a64daae9-d791-4249-b645-12a61580b8e7" width="400"/>
  <img src="https://github.com/user-attachments/assets/9d6819dd-213f-4ffa-baac-056a02f644e5" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/9e57b62b-c895-43fa-b831-0d05fda84a4e" width="400"/>
  <img src="https://github.com/user-attachments/assets/f7de8351-2c3e-43e2-a2b5-14d9e7abb0ff" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/2a0271bf-dae2-48c9-936d-2a03b8e85a3b" width="400"/>
  <img src="https://github.com/user-attachments/assets/7061e1c4-ba35-4016-99af-bc6c93da6778" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/bb2da64d-ee65-41e3-8531-f3a5a1782679" width="400"/>
  <img src="https://github.com/user-attachments/assets/fa120276-3f1e-426c-b186-da8e3adbc215" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/2f6c61af-b4fa-4924-bcd5-f775f1ccf12c" width="400"/>
  <img src="https://github.com/user-attachments/assets/7dd50212-e7f3-4c4e-b9a8-0cfe5406d6ec" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/d02d95f1-c17c-45dc-bdc7-620dcb713912" width="400"/>
  <img src="https://github.com/user-attachments/assets/046bdf0a-81a0-4b6f-96b7-256c2f663a1c" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/2adcd6aa-f539-4039-b8b3-3498cdd033bb" width="400"/>
</p>




### Comparison of Feature Sets for Ensemble Models
<p float="left">
  <img src="https://github.com/user-attachments/assets/c232b4a5-27a4-43ee-bc17-2c24f890b653" width="400"/>
  <img src="https://github.com/user-attachments/assets/f43f6ccf-986d-40a2-89ff-7c327a1a5b9e" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/075c69de-0e54-43d5-8ba9-140702d58084" width="400"/>
  <img src="https://github.com/user-attachments/assets/6d300ffd-437e-408e-a2d6-e7e15ba1ab1e" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/cac35d22-0edb-4700-9f25-c3c75b5ac391" width="400"/>
  <img src="https://github.com/user-attachments/assets/90bdf409-b105-4772-b9c4-375352202c54" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/1af7824b-30a3-408a-ab90-70a7bd6b26fe" width="400"/>
  <img src="https://github.com/user-attachments/assets/e066f33f-b961-40cb-91f8-8dd6aabfdf07" width="400"/>
</p>
<p float="left">
  <img src="https://github.com/user-attachments/assets/6f204724-cf7b-40ae-856d-198185dccc78" width="400"/>
  <img src="https://github.com/user-attachments/assets/2191c43f-08db-4b53-9430-212830d4aa7e" width="400"/>
</p>




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

## Feature Lists
For the analysis, all available features were grouped into five distinct feature sets: All Features, Days, Weeks, Objective, and Subjective. This structure allows for a targeted evaluation of different data dimensions. While All Features includes the complete set of variables, the remaining subsets focus on specific aspects such as daily or weekly metrics, purely objective training data, or subjective athlete self-assessments.

1. **All Features** – 'nr. sessions_day', 'total km', 'km Z3-4', 'km Z5-T1-T2', 'km sprinting', 'strength training',
'hours alternative', 'perceived exertion', 'perceived trainingSuccess', 'perceived recovery',
'nr. sessions.1_day', 'total km.1', 'km Z3-4.1', 'km Z5-T1-T2.1', 'km sprinting.1', 'strength training.1',
'hours alternative.1', 'perceived exertion.1', 'perceived trainingSuccess.1', 'perceived recovery.1',
'nr. sessions.2_day', 'total km.2', 'km Z3-4.2', 'km Z5-T1-T2.2', 'km sprinting.2', 'strength training.2',
'hours alternative.2', 'perceived exertion.2', 'perceived trainingSuccess.2', 'perceived recovery.2',
'nr. sessions.3', 'total km.3', 'km Z3-4.3', 'km Z5-T1-T2.3', 'km sprinting.3', 'strength training.3',
'hours alternative.3', 'perceived exertion.3', 'perceived trainingSuccess.3', 'perceived recovery.3',
'nr. sessions.4', 'total km.4', 'km Z3-4.4', 'km Z5-T1-T2.4', 'km sprinting.4', 'strength training.4',
'hours alternative.4', 'perceived exertion.4', 'perceived trainingSuccess.4', 'perceived recovery.4',
'nr. sessions.5', 'total km.5', 'km Z3-4.5', 'km Z5-T1-T2.5', 'km sprinting.5', 'strength training.5',
'hours alternative.5', 'perceived exertion.5', 'perceived trainingSuccess.5', 'perceived recovery.5',
'nr. sessions.6', 'total km.6', 'km Z3-4.6', 'km Z5-T1-T2.6', 'km sprinting.6', 'strength training.6',
'hours alternative.6', 'perceived exertion.6', 'perceived trainingSuccess.6', 'perceived recovery.6',
'nr. sessions_week', 'nr. rest days', 'total kms', 'max km one day', 'total km Z3-Z4-Z5-T1-T2',
'nr. tough sessions (effort in Z5, T1 or T2)', 'nr. days with interval session', 'total km Z3-4', 'max km Z3-4 one day',
'total km Z5-T1-T2', 'max km Z5-T1-T2 one day', 'total hours alternative training', 'nr. strength trainings', 'avg exertion',
'min exertion', 'max exertion', 'avg training success', 'min training success', 'max training success',
'avg recovery', 'min recovery', 'max recovery', 'nr. sessions.1_week', 'nr. rest days.1',
'total kms.1', 'max km one day.1', 'total km Z3-Z4-Z5-T1-T2.1', 'nr. tough sessions (effort in Z5, T1 or T2).1',
'nr. days with interval session.1', 'total km Z3-4.1', 'max km Z3-4 one day.1', 'total km Z5-T1-T2.1',
'max km Z5-T1-T2 one day.1', 'total hours alternative training.1', 'nr. strength trainings.1',
'avg exertion.1', 'min exertion.1', 'max exertion.1', 'avg training success.1', 'min training success.1',
'max training success.1', 'avg recovery.1', 'min recovery.1', 'max recovery.1', 'nr. sessions.2_week',
'nr. rest days.2', 'total kms.2', 'max km one day.2', 'total km Z3-Z4-Z5-T1-T2.2', 'nr. tough sessions (effort in Z5, T1 or T2).2',
'nr. days with interval session.2','total km Z3-4.2','max km Z3-4 one day.2', 'total km Z5-T1-T2.2',
'max km Z5-T1-T2 one day.2', 'total hours alternative training.2', 'nr. strength trainings.2', 'avg exertion.2',
'min exertion.2', 'max exertion.2','avg training success.2','min training success.2', 'max training success.2',
'avg recovery.2', 'min recovery.2', 'max recovery.2', 'rel total kms week 0_1',
'rel total kms week 0_2', 'rel total kms week 1_2'
2. **Days Features** – 'nr. sessions_day', 'total km', 'km Z3-4', 'km Z5-T1-T2', 'km sprinting', 'strength training',
'hours alternative', 'perceived exertion', 'perceived trainingSuccess', 'perceived recovery',
'nr. sessions.1_day', 'total km.1', 'km Z3-4.1', 'km Z5-T1-T2.1', 'km sprinting.1', 'strength training.1',
'hours alternative.1', 'perceived exertion.1', 'perceived trainingSuccess.1', 'perceived recovery.1',
'nr. sessions.2_day', 'total km.2', 'km Z3-4.2', 'km Z5-T1-T2.2', 'km sprinting.2', 'strength training.2',
'hours alternative.2', 'perceived exertion.2', 'perceived trainingSuccess.2', 'perceived recovery.2',
'nr. sessions.3', 'total km.3', 'km Z3-4.3', 'km Z5-T1-T2.3', 'km sprinting.3', 'strength training.3',
'hours alternative.3', 'perceived exertion.3', 'perceived trainingSuccess.3', 'perceived recovery.3',
'nr. sessions.4', 'total km.4', 'km Z3-4.4', 'km Z5-T1-T2.4', 'km sprinting.4', 'strength training.4',
'hours alternative.4', 'perceived exertion.4', 'perceived trainingSuccess.4', 'perceived recovery.4',
'nr. sessions.5', 'total km.5', 'km Z3-4.5', 'km Z5-T1-T2.5', 'km sprinting.5', 'strength training.5',
'hours alternative.5', 'perceived exertion.5', 'perceived trainingSuccess.5', 'perceived recovery.5',
'nr. sessions.6', 'total km.6', 'km Z3-4.6', 'km Z5-T1-T2.6', 'km sprinting.6', 'strength training.6',
'hours alternative.6', 'perceived exertion.6', 'perceived trainingSuccess.6', 'perceived recovery.6',
3. **Weeks Features** – 'nr. sessions_week', 'nr. rest days', 'total kms', 'max km one day', 'total km Z3-Z4-Z5-T1-T2',
'nr. tough sessions (effort in Z5, T1 or T2)', 'nr. days with interval session', 'total km Z3-4', 'max km Z3-4 one day',
'total km Z5-T1-T2', 'max km Z5-T1-T2 one day', 'total hours alternative training', 'nr. strength trainings', 'avg exertion',
'min exertion', 'max exertion', 'avg training success', 'min training success', 'max training success',
'avg recovery', 'min recovery', 'max recovery', 'nr. sessions.1_week', 'nr. rest days.1',
'total kms.1', 'max km one day.1', 'total km Z3-Z4-Z5-T1-T2.1', 'nr. tough sessions (effort in Z5, T1 or T2).1',
'nr. days with interval session.1', 'total km Z3-4.1', 'max km Z3-4 one day.1', 'total km Z5-T1-T2.1',
'max km Z5-T1-T2 one day.1', 'total hours alternative training.1', 'nr. strength trainings.1',
'avg exertion.1', 'min exertion.1', 'max exertion.1', 'avg training success.1', 'min training success.1',
'max training success.1', 'avg recovery.1', 'min recovery.1', 'max recovery.1', 'nr. sessions.2_week',
'nr. rest days.2', 'total kms.2', 'max km one day.2', 'total km Z3-Z4-Z5-T1-T2.2', 'nr. tough sessions (effort in Z5, T1 or T2).2',
'nr. days with interval session.2','total km Z3-4.2','max km Z3-4 one day.2', 'total km Z5-T1-T2.2',
'max km Z5-T1-T2 one day.2', 'total hours alternative training.2', 'nr. strength trainings.2', 'avg exertion.2',
'min exertion.2', 'max exertion.2','avg training success.2','min training success.2', 'max training success.2',
'avg recovery.2', 'min recovery.2', 'max recovery.2', 'rel total kms week 0_1',
'rel total kms week 0_2', 'rel total kms week 1_2'
4. **Objective Features** – 'nr. sessions_day', 'total km', 'km Z3-4', 'km Z5-T1-T2', 'km sprinting', 'strength training',
'hours alternative', 'nr. sessions.1_day', 'total km.1', 'km Z3-4.1', 'km Z5-T1-T2.1', 'km sprinting.1', 'strength training.1',
'hours alternative.1', 'nr. sessions.2_day', 'total km.2', 'km Z3-4.2', 'km Z5-T1-T2.2', 'km sprinting.2', 'strength training.2',
'hours alternative.2', 'nr. sessions.3', 'total km.3', 'km Z3-4.3', 'km Z5-T1-T2.3', 'km sprinting.3', 'strength training.3',
'hours alternative.3', 'nr. sessions.4', 'total km.4', 'km Z3-4.4', 'km Z5-T1-T2.4', 'km sprinting.4', 'strength training.4',
'hours alternative.4', 'nr. sessions.5', 'total km.5', 'km Z3-4.5', 'km Z5-T1-T2.5', 'km sprinting.5', 'strength training.5',
'hours alternative.5', 'nr. sessions.6', 'total km.6', 'km Z3-4.6', 'km Z5-T1-T2.6', 'km sprinting.6', 'strength training.6',
'hours alternative.6', 'nr. sessions_week', 'nr. rest days', 'total kms', 'max km one day', 'total km Z3-Z4-Z5-T1-T2',
'nr. tough sessions (effort in Z5, T1 or T2)', 'nr. days with interval session', 'total km Z3-4', 'max km Z3-4 one day',
'total km Z5-T1-T2', 'max km Z5-T1-T2 one day', 'total hours alternative training', 'nr. strength trainings',
'nr. sessions.1_week', 'nr. rest days.1', 'total kms.1', 'max km one day.1', 'total km Z3-Z4-Z5-T1-T2.1', 'nr. tough sessions (effort in Z5, T1 or T2).1',
'nr. days with interval session.1', 'total km Z3-4.1', 'max km Z3-4 one day.1', 'total km Z5-T1-T2.1',
'max km Z5-T1-T2 one day.1', 'total hours alternative training.1', 'nr. strength trainings.1',
'nr. sessions.2_week', 'nr. rest days.2', 'total kms.2', 'max km one day.2', 'total km Z3-Z4-Z5-T1-T2.2', 'nr. tough sessions (effort in Z5, T1 or T2).2',
'nr. days with interval session.2','total km Z3-4.2','max km Z3-4 one day.2', 'total km Z5-T1-T2.2',
'max km Z5-T1-T2 one day.2', 'total hours alternative training.2', 'nr. strength trainings.2', 'rel total kms week 0_1',
'rel total kms week 0_2', 'rel total kms week 1_2'
5. **Subjective Features** - 'perceived exertion', 'perceived trainingSuccess', 'perceived recovery',
'perceived exertion.1', 'perceived trainingSuccess.1', 'perceived recovery.1',
'perceived exertion.2', 'perceived trainingSuccess.2', 'perceived recovery.2',
'perceived exertion.3', 'perceived trainingSuccess.3', 'perceived recovery.3',
'perceived exertion.4', 'perceived trainingSuccess.4', 'perceived recovery.4',
'perceived exertion.5', 'perceived trainingSuccess.5', 'perceived recovery.5',
'perceived exertion.6', 'perceived trainingSuccess.6', 'perceived recovery.6',
'avg exertion', 'min exertion', 'max exertion', 'avg training success', 'min training success',
'max training success', 'avg recovery', 'min recovery', 'max recovery', 'avg exertion.1', 'min exertion.1',
'max exertion.1', 'avg training success.1', 'min training success.1', 'max training success.1',
'avg recovery.1', 'min recovery.1', 'max recovery.1', 'avg exertion.2', 'min exertion.2', 'max exertion.2',
'avg training success.2','min training success.2', 'max training success.2', 'avg recovery.2',
'min recovery.2', 'max recovery.2'

---
**Author:** Pascal Ghanimi
**GitHub Repository:** https://github.com/pascalghanimi/Injury-Prediction-in-Runners.git



