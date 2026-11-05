# Customer Feedback & Satisfaction Analysis

Analysis of 38,444 customer records in Google Sheets to find out what drives customer satisfaction and whether loyalty tier or purchase frequency matter.

**Headline result:** of the factors tested, perceived product and service quality are the only ones tied to satisfaction. Loyalty tier and purchase frequency show no meaningful relationship with it.

## Key Findings

- **Quality drives satisfaction.** The share of highly satisfied customers (score 76-100) rises from **37.5%** among customers who rated product quality 1 to **97.7%** among those who rated it 10. Service quality shows the same pattern (**36.3% to 97.8%**). Correlation with satisfaction score is moderate for both (product r = 0.548, service r = 0.554).
- **Low ratings are the biggest opportunity.** About 40% of customers rate product quality 1-4, and about 40% rate service quality 1-4. Only around 20% rate either at 9-10.
- **Loyalty tier does not predict satisfaction.** The share of highly satisfied customers is 74.0% (Bronze), 73.8% (Silver), and 73.4% (Gold).
- **Loyalty tiers rate quality similarly.** Roughly 20% of each tier rates product and service quality 9-10, so top ratings are not concentrated in any one segment.
- **Purchase frequency shows no clear link** to loyalty tier or to feedback category (Low/Medium/High). Each group splits roughly evenly.

## Business Recommendations

1. **Prioritize the lowest-rated products and services.** Customers rating quality 1-4 make up about 40% of the base, and only 37-65% of them are highly satisfied, compared with 88%+ of those rating 7 or higher.
2. **Don't rely on loyalty tier as a proxy for satisfaction.** Gold customers are no more satisfied than Bronze, so tier-based perks alone are unlikely to move satisfaction.
3. **Look beyond purchase frequency.** It did not explain feedback or loyalty differences. Factors such as price, convenience, and product availability would need additional data.

## Dataset

- **Dataset:** Customer Feedback and Satisfaction
- **Author:** Jahnavi Paliwal (Kaggle, 2024)
- **Link:** https://www.kaggle.com/datasets/jahnavipaliwal/customer-feedback-and-satisfaction
- **License:** Apache 2.0 
- **Size:** 38,444 customer records

Key fields: CustomerID, Age, LoyaltyLevel (Bronze/Silver/Gold), PurchaseFrequency, ProductQuality (1-10), ServiceQuality (1-10), FeedbackScore (Low/Medium/High), and SatisfactionScore.

Summary statistics: average purchase frequency 10.45, average product quality 5.49, average service quality 5.49, average satisfaction score 85.28 (range 4-100).

**Note on the data:** the distributions are almost perfectly uniform (loyalty tiers about 33% each, feedback categories about 33% each, purchase frequency groups about 25% each), which suggests the dataset is synthetic. This explains why several variables show no relationship, and the findings should be read as an exercise in method rather than conclusions about a real business.

## Method

1. Loaded the dataset into Google Sheets. 

	- Removed duplicates
	- Rounded satisfaction scores to the nearest whole number
     (SatisfactionScore_Round)
	- Calculated summary statistics (averages and correlations).
	- Doing a Purchase Frequency group (1-5, 6-10, 11-15, 16-20)

2. Built pivot tables showing each group as a percentage of customers (count of CustomerID). Values were grouped directly in the pivot tables.
   - Satisfaction score: 1-25, 26-50, 51-75, 76-100
   - Quality ratings (loyalty tables): 1-4, 5-8, 9-10
   - Age: 10-year bands (18-27 through 68-77)
  
3. Compared distributions across quality ratings, loyalty tiers, and purchase frequency groups, and calculated correlations between quality ratings and satisfaction score.
4. Charted the key comparisons and wrote up findings and recommendations.

## Limitations

- The data appears synthetic, so results may not reflect real customer behavior.
- Correlation does not imply causation: quality ratings are associated with satisfaction, but this analysis cannot show that improving quality would raise it.
- Quality ratings explain only part of satisfaction (r of about 0.55, or roughly 30% of the variation), so other drivers are not captured in this dataset.
- Similarity across groups was assessed by comparing percentages, not with formal statistical tests.

## Repository Contents

- `README.md`: Project Summary
- PDF of pivot tables and the Word document of findings and recommendations
- exported copy of the working sheet (.xlsx)

## Tools

Google Sheets (analysis, pivot tables, charts) and Google Docs (written findings).
