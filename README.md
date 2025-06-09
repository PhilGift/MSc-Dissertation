ASD Diagnosis in Children from fMRI Using XGBoost
MSc-Disssertation


A collection of Python scripts and notebooks for preprocessing ABIDE rs-fMRI data, training an interpretable XGBoost classifier, and evaluating performance in pediatric ASD diagnosis.


Features

* Download and preprocess ABIDE NYU pediatric subset (rs-fMRI + phenotypic data)
* Extract CC200 atlas functional connectivity matrices
* Perform feature selection (SelectKBest) and integrate phenotypic metadata
* Train and cross-validate an XGBoost classifier (12‑fold stratified CV)
* Generate performance metrics: accuracy, precision, recall, F1-score, ROC/AUC, confusion matrices
* Plot training curves, boxplots of CV metrics, connectome figures, and data‑flow diagrams



Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/PhilGift/MSc-Dissertation.git
   cd MSC-Dissertation
   ```
2. Create and activate the environment:

   ```bash
   conda env create -f environment.yml
   conda activate MSc-Dissertation
   ```

## Usage

1. **Preprocess data**:

   ```bash
   python scripts/preprocess_data.ipynb --input_dir data/raw 
   ```
2. **Select features_Train model**:

   ```bash
   python scripts/feature_selection_train_xgboost.ipynb 
   ```
3. **Top 20 Most Important Features**:

   ```bash
   python scripts/top_20_most_important_features.ipynb 
   ```

Files

* `preprocess_data.py`: loads raw NIfTI, applies motion correction, normalization, filtering, nuisance regression, and extracts ROI-to-ROI correlation matrices.
* `feature_selection_train_xgboost.ipynb`: trains an XGBoost classifier with 12-fold CV and logs performance metrics, performs SelectKBest on connectivity features and concatenates phenotypic features.
* `top_20_most_important_features.ipynb`: creates training loss/accuracy curves, boxplots, ROC curve, confusion matrices, and connectome lateralization figure.


