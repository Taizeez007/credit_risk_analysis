---Credit Risk Analysis Project
This project focuses on analyzing and predicting loan default using the hmeq.csv dataset. It includes exploratory data analysis, feature engineering, model training and evaluation, and model interpretation to identify the key drivers of credit risk.

Getting Started
These instructions will help you get a copy of the project up and running on your local machine for development and testing purposes.

Prerequisites
You will need Python 3.6 or higher and pip installed on your system.

Getting the Code
Clone the repository: Open your terminal or command prompt and run the following command, git clone https://github.com/**** the link can be copied in the repo

Install the requiremnts libraries and packages to run the code in your virtual environment using pip install -r requirements.txt. Ensure you have moved to your virtual environment before doing this. .venv\Scripts\activate will do

---Meaning of abbreviaitons from this project
HMEQ Dataset Columns Used for Modeling:

Here are the columns from the hmeq_df dataset that will be used as features for training the credit risk models:

BAD: Target variable (1 = applicant defaulted on loan or seriously delinquent; 0 = applicant paid loan). This column will be excluded from the features and used as the target.
LOAN: Amount of the loan request.
MORTDUE: Amount due on existing mortgage.
VALUE: Value of current property.
YOJ: Years at present job.
DEROG: Number of major derogatory reports.
DELINQ: Number of delinquent credit lines.
CLAGE: Age of oldest credit line in months.
NINQ: Number of recent credit inquiries.
CLNO: Number of credit lines.
DEBTINC: Debt-to-income ratio.
REASON_HomeImp: Binary feature indicating if the loan reason is Home Improvement (created from 'REASON').
JOB_Office: Binary feature for 'Office' job category (created from 'JOB').
JOB_Other: Binary feature for 'Other' job category (created from 'JOB').
JOB_ProfExe: Binary feature for 'Professional Executive' job category (created from 'JOB').
JOB_Sales: Binary feature for 'Sales' job category (created from 'JOB').
JOB_Self: Binary feature for 'Self' job category (created from 'JOB').
These features, after handling missing values and encoding, will be used to train the models to predict the BAD outcome.

###

Key Insights from the Analysis:

Significant Predictors of Default: Both the tree-based models (Random Forest and XGBoost) and Logistic 
Regression consistently identified certain features as strong indicators of loan default. The most 
prominent among these are:

DEBTINC (Debt-to-Income Ratio): A higher debt-to-income ratio is strongly associated with a higher 
likelihood of default.

DELINQ (Number of Delinquent Credit Lines): Applicants with a history of delinquencies are significantly
 more likely to default.

CLAGE (Age of Oldest Credit Line): A longer credit history (older credit lines) generally indicates 
lower risk, while newer credit histories or a lack of established credit are associated with higher 
default rates.

NINQ (Number of Recent Credit Inquiries): A high number of recent credit inquiries can suggest financial 
distress or an increased appetite for credit, both of which are linked to higher default risk.

Other Factors: Features like DEROG (derogatory reports), CLNO (number of credit lines), and property-related
features (VALUE, MORTDUE) also play a role, although their importance might vary slightly across models.

Impact of Job Type and Loan Reason: Our exploratory analysis showed that certain job types (like Sales and 
Self-employed) had a higher ratio of bad to good credit compared to others. Similarly, the reason for the 
loan (e.g., Home Improvement vs. Debt Consolidation) also showed different default patterns.

Model Performance: The tree-based models (Random Forest and XGBoost) demonstrated significantly better 
predictive performance (higher ROC AUC, Precision, Recall, and F1-Score) compared to the simpler Logistic 
Regression model. This suggests that the relationship between the features and loan default is likely 
non-linear and complex, which ensemble models are better at capturing.
Business Decisions and Recommendations:

Based on these insights, here are some actionable business decisions for credit risk management:

Strengthen Underwriting Focus: Prioritize the key risk factors identified (DEBTINC, DELINQ, CLAGE, NINQ)
 in your loan application review process. Implement stricter thresholds or guidelines for these features,
especially for applicants who score poorly on multiple indicators.

Enhance Data Collection: Ensure accurate and complete data collection for the identified key features. 
Missing or inaccurate data can hinder the effectiveness of the risk assessment models.

Develop Risk-Based Pricing: Utilize the model's predicted probability of default to implement risk-based 
pricing for loans. Applicants with a higher predicted risk could be offered loans with higher interest 
rates to compensate for the increased risk, while lower-risk applicants could receive more favorable terms.

Automate Risk Assessment: Integrate the trained and validated predictive model into an automated credit risk
 assessment system. This can streamline the application process, ensure consistency in risk evaluation, and 
 allow for faster decision-making.

Implement Early Warning Systems: Use the model to monitor existing loan portfolios and identify loans that 
are at a higher risk of future default based on changes in borrower behavior or external factors (if such 
data becomes available). This can enable proactive intervention strategies.

Tailor Product Offerings: Consider tailoring loan products or offering specific support (e.g., financial 
literacy resources) to applicants who present higher risk profiles based on the model's predictions.

Continuously Monitor and Retrain: Regularly monitor the model's performance on new data and retrain it 
periodically to ensure it remains accurate and relevant as economic conditions and borrower behaviors 
change.

By leveraging the insights from this analysis and implementing these recommendations, lenders can make 
more informed decisions, reduce potential losses from defaults, and improve the overall health of their 
loan portfolio.

###
