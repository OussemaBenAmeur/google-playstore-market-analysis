# Google Play Store Market Analysis

This repository contains my first data science project and my first academic semestrial project. The work studies the Google Play Store market using the Kaggle dataset [Google Play Store Apps](https://www.kaggle.com/datasets/gauthamp10/google-playstore-apps) by Gautham Prakash, which contains Google Play Store app data collected in June 2021 and covers 2.3M+ applications.

The main purpose of the project is not just to visualize the dataset, but to build a complete analysis workflow around it:

- clean and standardize raw Play Store app data
- engineer new features such as `Rating Confidence`, app age, update recency, seasonality, region, and a custom `Monetization Score`
- explore how installs, pricing, app size, category, and release timing relate to app performance
- use unsupervised learning to segment apps and detect unusual market behavior

## Project Focus

The analysis is centered on understanding how app characteristics relate to market performance in the Play Store. In the notebooks, the project specifically looks at:

- category distribution and average installs by category
- relationships between installs and rating confidence, size, price, age, and update frequency
- free vs paid app behavior
- regional and seasonal patterns derived from the dataset
- feature correlations across the engineered dataset
- K-means clustering after PCA for app segmentation
- Isolation Forest for outlier detection

This means the project is part exploratory data analysis, part feature engineering exercise, and part introductory machine learning project.

## Project Layout

```text
google-playstore-market-analysis/
├── data/
│   ├── processed/
│   └── raw/
├── notebooks/
│   ├── 00_helpers.ipynb
│   ├── 01_data_preparation.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   └── 03_unsupervised_segmentation.ipynb
├── Google_Playstore_Market_Analysis.ipynb
└── README.md
```

`Google_Playstore_Market_Analysis.ipynb` is the original notebook. The `notebooks/` directory contains a cleaner modular version of the same project flow.

## Notebook Flow

1. [01_data_preparation.ipynb](/home/oussema/Desktop/github/google-playstore-market-analysis/notebooks/01_data_preparation.ipynb)  
   Loads the raw dataset, removes unnecessary fields, cleans missing values, converts dates and sizes, and creates analysis-ready features.

2. [02_exploratory_analysis.ipynb](/home/oussema/Desktop/github/google-playstore-market-analysis/notebooks/02_exploratory_analysis.ipynb)  
   Covers the main EDA: category trends, install behavior, pricing patterns, regional and seasonal views, and correlation analysis.

3. [03_unsupervised_segmentation.ipynb](/home/oussema/Desktop/github/google-playstore-market-analysis/notebooks/03_unsupervised_segmentation.ipynb)  
   Applies PCA, K-means clustering, and Isolation Forest to group apps and flag outliers.

[00_helpers.ipynb](/home/oussema/Desktop/github/google-playstore-market-analysis/notebooks/00_helpers.ipynb) contains the shared setup and reusable cleaning logic.

## Dataset

Dataset source: [Kaggle - Google Play Store Apps](https://www.kaggle.com/datasets/gauthamp10/google-playstore-apps)

Relevant dataset details from the Kaggle page:

- title: `Google Play Store Apps`
- scale: `2.3 Million+ App Data`
- collection method: scraped with Python/Scrapy
- collection period: June 2021

Place the raw CSV in one of these locations:

- `data/raw/Google-Playstore.csv`
- project root as `Google-Playstore.csv`
- Kaggle path `/kaggle/input/google-playstore-apps/Google-Playstore.csv`

The modular notebooks search these paths automatically.

## Recommended Run Order

1. Run [01_data_preparation.ipynb](/home/oussema/Desktop/github/google-playstore-market-analysis/notebooks/01_data_preparation.ipynb)
2. Confirm that `data/processed/google_playstore_cleaned.csv` was created
3. Run [02_exploratory_analysis.ipynb](/home/oussema/Desktop/github/google-playstore-market-analysis/notebooks/02_exploratory_analysis.ipynb)
4. Run [03_unsupervised_segmentation.ipynb](/home/oussema/Desktop/github/google-playstore-market-analysis/notebooks/03_unsupervised_segmentation.ipynb)

## Environment

Recommended stack:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```
