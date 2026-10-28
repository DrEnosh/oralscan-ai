# OralScan AI

A Streamlit demo that estimates oral cancer risk from a handful of risk factors and produces a one-page PDF summary.

> **Educational demo, not a clinical tool.** The model has not been clinically validated and must not be used to assess real patients.

## What it does

- Takes seven yes/no inputs in the sidebar: tobacco use, alcohol, betel quid, oral lesions, red or white patches, HPV infection and early diagnosis
- Runs a Random Forest classifier and shows a risk category with a probability, a confidence value and a short plain-language reason
- Lets you download the result as a PDF report (ReportLab)

## How the model is built

When the app starts, it loads `oral_cancer.csv` (about 85,000 patient records), converts Yes/No columns to 1/0, one-hot encodes the remaining categorical columns and fits a Random Forest (250 trees) to predict `Oral Cancer Diagnosis`.

The model is trained on the whole dataset inside the app and no held-out evaluation is reported, so the risk figures should be read as an illustration of the workflow rather than a measured accuracy.

## Run it

You need a recent Python 3.

```bash
pip install -r requirements.txt
streamlit run app.py
```

Then open the local address Streamlit prints (usually http://localhost:8501). The repo also includes a dev container for GitHub Codespaces.

## Files

| File | Purpose |
| --- | --- |
| `app.py` | Streamlit app: data prep, model, dashboard, PDF report |
| `oral_cancer.csv` | Dataset used to train the model |
| `requirements.txt` | Python dependencies |
| `.devcontainer/` | Codespaces / VS Code dev container |

## Author

Dr. Enosh A Paulson. [LinkedIn](https://linkedin.com/in/dr-enosh) · [GitHub](https://github.com/DrEnosh)
