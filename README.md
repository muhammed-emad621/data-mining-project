# Data Mining Algorithms Project — Wine Cultivar Classification

## Project question
Can classical data-mining classification algorithms identify the cultivar of an Italian wine from 13 chemical measurements?

## Dataset
- **Source:** UCI Machine Learning Repository — Wine dataset
- **DOI:** https://doi.org/10.24432/C5PC7J
- **Instances:** 178
- **Predictive features:** 13 numeric chemical measurements
- **Target:** 3 wine classes
- **Missing values:** none

## Preprocessing
- Audited shape, class balance, missing values, and duplicates.
- Used a stratified 80/20 train/test split (`random_state=42`).
- Ranked features with mutual information.
- Selected the top 8 features **inside the modeling pipeline** to prevent leakage.
- Standardized inputs for KNN only.

## Algorithms
1. **Decision Tree:** entropy criterion, max depth 4.
2. **KNN:** 7 neighbors, distance weighting, with standardization.
3. **Random Forest:** 200 trees, maximum depth 6, square-root feature sampling.

## Results
The exact numbers below were obtained by running the project locally with scikit-learn 1.8.0 on the fixed 80/20 stratified split:

| Model | 5-fold CV Accuracy | Test Accuracy | Weighted F1 |
|---|---:|---:|---:|
| Decision Tree | 0.874 ± 0.046 | 1.000 | 1.000 |
| KNN | 0.965 ± 0.022 | 0.944 | 0.944 |
| Random Forest | 0.972 ± 0.026 | 1.000 | 1.000 |

## Selected features
alcohol, malic_acid, total_phenols, flavanoids, color_intensity, hue, od280/od315_of_diluted_wines, proline

## Tool
Python in Google Colab using pandas, NumPy, Matplotlib, Seaborn, and scikit-learn.

## Files
- `Wine_Data_Mining_Project.ipynb` — complete runnable notebook
- `Data_Mining_Project_Report.docx` — project report
- `Data_Mining_Project_Presentation.pptx` — 5–10 minute presentation
- `Speaker_Notes.md` — presentation script
- `figures/` — generated figures
- `results.csv` — machine-readable results
- `requirements.txt` — Python dependencies

## Running in Colab
Open the notebook in Google Colab and run all cells. The dataset is loaded through scikit-learn, so no manual download is required; the original source is UCI.
