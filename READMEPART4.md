Part 4: Short Answers

Q1: Handling Negative Package Weights

No, I would not immediately drop 25% of the dataset, as removing such a large portion of data could lead to significant information loss and introduce bias into the model. Since negative package weights are not physically meaningful, they most likely indicate a data quality issue, such as incorrect data entry or system errors.

Instead, I would take the following approach:

1. Investigate the root cause

- Analyze whether negative weights are concentrated within specific time periods, vendors, or data sources

- Determine whether the issue is systematic or caused by isolated anomalies


2. Apply a correction or imputation strategy. Depending on the findings, possible approaches include:

- Replacing negative values with a representative statistic (e.g., median of valid weights)

- Introducing a binary indicator feature (e.g., is_weight_corrected) to preserve information about data reliability

3. Drop rows only as a last resort
- If the values are clearly corrupted and cannot be reasonably corrected
- And only after confirming that removal does not introduce bias

This approach balances data integrity with preserving as much useful information as possible.

----- 
Q2: Evaluating Whether a Paid traffic_level Feature Is Worth the Cost

To determine whether the paid traffic_level feature justifies its cost, I would evaluate both its predictive value and business impact.

Step 1: Measure Predictive Value
I would compare model performance with and without the traffic_level feature using consistent evaluation metrics such as MAE or RMSE.
- If performance improvement is minimal, the feature may not justify the additional cost
- If it significantly reduces prediction error, it adds clear value

Step 2: Assess Business Impact
I would translate model performance improvements into business outcomes, such as:

- More accurate delivery time estimates
- Reduced customer complaints or support tickets

If a small reduction in error leads to customer satisfaction improvements, the feature may be justified.


Step 3: Explore Cost-Effective Alternatives
Before committing to a paid API, I would explore alternatives such as:

- Proxy variables (e.g. time of day, day of week)
- Cached or less granular traffic data
- Hybrid approaches where the API is only called for high-impact orders


Ultimately, the feature is worth the cost only if the incremental business value it provides outweighs the ongoing API expense. Otherwise, a simpler or approximate solution would be more sustainable.
