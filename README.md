# Speaker-independent voice pathology detection on the Saarbrücken Voice Database: revision code

Code and session-level tables for the revised version of manuscript JVOICE-D-26-01691,
"Clinical Praat Parameters and Cepstral Representations for Speaker Independent Voice Pathology
Detection: The Influence of Age and Dysphonia Severity".

## Contents

| Path | What it does |
| --- | --- |
| `notebooks/01_gravidade_idade_sexo.ipynb` | Metadata (age, sex, real speaker), removal of duplicated sessions, AVQI v03.01, severity strata, signal typology, age matching and age-reweighted XGBoost; Tables 1, 2, 3, 4, 8, 9 and Figures 1, 2, 7, 8, 9 |
| `notebooks/02_modelos_ablacoes_tabelas_5a7.ipynb` | SVM, Random Forest, XGBoost, FT-Transformer and wav2vec 2.0 under nested cross-validation grouped by speaker; ablations, equivalence test, SHAP; Tables 5, 6, 7 and Figures 3 to 6 |
| `notebooks/03_pipeline_original_corrigido.ipynb` | Pipeline of the original submission with the corrections applied, including the count of duplicated sessions split across folds |
| `praat/AVQI_v03.01.praat` | AVQI v03.01 script, run unmodified through parselmouth |
| `tabelas/` | Session-level tables produced by the notebooks (CSV) |

## Data

The Saarbrücken Voice Database is publicly available at https://stimmdb.coli.uni-saarland.de.
Recordings are not redistributed here. Age, sex and speaker identifiers come from the `summary.csv`
file distributed with the `sbvoicedb` Python package.

## Reproducing

Run the notebooks in Google Colab (GPU runtime for notebook 02) with the SVD feature matrix in
`MyDrive/svd_data`. Every fold is cached, so an interrupted session resumes where it stopped.
Seeds are fixed (42); outer folds are stored in the cache folder.
