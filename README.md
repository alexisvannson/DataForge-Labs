# DataForge-Labs Customer Intelligence Platform

A data-driven customer intelligence platform that leverages machine learning to optimize marketing ROI through customer segmentation, lifetime value analysis, and predictive campaign targeting.

## Overview

ROILab transforms raw customer data into actionable business insights by identifying distinct customer segments, predicting campaign response rates, calculating customer lifetime value (CLV), and monitoring churn risk. The platform enables data-driven marketing decisions that reduce costs while maintaining or improving conversion rates.

## Getting Started

### Data Analysis

The complete analysis is available in the Jupyter notebook:

```bash
jupyter notebook ClientInsights.ipynb
```

### Web Dashboard

Launch the interactive ROILab dashboard:

```bash
cd ui
npm install
npm run dev
```

## Data Source

Analysis based on the [Customer Personality Analysis dataset](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis) containing 2,240 customer records with demographics, purchase history, and campaign responses.

## Technical Stack

**Analysis**
- Python 3.x
- pandas, numpy
- scikit-learn (K-means, Random Forest, Gradient Boosting)
- matplotlib, seaborn

**Dashboard**
- React 18 + TypeScript
- Vite
- shadcn/ui + Radix UI
- TailwindCSS
- Recharts

## Authors

**Millan Das, Arthur de Leusse & Alexis Vannson**

## License

This project is licensed under the terms in the [LICENSE](LICENSE) file.
