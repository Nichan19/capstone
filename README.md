# Capstone Project "AI-Driven Marketing Channels Optimization and identification for Maximizing Paid Media ROI." Final Project

## Problem Statement
Identifying which channels to invest at Salesforce Marketing Department is a big challenge. The multi million budget spending requires strong data driven insights to identify which paid advertising channel is more viable to ROI. The goal is to identify where to invest more and identify data backed scalable long term efficiency strategies.

## Model Outcome and Prediction
This analysis tries to classify and predict an ideal investment methodology and process for advertising channels. The project is based on the CRISP-DM methodology.

## Data Acquisition
Data is representing 3 years of advertising channels data with their hirarchical KPIs such as impressions, clicks, conversions, leads, MQLs, SALs, Opportunities Stage 1 and Stage 2 and last but not least ACV. The dataset has been downloaded from Snowflake table connected to Salesforce CRM. The data is representing 3 years of KPIs downloaded on advertising channels segments level.

## Contents:  
1- Understand the Data and Import Necessary Libraries  
2- Read In and Explore the Data  
3- Data Visualization and Analysis  
4- Cleaning Data  
5- Data Modeling and Evaluation  
6- Choosing the Best Model - Model Comparison  
7- Scoring and Improving the Model  
8- Providing Best Business Recommendations  

## Findings:  
ROI doesn't seem to be correctly capturing properly everything based on current business domain knowledge. I will try o future engineer further to adjust the dataset for a better performance

## Initial Data Assessment Summary  
- The dataset has 41,864 rows and 34 columns  
- Impute missing values in partially missing columns like CAMPAIGN_INDUSTRY and CAMPAIGN_L1_PRODUCT  
- Standardize and add additional column names.

## Hypothesis:
If a channel has high funnel value but low ROI, it may be worth optimizing (e.g., reduce cost or improve conversion).
If a channel has high ROI but low funnel value, it's efficient but not moving the needle. We need to consider scaling it.

## Closer look to the clusters performance
We have grouped your marketing rows (channels, accounts, etc.) into 2 distinct behavior profiles.
The PCA plot shows how separated the clusters are, it is a good sign as they are separated.

## Learnings:  
We trained a Logistic Regression and a Ridge Classifier to predict CLUSTER (campaign group).  
This table shows the coefficients of each feature in the models.  

##Outcome:  
Higher absolute values mean more influence on the classification outcome.

#Insights:  
- STAGE_1 and STAGE_2 Opportunities are the most predictive features across both models.  
- WON_OPPORTUNITY has a weaker signal, possibly due to multicollinearity with STAGE_2.  
- MQLS and RESPONSES contribute very little predictive power.  
- MEDIA_COST has almost no predictive weight and can likely be dropped for modeling.

## Conclusions:  
Model results indicate that campaign clusters are primarily driven by conversion-stage outcomes such as stage 1/2 opportunities and won deals. Early funnel engagement (clicks, impressions) and media cost show negligible influence, suggesting that investment should prioritize campaigns with proven downstream performance rather than just volume metrics.  

## Final Takeaways:     
Final business recommendation summary based on the funnel conversion rates, cost efficiency, and opportunity volume:  
  
1. Review Sites  
Strengths: Strong funnel progression, especially from Stage 2 to Won. Low cost per win (~$1,484). Balanced tactic.  
Weaknesses: Moderate top-of-funnel scale.  
Recommendation: Keep and cautiously scale. It's efficient and reliably delivers wins. Ideal for targeted investment.  
  
2. SEM  
Strengths: High volume at every stage. Delivers the highest number of won opps (6,150).  
Weaknesses: Higher cost per Stage 2 opp (~$2,244). Weak ROI_SALES_FOCUSED.  
Recommendation: Keep as a volume engine, but audit keyword/ad set performance to cut waste. Optimize for better bottom-funnel payoff.  

3. Paid Social  
Strengths: Very strong Stage 2-to-Won conversion. Low cost per win (~$778).  
Weaknesses: Leaky mid-funnel (weaker conversion from Valid Leads to Stage 1). Composite score is modest.  
Recommendation: Refine mid-funnel targeting. Great potential if nurtured properly.  
  
4. Display  
Strengths: Reasonable conversion into Stage 2.  
Weaknesses: Very few wins (only 306). Inefficient relative to spend. Mid-tier composite performance.  
Recommendation: Limit spend or reserve for retargeting only. Reevaluate creative and audience alignment.  
  
5. Content Syndication  
Strengths: Massive top-of-funnel volume.  
Weaknesses: Terrible funnel efficiency. High spend with weak win volume. Low composite score.  
Recommendation: Aggressively cut or rebuild. Only keep specific vendors showing real opp conversion.  
  
6. Third Party Email  
Strengths: Best log-weighted ROI and lowest cost per win (~$323).  
Weaknesses: Extremely weak volume (only 85 wins). Poor Stage 1 and 2 conversion.  
Recommendation: Niche tactic. Use only with verified, high-intent lists. Do not scale broadly.  
  
## Strategic Takeaways  
Focus investment on Review Sites and SEM for reliable wins and funnel stability.  
Use Paid Social as a scalable low-CAC source — but plug funnel leaks.  
Display and Content Syndication need aggressive cleanup — too costly for current return.  
Third Party Email is only worth running on precision-targeted campaigns.
