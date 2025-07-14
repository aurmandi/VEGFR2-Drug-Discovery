# VEGFR2pred: A Machine Learning Tool for Predicting VEGFR2 Inhibition


A user-friendly graphical interface and command-line tool that leverages machine learning to predict the inhibitory activity of small molecules against Vascular Endothelial Growth Factor Receptor 2 (VEGFR2). This tool is the official implementation of the models described in our paper:

## Overview
VEGFR2 is a critical therapeutic target in oncology. This project provides a robust and validated tool to accelerate the discovery of novel VEGFR2 inhibitors by providing rapid, in silico predictions of a compound's potential activity.

VEGFR2pred uses an ensemble of machine learning models trained on a curated dataset of over 17,000 compounds to classify a molecule as a potential VEGFR2 inhibitor or non-inhibitor based on its chemical structure (provided as a SMILES string).


## Features
Multiple High-Performing Models: Utilizes three robust machine learning models: Support Vector Machine (SVM), Random Forest (RF), and XGBoost.

Dual Fingerprint Analysis: Generates predictions using two of the most informative molecular fingerprints: ECFP-like and RDKit fingerprints.

Ensemble Prediction: Provides a final classification based on a majority-vote consensus from the six model-fingerprint combinations for higher confidence.

Probability Scores: Outputs the predicted probability of inhibition for each model, giving insight into the model's confidence.

Simple User Interface: Includes an easy-to-use Graphical User Interface (GUI) for interactive predictions.

Command-Line Interface: Also available as a script for high-throughput screening and integration into automated workflows.

## Installation
To get started with VEGFR2pred, clone the repository and install the required dependencies. A Python version of 3.8 or higher is recommended.

### 1. Clone the repository
git clone [https://github.com/your-username/VEGFR2pred.git](https://github.com/your-username/VEGFR2pred.git)
cd VEGFR2pred

### 2. (Recommended) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

### 3. Install the required packages
pip install -r requirements.txt

* Dependencies: *
The main dependencies are listed in requirements.txt and include:

numpy  
joblib  
rdkit  
standardiser  
scikit-learn  
xgboost  
pillow  

## Usage
Graphical User Interface (GUI)
To launch the graphical interface, run the following command from the project's root directory:

python gui.py

Enter a SMILES string into the text box and click "Predict". The results will be displayed in the table.

Command-Line Tool
For programmatic use or batch processing, you can use the predict.py script:

python predict.py --smiles "Cn1cnc2c1c(=O)n(c(=O)n2C)C"


## How It Works
The prediction process follows the workflow described in our paper:

Standardization: The input SMILES string is standardized to ensure a consistent molecular representation (e.g., tautomers corrected, salts removed).

Fingerprint Generation: Two molecular fingerprints are generated: ECFP and RDKit.

Model Prediction: Each fingerprint is passed to our three pretrained models (RF, SVM, XGBoost), resulting in six total predictions.

Consensus Classification: A final prediction is made using a majority vote. If more than half of the predictions are class 1 (inhibitor), the compound is classified as a potential inhibitor.


