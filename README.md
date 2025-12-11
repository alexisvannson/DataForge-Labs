# ROILab: Customer Intelligence Platform

A data-driven customer intelligence platform that leverages machine learning to optimize marketing ROI through customer segmentation, lifetime value analysis, and predictive campaign targeting.

## Overview

ROILab transforms raw customer data into actionable business insights by identifying distinct customer segments, predicting campaign response rates, calculating customer lifetime value (CLV), and monitoring churn risk. The platform enables data-driven marketing decisions that reduce costs while maintaining or improving conversion rates.

## Key Features

- **Customer Segmentation**: K-means clustering identifies 5 distinct customer personas with unique behavioral patterns
- **Campaign Response Prediction**: ML models predict which customers are most likely to respond to campaigns
- **ROI Optimization**: Reduce marketing spend by 30-40% while maintaining 90%+ of conversions
- **Customer Lifetime Value (CLV) Analysis**: Calculate and track CLV by segment using RFM methodology
- **Churn Risk Monitoring**: Identify at-risk customers and estimate potential revenue recovery
- **Next Best Action Engine**: Generate personalized recommendations for products, channels, and discount strategies
- **Interactive Dashboard**: Real-time visualization of key metrics and segment performance

## Customer Segments

The analysis identifies 5 distinct customer segments:

1. **Affluent Singles** (32.8% of customers, 53.3% of revenue)
   - Highest revenue contributors
   - Low discount sensitivity
   - Prefer wines via store channel

2. **Budget-Conscious Families** (11.8% of customers, 32.3% of revenue)
   - Highest campaign response rate (84%)
   - Value-focused, not discount-driven
   - Weekly campaign engagement

3. **High-Value Champions** (26.3% of customers, 8.4% of revenue)
   - Moderate discount sensitivity
   - Prefer store channel
   - Monthly campaign frequency

4. **Mature Loyalists** (29.1% of customers, 5.9% of revenue)
   - Low discount sensitivity (5-10% effective)
   - Consistent store shoppers
   - Monthly campaign engagement

5. **Price-Sensitive Shoppers** (0.1% of customers, <0.1% of revenue)
   - Highly discount-sensitive
   - Prefer catalog channel
   - Limited engagement

## Business Impact

### ROI Optimization
- **Current Approach**: Targeting all 2,212 customers
- **Optimized Approach**: Target only high-response segments (>20% predicted response)
- **Result**: 30-40% cost reduction with 90%+ conversion retention

### Churn Prevention
- Identify high-value at-risk customers
- Potential revenue recovery through 10% retention improvement
- Segment-specific retention strategies

## Project Structure

```
MolSignal/
├── ClientInsights.ipynb          # Complete data analysis notebook
│                                  # - Customer segmentation
│                                  # - Predictive modeling
│                                  # - CLV calculation
│                                  # - ROI analysis
│
├── customer_segments.csv         # Customer-level data with segments
├── segment_summary.csv           # Aggregate segment statistics
├── next_best_actions.csv         # Marketing recommendations
│
└── ui/                           # ROILab web application
    ├── src/
    │   ├── components/dashboard/
    │   │   ├── ROICalculator.tsx           # Campaign ROI optimizer
    │   │   ├── SegmentExplorer.tsx         # Segment deep-dive
    │   │   ├── CLVAnalysis.tsx             # Lifetime value analysis
    │   │   └── ChurnRiskMonitor.tsx        # Churn prediction dashboard
    │   ├── data/mockData.ts                # Segment data & metrics
    │   └── types/customer.ts               # TypeScript definitions
    └── package.json
```

## Getting Started

### Data Analysis

The complete analysis is available in the Jupyter notebook:

```bash
jupyter notebook ClientInsights.ipynb
```

The notebook covers:
1. Data loading and preprocessing
2. Feature engineering (RFM, engagement scores, channel preferences)
3. K-means clustering and segment profiling
4. Campaign response prediction (Random Forest, Gradient Boosting, Logistic Regression)
5. CLV calculation and Pareto analysis
6. Next Best Action recommendations
7. Churn risk stratification
8. ROI impact quantification

### Web Dashboard

Launch the interactive ROILab dashboard:

```bash
cd ui
npm install
npm run dev
```

The dashboard provides:
- **Campaign ROI Optimizer**: Compare current vs. optimized targeting strategies
- **Customer Segments**: Explore segment characteristics and revenue contribution
- **Lifetime Value Analysis**: Visualize CLV distribution and trends
- **Churn Risk Monitor**: Track at-risk customers and recovery opportunities

## Methodology

### Segmentation Approach
- **Algorithm**: K-means clustering with 5 clusters (optimized via silhouette analysis)
- **Features**: Income, spending, purchases, age, tenure, family size, AOV, web visits, deal sensitivity
- **Validation**: Silhouette score and business interpretability

### Predictive Modeling
- **Target**: Campaign response (binary classification)
- **Models Tested**: Logistic Regression, Random Forest, Gradient Boosting
- **Features**: Demographics, behavioral, RFM scores, segment membership
- **Validation**: ROC AUC, precision, recall, F1 score

### CLV Calculation
```
CLV = (Avg Order Value × Purchase Frequency × Customer Tenure) × Profit Margin
```
- Profit margin assumed at 20%
- RFM scoring on 1-5 quintile scale
- Segment-level aggregation

### Churn Risk Classification
- **High Risk**: No purchase in 75+ days
- **Medium Risk**: No purchase in 50-75 days
- **Low Risk**: Purchase within 50 days

## Strategic Recommendations

### Immediate Actions (Next 30 Days)
1. Implement targeted campaigns focusing on Affluent Singles and Budget-Conscious Families
2. Launch retention program for high-value at-risk customers
3. A/B test targeted vs. broadcast campaigns

### Medium-Term (3-6 Months)
1. Develop segment-specific product offerings
2. Optimize channel experience based on preferences
3. Refine predictive models with new campaign results

### Long-Term (6-12 Months)
1. Map complete customer journeys by segment
2. Design segment migration programs (move customers to higher-value segments)
3. Integrate with marketing automation platforms

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
