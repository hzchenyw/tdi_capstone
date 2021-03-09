# TDI Capstone Project: Predict the Lengths of Stay (LOS)

## Why is it important to predict the lengths of Stay (LOS)?
- A metric for provider reimbursement and healthcare quality .
- Medicare reimbursement, the Inpatient Prospective Payment System Rule (IPPS), determines payments by case, not days of stay. Thus, hospitals would like to identify patients with high LOS risk.
- Help with the logistics of the hospital: optimizing patient flow, minimal waiting, minimal exposure to risks associated with hospitalization, and efficient use of resources such as hospital beds, medical equipment and available clinical staff.

## Dataset
- The project origantes from the kaggle challenge https://www.kaggle.com/nehaprabhavalkar/av-healthcare-analytics-ii
- Features on hospital include: hospital code, hospital type code, city code, region code and availbale extra rooms.
- Features on patients include: department, ward type, ward facility code, bed grade, patient ID, city code, type of admission, severity of illness, visitors with patient, age and admission deposit.  
- Output predictor stay is in 10 days' intervals.  

## Model Development
- Data wranglling: replace NA's with the mode and encode categorical varaibles.
- Since the output varibale stay is a categorical variable, I used descision tree model as my baseline. The descision tree reports 40% accuracy.
- Then I applied random forest and boosting algorithm to see if I can improve the performance of the model. GridsearchCV is used to find best parameters. The final model using random forest reports 42.1% accuracy and the final model with boosting algorithm does not have siginificant improvement, which also reports 42.1% accuracy.

## Predictions
- The ML pipeline can be applied to the test data set.
- Since many variables like hospital code, city and ward type are coded due to the original dataset, here I chose 4 categorical varibales (deaprtment, severity of illness, type of admission, and age) which have real meaning and can be used in daily business. In the Tableau dashboard, you can select on these 4 variables and see the predicted lengths of stay from my boosting algorithm model.

Tableau visulization of the LOS and predictions: https://public.tableau.com/profile/yiwenhz#!/vizhome/Capstone_16134903737260/Story1?publish=yes
Data processing and model development are in capstone.ipynb 
