# Tumor Origin Predictor

Predicts where a tumor started (its cancer type) from its gene activity, using public TCGA data.

## Goal

1. **Predict:** train a model on ~10,600 primary tumors to predict which of 33 cancer types a tumor is from its ~20,500 gene activity values.
2. **Simplify:** find the fewest genes that keep accuracy close to the best.
3. **Explain:** trace the model's mistakes to biology (e.g. colon vs. rectal tumors).
4. **Real-world test:** test the trained model on metastatic tumors it never saw.
5. **App:** a FastAPI + React app that takes a tumor's gene profile and returns the predicted origin, confidence, and the genes behind it.

## Data

- Expression table (GDC Pan-Cancer Atlas, ~1.9 GB): https://api.gdc.cancer.gov/data/3586c0da-64d0-4b74-a449-5ff4d9136611
- Cancer-type labels (UCSC Xena): https://tcga-pancan-atlas-hub.s3.us-east-1.amazonaws.com/download/TCGA_phenotype_denseDataOnlyDownload.tsv.gz

## Structure

```
scripts/   download the data
src/       load, stats, model, evaluate
notebooks/ exploration
app/       FastAPI + React app
results/   figures
data/      downloaded files (not committed)
```
