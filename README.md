# Marketing Intelligence & Model Monitoring System

An end-to-end portfolio project demonstrating marketing analytics, data-quality controls, an illustrative marketing mix model (MMM), Bayesian regression, and ongoing model/data monitoring using Python and Power BI.

> **Portfolio / learning project:** All records are synthetic. The model and alert rules are illustrative and are not a production marketing measurement system or evidence of real campaign performance.

## Business problem

Marketing teams need to understand channel performance, investigate unusual movements in spend and outcomes, and distinguish data-quality problems from model-performance issues. This project builds a reproducible analytical workflow around those tasks.

## Project workflow

1. **Synthetic data generation** — weekly advertising, sales and promotion data for Google Ads, Meta Ads and TikTok Ads.
2. **Data quality audit and remediation** — identify missing fields, duplicate records and invalid spend; document exclusions and flags.
3. **Marketing analytics** — calculate channel-level CTR, CVR, CPC and CPA; prepare time-series features; fit a regression-based MMM-style model with adstock and saturation transformations.
4. **Bayesian regression** — estimate posterior distributions for channel and control coefficients with PyMC; review convergence diagnostics and posterior predictive behaviour.
5. **Monitoring** — generate weekly business and model-monitoring outputs, including spend movement, data-quality flags and prediction-error alerts.
6. **Power BI reporting** — present an executive overview, channel performance, and model-health / anomaly investigation pages.

## Repository structure

```text
.
├── data/
│   ├── raw/
│   ├── processed/
│   └── outputs/
├── notebooks/
├── reports/
└── dashboard/
```

## Key analytical definitions and caveats

- CTR = clicks / impressions; CVR = conversions / clicks; CPC = spend / clicks; CPA = spend / conversions.
- Revenue is weekly business-level revenue. It is **not** channel-attributed revenue. Therefore, this project does not present channel ROAS as an observed metric.
- Blended ROAS = total weekly business revenue / total advertising spend. Blended CAC = advertising spend / new customers. These are aggregate ratios, not incremental or causal channel returns.
- Adstock decay and Hill saturation settings are illustrative simulation assumptions. Model coefficients and channel contribution estimates are associations within this synthetic dataset, not causal lift estimates.
- Monitoring cut-offs are demonstrative configuration choices, not universal industry standards.
- Bayesian convergence diagnostics assess sampling behaviour; good convergence does not establish that the model is correctly specified, accurate in a new business, or causal.

## Run the notebooks

The notebooks were developed in Google Colab and use a Google Drive project directory. Update project paths in setup cells when running outside the original environment.

Install dependencies:

```bash
pip install -r requirements.txt
```

Download and extract [`notebooks/notebook_source_bundle.zip`](notebooks/notebook_source_bundle.zip) into the `notebooks/` folder, then run the notebooks in numerical order:

1. `01_data_generation.ipynb`
2. `02_data_quality_audit.ipynb`
3. `03_marketing_analytics.ipynb`
4. `04_bayesian_mmm.ipynb`
5. `05_marketing_model_monitoring.ipynb`

Open `dashboard/Marketing_Intelligence_Model_Monitoring.pbix` in Power BI Desktop. The original `.pbix` dashboard and complete CSV data exports are not included in this initial repository upload; the dashboard and data remain in the source ZIP shared for publication.

## Tools

Python, pandas, NumPy, scikit-learn, statsmodels, PyMC, ArviZ, matplotlib and Power BI.

## Author

**Oluwaseun Aribisogan**  
[GitHub](https://github.com/oluwaseun-tech) · [Portfolio](https://oluwaseun-tech.github.io/portfolio/)
