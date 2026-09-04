# SurgicalInsight

**Open-source machine learning risk calculator for retroperitoneal anterior lumbar interbody fusion (ALIF) surgery.**

Developed as part of the study:
> *"Development and Open-Source Deployment of a Machine Learning Risk Calculator for Retroperitoneal Anterior Lumbar Interbody Fusion: A Validated Preoperative Tool for Patient Selection and Complication Risk Stratification"*
> Puranjay Gupta, [Institution]

## Live application
🔗 [surgical-insight.streamlit.app](https://surgical-insight.streamlit.app) *(deploy via Streamlit Community Cloud)*

## What it does
SurgicalInsight provides six interactive panels for retroperitoneal ALIF risk analysis:

| Tab | Description |
|-----|-------------|
| 📊 Demographics | Cohort characteristics and distributions |
| ⚕️ Complications | 30-day outcome rates and profiles |
| ⏱ Exposure time | ET analysis by level and complexity |
| 🤖 Model | SHAP importance, regression table, ROC curve |
| 🎯 Risk calculator | Patient-level complication probability |
| 🏥 ALIF Operative Risk | Level-stratified calculator with ET pre-fill |

## ALIF Operative Risk Calculator
The flagship feature. Enter:
- Patient demographics (age, sex, BMI, ASA class)
- Surgical history (prior abdominal surgery, revision)
- Planned operative levels (L5-S1, L4-5, L3-4, L2-3)
- Estimated exposure time (auto pre-filled from registry medians)
- Anticipated surgical time

Output: individualised 30-day complication probability with risk tier, risk curve, and driver summary table.

## Model
- **Algorithm:** Logistic regression (retrained with individual anatomical level flags)
- **AUC:** 0.710 (5-fold stratified cross-validation)
- **n:** 331 consecutive patients, single institution
- **Outcome:** 30-day composite complication endpoint
- **Key finding:** Age and ASA class are the dominant independent predictors; approach exposure time is not independently significant once patient complexity is controlled

## Running locally
```bash
pip install -r requirements.txt
streamlit run app.py
```

## Data
The de-identified dataset (331 patients × 88 columns) is included as `data_submission_deidentified.csv`. Variables are described in the accompanying data dictionary.

## Citation
[To be updated on publication]

## License
MIT License — free to use, adapt, and deploy with attribution.

## Contact
[Author contact — to be completed]
