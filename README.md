# ML-Driven VEGFR2 Inhibitor Discovery Pipeline

## Overview
This repository hosts a comprehensive pipeline that integrates machine learning, similarity search, and molecular docking to identify potential inhibitors of the VEGFR2 receptor. Our workflow begins with a curated dataset of biomolecules—each evaluated for their IC50 values—and employs state-of-the-art cheminformatics and predictive modeling to partition molecules into inhibitory (label 1) and non-inhibitory (label 0) classes. The top inhibitory candidates are further expanded through similarity-based searches and rigorously filtered before advancing to molecular docking analyses.

## Project Description
Our pipeline is designed to tackle the complexities of drug discovery in a systematic and data-driven manner. The key steps are as follows:
- **Data Curation & Labeling:** Biomolecules with experimentally determined IC50 values are partitioned by a set threshold. Molecules exhibiting lower (more inhibitory) IC50 values are labeled as 1, while the rest are labeled 0.
- **Model Development & Evaluation:** Various machine learning algorithms and multiple SMILES fingerprint descriptors are compared to ascertain the most predictive models.
- **Similarity Search Expansion:** The PubChem REST API is used to retrieve hundreds of similar compounds (based on Tanimoto similarity) to the best-performing inhibitors.
- **Predictive Filtering & Docking:** The pre-validated model filters these similar molecules to prioritize candidates for molecular docking. Ultimately, the top three molecules with the best predicted binding profiles are selected for further investigation.
- **Integrated Reporting:** Detailed summaries and result files are generated at every stage for transparency and reproducibility.

## Features
- **Robust Data Partitioning:** Automated thresholding to convert IC50 measurements into binary labels.
- **Comparative Model Analysis:** Evaluation of multiple machine learning approaches with diverse SMILES-based fingerprints.
- **PubChem-Based Similarity Retrieval:** Leverages the PubChem REST API for Tanimoto similarity search to expand the inhibitor space.
- **End-to-End Docking Integration:** Seamless transition from predictive filtering to docking simulation, culminating in the identification of top candidate inhibitors.
- **Comprehensive Reporting:** Detailed performance metrics, ranked candidate lists, and docking outputs are provided to support decision-making.

## Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/aurmandi/?
   cd ?
## Requirements:
?
?
?
