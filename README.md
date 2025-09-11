# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

# Project: Healthcare Insurance Costs Analysis 

# Business Rationale

Health insurance company, understanding their customer base and cost to determine accurate/fair pricing. Potentially target high risk cases for health campaigns.

## Hypotheses we checked:

* High-risk cases will pay more for health insurance (smoking, unhealthy weight, elderly),  
* Risk factors will combine (e.g. being older, overweight, and a smoker) to further increase costs.  
* Smokers will pay more for health insurance.  
* Health insurance costs will increase with age.  
* Overweight and obese categories will pay more for health insurance.  
* Region may impact health insurance costs (some regions may have more high-risk cases).  
* The North-east is likely to have higher insurance costs.  
* Number of children may influence insurance costs.  
* A person’s sex may affect how much they are charged.

# Dataset 

This project uses publicly available data from Kaggle. It  contains information about a person's age, gender, body mass index (BMI), number of children, smoking status, and region in connection to their healthcare insurance costs.

# Ethical and legal considerations

No ethical issues, the dataset is publicly available on Kaggle and used for training purposes only.

# Main data analysis libraries

Pandas (for data cleaning, manipulation and data visualisation and exploration), NumPy (for numerical operations), SciPy (for statistical functions), and Statsmodels (for modelling and hypothesis testing).

# Dashboard Design

The main dashboard was developed in Power BI, enabling interactive exploration, predictive forecasting, and the delivery of stakeholder friendly insights.

## What we found and the tests done.

### Hypotheses Confirmed

* Smokers pay more  
  *Tests:* Group comparisons, regression and Power BI.  
  *Result:* Confirmed. Smokers pay on average \~£23.8k more in the regression model and Power BI key influencers on average \~£23.61k , very significant.

* Costs increase with age  
  *Tests:* Regression, ANOVA, grouped summaries.  
  *Result:* Confirmed. \~£257 more per year of age, highly significant.

* BMI (overweight/obese) increases costs  
  *Tests:* Regression, ANOVA, grouped summaries by category.  
  *Result:* Confirmed. \~£336 more per BMI unit. Obese categories show much higher charges.

* High-risk cases pay more (elderly, smokers, overweight)  
  *Tests:* Outlier analysis (IQR \+ \>£40k threshold)\*  
  *Result:* Confirmed. All high-cost outliers had at least 2 of these 3 risk factors.

* Risk factors combine to increase costs  
  *Tests:* Outlier drilldown, regression with multiple predictors.  
  *Result:* Confirmed. Combined effects (e.g. older \+ obese \+ smoker) clearly drive the very high charges.

**\*Note: Outliers were identified using two approaches:**

* Statistical method: the IQR rule flagged extreme values.  
* A theoretical business rule was applied: a £40k threshold was applied to filter “High Cost” cases for Power BI reporting.

We recommend further stakeholder discussions on how these outliers should be treated in business reporting, as they have a significant impact on averages and risk estimates. 

### Hypotheses Partially Supported

### Tests:

### Group summaries / descriptive statistics

* Looked at mean and median charges by region.  
* Compared distributions of BMI and smoking rates across regions. 

### ANOVA (Analysis of Variance)

* Tested whether mean charges differed significantly between regions.

###  Regression including region as a categorical variable

* Checked if regional effects remained significant once controlling for other risk factors (age, BMI, smoking, children, sex).

* Found that region dropped out as not significant when adjusting for those factors.

* Number of children affects costs  
  *Tests:* ANOVA, regression.  
  *Result:* Mixed. 2 and 4 children showed significant increase; other categories not significant (likely due to small sample sizes).

* Region affects costs  
  *Tests:* ANOVA, group comparisons.  
  *Result:* Some differences in distribution of BMI and smokers by region, but not strong or consistent effects on charges overall.

## Hypotheses Not Strongly Supported

* North-East has higher costs  
  *Tests:* Regional comparisons.  
  *Result:* Not clearly supported. North-East wasn’t consistently higher once controlling for risk factors.

### Regional differences found:

* The North-East showed higher average charges.

* The South-East had more high-risk factors (e.g. smokers, higher BMI), but this did not translate into higher charges.

* Sex affects charges  
  *Tests:* Regression, group means.  
  *Result:* Not significant. No evidence of sex driving cost differences.

## Visualisation Analysis

Hypothesis findings were supported through Power BI visualisation analysis, using a range of tools to explore and confirm patterns in the data:

* Clustered column charts – to compare average, minimum, and maximum charges across categories such as smoker status, BMI, and age bands.

* Reporting tables with conditional formatting to show detailed breakdowns of average charges by region, BMI mix, and age distribution.

* Histograms to show the distribution of charges and highlight right-skew and outliers.

* Pie and bar charts to illustrate regional shares, BMI categories, child counts, and sex distributions.

* Key Influencers / Top Segments analysis to identify the strongest drivers of high charges and segment populations by risk.

* High cost case analysis visuals – to filter and drill into “High Cost” cases (\>£40k) by age band and BMI category.

## Additional Findings

* **Charges distribution:** Strongly right-skewed. Median much lower than mean, showing outlier influence.

* **Outliers:** Identified using IQR \+ business rule (\>£40k). All linked to smoking, high BMI, and/or age.

## Recommendation: 

Stakeholders should decide how to treat outliers in reporting, as these materially affect averages and risk estimates. The highest risk and cost factors for health campaigns are smoking, high BMI, and age, with smoking emerging as the single most significant driver of charges.

# Credits

We received support from our tutor Vasi Pavaloi for resolving project issues and understanding how to complete tasks.

We used Chat GPT 4.0 and GitHub CoPilot to help with problems, explain errors, and explore different ways to write and (or improve) functions and code.

