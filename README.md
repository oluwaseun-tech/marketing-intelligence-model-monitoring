# Marketing Intelligence & Model Monitoring System

An end-to-end portfolio project demonstrating marketing analytics, data-quality controls, an illustrative marketing mix model (MMM), Bayesian regression, and ongoing model/data monitoring using Python and Power BI.

> **Portfolio / learning project:** All records are synthetic. The model and alert rules are illustrative and are not a production marketing measurement system or evidence of real campaign performance.

## Business problem

Marketing teams need to understand channel performance, investigate unusual movements in spend and outcomes, and distinguish data-quality problems from model-performance issues. This project builds an analytical workflow around those tasks.

## Project workflow

1. Synthetic data generation across Google Ads, Meta Ads and TikTok Ads.
2. Data-quality audit and remediation of missing values, duplicates, inconsistent labels and invalid spend.
3. Channel-level marketing analytics, including CTR, CVR, CPC and CPA.
4. Regression-based MMM-style modelling with adstock and Hill saturation transformations.
5. Bayesian regression and model diagnostics using PyMC.
6. Weekly business, data-quality and model monitoring, presented in a three-page Power BI report.

## Repository contents

This repository currently contains:
- Project documentation and setup guidance.
- Python dependency specification and `.gitignore`.
- Selected result exports: channel metrics, Bayesian coefficient summary and data-quality audit.

**The original five notebooks, complete raw and processed CSV datasets, monitoring report exports, Bayesian trace file and Power BI `.pbix` dashboard have not yet been uploaded to this repository.** The complete project archive is available in the ChatGPT conversation where the project was prepared.

## Dashboard screenshots

The report has three pages. The screenshots below are preview images; use the Power BI `.pbix` file for the interactive report once it is added to `dashboard/`.

### Executive Overview

![Executive Overview](images/executive-overview.jpg)

### Channel Performance

![Channel Performance](images/channel-performance.jpg)

### Model Health & Anomalies

![Model Health & Anomalies](images/model-health-anomalies.jpg)

## Key analytical definitions and caveats

- CTR = clicks / impressions; CVR = conversions / clicks; CPC = spend / clicks; CPA = spend / conversions.
- Revenue is weekly business-level revenue. It is **not** channel-attributed revenue; channel ROAS is therefore not presented as an observed metric.
- Blended ROAS = total weekly business revenue / total advertising spend. Blended CAC = advertising spend / new customers. These are aggregate ratios, not incremental or causal channel returns.
- Adstock decay and Hill half-saturation settings are simulation assumptions. Modelled channel contributions are associations within the synthetic dataset, not causal lift estimates.
- Monitoring cut-offs are demonstrative configuration choices, not universal industry standards.
- Bayesian convergence diagnostics assess sampling behaviour; they do not establish model validity, predictive generalisation or causality.

## Run the project

The notebooks were developed in Google Colab and use a Google Drive project directory. After uploading/extracting the full project files, update the setup/path cells when running in another environment.

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebooks in numerical order:

1. `01_data_generation.ipynb`
2. `02_data_quality_audit.ipynb`
3. `03_marketing_analytics.ipynb`
4. `04_bayesian_mmm.ipynb`
5. `05_marketing_model_monitoring.ipynb`

Open the Power BI file in Power BI Desktop after adding it to `dashboard/`.

## Tools

Python, pandas, NumPy, DuckDB, scikit-learn, statsmodels, PyMC, ArviZ, matplotlib and Power BI.

## Author

**Oluwaseun Aribisogan**  
[GitHub](https://github.com/oluwaseun-tech) · [Portfolio](https://oluwaseun-tech.github.io/portfolio/)
