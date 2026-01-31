# Machine Learning Prediction of Core Body Temperature under Heat Stress

This repository contains the datasets and scripts used in the study:

**“Machine Learning Prediction of Core Body Temperature in Recreational Athletes Exercising Under Heat Stress.”**

The project investigates the use of machine learning (ML) methods to predict core body temperature (Tcore) in recreational athletes exposed to environmental heat stress, using physiological and environmental measurements collected during controlled 10 km running trials.

The repository provides data preprocessing scripts, model training pipelines, and evaluation workflows to allow full reproducibility of the results presented in the article.

---

## 📌 Repository Structure

tcore/
│
├── data/
│ ├── raw/ # Original dataset obtained from Andrade et al.
│ ├── processed/ # Preprocessed datasets (DS1–DS6)
│
├── notebooks/ # Jupyter notebooks for data analysis and experiments
│
├── src/
│ ├── preprocessing/ # Data cleaning and dataset construction scripts
│ ├── models/ # Model training scripts
│ ├── evaluation/ # Model evaluation and metrics computation
│ └── utils/ # Helper functions
│
├── results/ # Output metrics, model results, and figures
│
├── environment.yml # Optional Conda environment specification
├── requirements.txt # Python dependencies
└── README.md

yaml
Copiar código

*(Folder names may vary slightly depending on repository organization.)*

---

## 📊 Datasets

The repository includes datasets derived from the experimental protocol described in Andrade et al. (2023), consisting of treadmill running trials performed under controlled heat stress conditions.

Two modeling strategies are used:

### 1. Endpoint datasets (post-10 km measurements)

These datasets reproduce the original modeling strategy:

| Dataset | Description | Samples |
|----------|------------|----------|
| DS1 | Full predictor set (10 variables) | 75 |
| DS2 | Reduced predictor set (8 variables) | 75 |
| DS3 | Field-applicable predictors (5 variables) | 75 |

---

### 2. Kilometer-level datasets (longitudinal modeling)

Measurements aggregated every kilometer during the run:

| Dataset | Description | Samples |
|----------|------------|----------|
| DS4 | Physiological + environmental predictors | 750 |
| DS5 | Environmental + peripheral variables | 750 |
| DS6 | Extended environmental and physiological set | 750 |

These datasets enable time-resolved modeling of thermoregulatory responses.

---

## ⚙️ Methods Overview

The modeling pipeline includes:

- Data preprocessing and feature selection
- Dataset construction
- Training/testing splits preserving group independence
- Nested cross-validation
- Hyperparameter optimization via Grid Search
- Performance evaluation using:
  - RMSE
  - R²
- Model interpretability using SHAP values

Algorithms evaluated:

- LASSO Regression
- Decision Tree
- Random Forest
- Support Vector Regression (SVR)
- XGBoost

---

## 🚀 Reproducing the Experiments

### 1. Clone repository

```bash
git clone https://github.com/LBS-UFMG/tcore.git
cd tcore
2. Create environment
Using Conda:

bash
Copiar código
conda env create -f environment.yml
conda activate tcore
or pip:

bash
Copiar código
pip install -r requirements.txt
3. Run preprocessing
bash
Copiar código
python src/preprocessing/build_datasets.py
4. Train models
Example:

bash
Copiar código
python src/models/train_models.py --dataset DS5 --model xgboost
5. Evaluate models
bash
Copiar código
python src/evaluation/evaluate_models.py
Results will be saved in the results/ directory.

📈 Output
The repository enables reproduction of:

Model performance metrics

Comparison across datasets

Hyperparameter configurations

SHAP feature importance analyses

🔍 Model Interpretation
SHAP analysis is used to:

Explain individual predictions

Rank feature importance

Understand model decision patterns

This improves transparency of ML-based predictions.

⚠️ Limitations
Kilometer-level datasets contain repeated measurements from the same individuals and should not be treated as independent samples.

Model performance depends on controlled laboratory conditions and may vary under real-world environments.

📜 Data Availability
All data and scripts required to reproduce the analyses are provided in this repository, following anonymization procedures described in the original study.

📚 Citation
If you use this repository, please cite:

css
Copiar código
Gontijo L. et al. Machine Learning Prediction of Core Body Temperature in Recreational Athletes Exercising Under Heat Stress. (Year).
and

arduino
Copiar código
Andrade MT et al. Predicting the body core temperature of recreational athletes at the end of a 10 km self-paced run under environmental heat stress. Experimental Physiology. 2023.
🤝 Contributions
Contributions, bug reports, and suggestions are welcome. Please open an issue or submit a pull request.

📄 License
Specify license information here.

📬 Contact
For questions regarding data or scripts:

Laboratory of Bioinformatics and Systems (LBS)
Federal University of Minas Gerais (UFMG) – Brazil