### COVID19 Risk Prediction

**Author**
Venkata Suresh Gummadilli 

#### Executive summary
The objective of this project is to detect more effective ways for detecting people who are at risk of COVID19 by identifying and evaluating the best model for COVID19 risk detection through patients medicals history and health conditions. We will be training and tuning classification models to accurately classify whether a patient is at risk or not. Models will be able to predict from various patients medical conditions, covid test results and chronic health diseases. 

#### Findings: 
The best model for detection COVID19 Risk is Decision Tree model with an accuracy of 0.89, a recall 0.95 of and F-1 of 0.89. Its performance is followed by Decision Tree model, K-Nearest Neighbour, Logistic regression and Naive Bayes model. The decision is based on the best accuracy, recall and F1 score of the models as shown in the below.

![Screenshot 2023-07-07 at 1 05 45 AM](https://github.com/sureshgv/UCB-CapStone-Project/assets/1572856/c5e0b1ab-e402-4bb6-9274-533034b4da66)

#### Results and conclusion


#### Rationale
During the entire course of the pandemic, one of the main problems that healthcare providers have faced is the shortage of medical resources and a proper plan to efficiently distribute them. In these tough times, being able to predict what kind of resource an individual might require at the time of being tested positive or even before that will be of immense help to the authorities as they would be able to procure and arrange for the resources necessary to save the life of that patient.

The main goal of this project is to build a machine learning model that, given a Covid-19 patient's current symptom, status, and medical history, will predict whether the patient is in high risk or not.


#### Research Question
The objective of this project is to identify the optimal classification model for identifying patients at risk for COVID-19.

#### Data Sources
The COVID19 dataset is taken from Kaggle and was provided by the Mexican government (link). This dataset contains an enormous number of anonymized patient-related information including pre-conditions. The raw dataset consists of 21 unique features and 1,048,576 unique patients. In the Boolean features, 1 means "yes" and 2 means "no". values as 97 and 99 are missing data.

Patients medical history, Covid test findings, any chronic diseases and other healthy habits can be used to determine if the patient is at high risk or not. 

##### Exploratory data analysis: 
There are no null values in this data but there are few values where numbers 99, 97, 98 missing records for that specific records. We did cleaned up these things case by case.

##### Cleaning and preparation: 
After the correlation matrix, several columns are dropped as they dont have lot of impact on COVID risk. 
Several columns like SEX,PREGNANT,COPD,ASTHMA,INMSUPR,OTHER_DISEASE,CARDIOVASCULAR,OBESITY,TOBACCO are dropped as they have less correction with the Covid19 risk. 

The unique ID column was dropped because it adds no meaningful information to the analysis. The "class" column was renamed "suicide", and its values numerically represented by designating the "suicide" class as 1 and the "non-suicide" class 0.



#### Methodology
In this project, I have used various machine learning models as follows:
* Logistic Regression
* K-Nearest Neighbors
* Decision Tree
* Random Forests
* Naive Bayes

What methods are you using to answer the question?

#### Results
* Old people are at high risk for COVID19
* People with Pneumonia are at high risk
* People with chronic disesases like diabetes, hypertension are also at the risk of Covid
* Pregnant women are at low risk of COVID19 

What did your research find?

#### Next steps
What suggestions do you have for next steps?

#### Outline of project

- [Analysis & Model selection Notebook](https://github.com/sureshgv/UCB-CapStone-Project/blob/main/covid19-high-risk-prediction.ipynb)


##### Contact and Further Information
gvs.114@gmail.com
