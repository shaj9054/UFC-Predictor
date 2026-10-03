# UFC Fight Data Exploration

An in-progress Python project exploring UFC fight records and preparing features for a future prediction model. The current repository contains exploratory data analysis and feature engineering in a Jupyter notebook; it does not yet contain a trained predictor.

## Current workflow

- Loads historical fights from `data/ufc-master.csv` with pandas.
- Inspects columns, types, missing values and outcome distributions.
- Keeps records with Red/Blue winners and recognised finish methods.
- Groups decision outcomes into DEC, alongside SUB and KO/TKO.
- Identifies paired red/blue fighter statistics and computes differences.
- Builds ranking indicators, filled ranking values, stance differences and debut-related features.
- Fills selected average-statistic differences using medians.
- Adds fight-level attributes for title bouts, gender and average weight.

## Repository structure

| Path | Purpose |
| --- | --- |
| `explore.ipynb` | Exploratory analysis and feature preparation. |
| `data/ufc-master.csv` | Historical fight dataset used by the notebook. |
| `data/upcoming.csv` | Included upcoming-fight input; not used by the current notebook workflow. |
| `requirements.txt` | Pinned environment snapshot, including notebook and data-science packages. |

## Requirements and running

Use Python 3 and a Jupyter environment. For a minimal environment matching the packages directly used by the notebook:

```bash
git clone https://github.com/shaj9054/UFC-Predictor.git\ncd UFC-Predictor\npython3 -m venv .venv\nsource .venv/bin/activate\npython -m pip install pandas jupyterlab\njupyter lab explore.ipynb
```

On Windows, activate with `.venv\\Scripts\\activate` instead of `source`. The full environment snapshot can alternatively be installed with `python -m pip install -r requirements.txt`; exact version availability and platform compatibility may vary.

Start Jupyter from the repository root and run cells in order so the relative `data/` paths resolve and intermediate variables exist.

## Outputs

The notebook displays tables, counts, distributions and engineered columns in `df_clean`. It does not currently export a model or generate predictions for upcoming fights.

## Next steps

Establish dataset provenance and feature timing, then define a prediction target and use chronological training/validation/test splits. Fit preprocessing on training data only, compare against a simple baseline and report held-out performance. Persist the fitted pipeline before adding upcoming-fight inference.

The current full-dataset median filling is exploratory and should not be copied into a train/test evaluation without adjustment. No model accuracy claims are made at this stage.

**Author:** Mohammed Shajalal Sarwar. **Language:** Python.
