## A Comparative Study of Feature Representations for Machine Learning-Based Peptide RT Prediction

### Motivation
Understanding peptide retention time (RT) in liquid chromatography is crucial for enhancing peptide identification and separation. Peptide RT refers to the time it take to elude from a liquid chromatography column. RT is primarily determined by peptide hydrophobicity, sequence, and other physicochemical properties. I chose this topic as a learning exercise to explore fundamental aspects of feature representation of peptide in machine learning to predict RT of experimental dataset. Since both peptide sequence and chemistry influence peptide properties like RT, it is worthwhile to investigate how simple sequence- and chemistry-based feature representations can improve model performance. In this context, starting with a basic amino acid count-based approach for peptide RT prediction provides a useful foundation. Additionally, examining how data dimensionality impacts predictive performance may offer further insights.

### Dataset
I am using two datasets from the [PepMNet RT Data repository](https://github.com/danielgarzonotero/PepMNet/tree/main/data/RT):  

| Dataset | LC Type | Number of Peptides |
|---------|---------|------------------|
| HeLa    | RPLC    | 1,170            |
| Yeast   | RPLC    | 14,361           |

These datasets contain peptides composed of natural amino acids, measured using reversed-phase liquid chromatography (RPLC). RPLC separates peptides based on hydrophobic interactions with a stationary phase, making the data particularly suitable for studying sequence- and structure-based determinants of hydrophobicity and retention behavior.

### Goals
The project aims to investigate how effectively various machine learning methods can predict peptide retention time (RT) and to quantify the contribution of sequence‑based and physicochemical features. The specific objectives are:

1. Evaluate the influence of different feature representations on prediction accuracy, including:

    a. Sequence‑independent features: bag‑of‑words (BoW) with sequence length, and bag‑of‑words with sequence length plus physicochemical descriptors (BoW+PD) (e.g., net charge, aromaticity, hydrophobicity).

    b. Sequence‑dependent features: one‑hot encoding of amino acid sequences.

2. Assess the performance of multiple machine learning models: Linear Regression, Kernel Ridge Regression, and XGBoost—using each of the three feature representations for peptide RT prediction.

Benchmark these models against PepMNet, a pretrained hierarchical graph‑based model that incorporates both atom‑level and amino‑acid‑level information.

## Directory Structure
| File / Directory | Description |
|------------------|-------------|
| `data_science_project_2025.ipynb` | Main Jupyter notebook containing all analysis, feature extraction, model training, and evaluation |
| `hela_mod3.csv` | Dataset of modified peptides from HeLa cell experiments |
| `yeast_unmod.csv` | Dataset of unmodified peptides from yeast |
| `saved_csv_features/` | Generated feature and output CSV files (e.g., Bag-of-Words, One-Hot encodings, physicochemical descriptors) |
| `final_plots/` | Final plot images summarizing model performance and comparisons |
| `model_outputs/` | Saved trained machine learning models (`.pkl` files) |
| `results/` | Directory containing processed results |
| `results/RT/` | Excel (`.xlsx`) files with training/testing splits for retention time prediction |
| `README.md` | Project documentation and usage instructions |
| `requirements.txt` | Python dependencies required to run the project |

