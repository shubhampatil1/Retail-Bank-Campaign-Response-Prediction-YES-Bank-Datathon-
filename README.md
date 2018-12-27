# Retail Bank Campaign Response Prediction-YES Bank Datathon 

## Data Description:
<p>The data given is of campaigns run by a retail bank. Objective of the problem is to predict the categorical outcome of each entity in the test data set. “outcome” variable is to be predicted as per “serial_number” variable of the test data set. From exploratory data analysis, it is seen that the data is imbalanced. The ratio of positive class in target variable is 5.8% which is vary low. Imbalaced data leads to baised model so we need consider oversampling methods to get rid of this problem. </p> 

###### Outcome Factors ratio

![Screenshot](https://github.com/shubhampatil1/Retail-Bank-Campaign-Response-Prediction-YES-Bank-Datathon-/blob/master/outcome%20factors%20ratio%20file.png)

## Variables Dictionary

   - serial_number: Unique identifier for each entity.
   - age_in_years: Age in number of years of the individuals targeted.
   - job_description: Categorical variable which describes the job held by each individual.
   - marital_status: Categorical variable which describes the marital status of the individual.
   - educational_status: Categorical variable which describes the educational status of the individual
   - has_default: Binary variable which describes if the individual has a previous loan default.
   - balance_in_account: Numerical variable which describes the average yearly balance of the account. (units of currency)
   - housing_status: Binary variable which describes if the individual has previous housing loan existing.
   - previous_loan: Binary variable which describes if the individual has previous previous personal loan existing.
   - phone_type: Type of phone on which the individual was contacted.
   - date: Day of the month on which the individual was contacted.
   - month_of_year: Categorical variable which describes the month of the year on which the individual was contacted.
   - call_duration: Contact duration in number of seconds on the last campaign call.
   - campaign_contacts: Number of days from the previous campaign after which the individual was contacted. -1 signifies that no previous                         contact is on record.
   - days_passed: Total number of contacts to this individual before the current campaign started.
   - previous_contact: Number of previous contacts on the previous marketing campaign
   - outcome_of_the_campaign: Categorical variable that describes the outcome of the previous campaign.
   - outcome: Binary outcome of the current campaign.
   
## Data Preparation:

- The data set does not have any missing values so missing value treatmeant is not required.
- Target variable "outcome" is in categorical form 'yes' 'no' so variable encoding is done as per the requirement and new variable outcome_bin is created.
- Variables has_default, housing_status, previous_loan consists of two factors which can be encoded to '0' '1' form to avoide extra dummy variables.
- Factors reduction is done for the variables job description, education_details, month_of_year, poutcome_of_campaign based on target variable "outcome_bin".
- It is found that test and train data sets contain different number of classes so both data sets are concatinated and dummy variables are created. After creating dummy variables test & train data sets are separated.
- Since the train data is imbalanced, oversampling is introduced by using SMOTE.

## Modeling Technique Used:

- Random forest classifier

## Packages Required

- Sklearn
- Imblearn
- Matplotlib
- Pandas
- Numpy
- OS

## Results

- Random Forest classifier score: 97.2%
- Out of Bag error score: 97.3%
