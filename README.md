# Running Footwear & Apparel Customer Segmentation
Unsupervised learning study that segments running footwear & apparel customers into behavioral clusters, then breaks those clusters down by market (USA, UK, Japan) to generate region-specific product and marketing recommendations.

## Overview
A running footwear & apparel brand surveyed 175 consumers across the USA, UK, and Japan about their running habits, gear preferences, and pain points. This project uses K-Means clustering on the survey responses to identify distinct customer segments, then profiles each segment by demographics, running frequency, shoe ownership, cushioning/plating preferences, color preferences, and top complaints, producing actionable recommendations for product design and regional marketing strategy.

## Objective
To apply unsupervised learning techniques to consult a running footwear & apparel company on strategic decisions regarding their running product and marketing.

## Data
- Source: Consumer survey (survey_data.csv), 175 respondents, 47 columns.
- Format: Mostly binary (0/1) indicator variables for multi-select survey questions, plus a record ID and country/validity flags.
- Key fields: Full column-by-column definitions are documented in the notebook's Data Dictionary section.

## Methodology
1. Data cleaning — dropped non-informative ID columns, removed invalid survey responses (per S2r2), and confirmed there were no missing values or duplicates.
2. Exploratory analysis — profiled the sample by country, gender, age, and gear preferences with bar charts.
3. Similarity metric — computed a Jaccard similarity matrix, appropriate for binary survey data.
4. Clustering — evaluated cluster count using the elbow method (SSE) and silhouette score; selected k = 3 via K-Means (Gaussian Mixture Models were also tested but K-Means gave more interpretable results).
5. Segment profiling — split each of the 3 clusters by country (USA / UK / Japan) and by gender to compare age, running frequency, gear ownership, preferences, and complaints across segments.
6. Recommendations — synthesized region-specific product and marketing recommendations for each cluster.

## Key Findings
Across all three markets, the same three behavioral segments emerged consistently:
- Cluster 0: "Committed Regulars": Run 3–4x/week, own ~1 pair of shoes, financially stable, want more fashionable and durable shoes.
- Cluster 1: "Casual/Occasional Runners": Skew younger, run occasionally, own a single multi-purpose pair, primary complaint is style/fashion.
- Cluster 2: "Committed Enthusiasts": Run 5+x/week, own 3–5+ pairs, most knowledgeable about gear, fewest complaints, represent the most established customer base.

Regional nuances (e.g., color preference splits by gender, cushioning/plating preference differences between the UK and USA) are detailed in the notebook's per-country sections.

## Tools & Libraries
Python, pandas, NumPy, scikit-learn (KMeans, GaussianMixture, silhouette_score, pairwise_distances), Matplotlib, Seaborn


## Repository Structure

```
running-gear-segmentation-study/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── Running-Gear-Segmentation-Study.ipynb
├── data/
│   └── survey_data.csv
|   └── Data_Dictionary.txt         
└── images/                      # optional: exported charts for README/reports
```

## Author
Balbina Salas