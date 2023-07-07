### COVID19 Risk Prediction

**Author**
Venkata Suresh Gummadilli 

#### Executive summary
The objective of this project is to detect more effective ways for detecting people who are at risk of COVID19 by identifying and evaluating the best model for COVID19 risk detection through patients medicals history and health conditions. We will be training and tuning classification models to accurately classify whether a patient is at risk or not. Models will be able to predict from various patients medical conditions, covid test results and chronic health diseases. While our model evalution gave the best model, the model also provided features of higher importance. These additional features helped futher to identity high of the patients.

#### Findings: 
The best model for detection COVID19 Risk is Random Forest model with an accuracy of 0.89, a recall 0.95 of and F-1 of 0.89. Its performance is followed by Decision Tree model, K-Nearest Neighbour, Logistic regression and Naive Bayes model. The decision is based on the best accuracy, recall and F1 score of the models as shown in the below.

![Screenshot 2023-07-07 at 1 44 03 AM](https://github.com/sureshgv/UCB-CapStone-Project/assets/1572856/108ecff8-febb-4451-81d8-bc90964ba3c0)


#### Results and conclusion
Our evaluation of the best model returned some features of importance. These features are very helpful to find a patient is at high risk or not. The top 5 features for best model is as follows:

| Feature Name | Score |
| ------- | --- |
| PATIENT_TYPE | 0.5738453452374209 |
|PNEUMONIA|0.24827651295809022|
|AGE|0.14527962392496763|
|DIABETES| 0.014647142028060979|
|HIPERTENSION| 0.017951375851460307|

The patients who are hospitalized and heave other health conditions like pnemonia, diabetes, hipertension and diabetes are at high risk for the covid. Few other findings include, old people are more impacted than younger ones. Similarly, people with obesity have higher risk than normal people. One the otherside, pregnant women have low risk.
In conclusion, old people, people with chronic health conditions, obesity issues people are at higher risk.

#### Future research and development
The existing dataset focuses on one country, prompting curiosity regarding the potential impact of diverse factors such as different countries, climates, and food habits on individuals' COVID-19 risk. Exploring correlated features from various dimensions, such as genetics, urban versus rural environments, and others, could provide valuable insights into assessing risk levels. By expanding our understanding in these areas, we can enhance our ability to provide better assistance and support to individuals based on their specific risk profiles.

#### Rationale
During the entire course of the pandemic, one of the main problems that healthcare providers have faced is the shortage of medical resources and a proper plan to efficiently distribute them. In these tough times, being able to predict what kind of resource an individual might require at the time of being tested positive or even before that will be of immense help to the authorities as they would be able to procure and arrange for the resources necessary to save the life of that patient.

The main goal of this project is to build a machine learning model that, given a Covid-19 patient's current symptom, status, and medical history, will predict whether the patient is in high risk or not.

#### Research Question
The objective of this project is to identify the optimal classification model for identifying patients at risk for COVID-19.

#### Data Sources
**Dataset:** The dataset used in this project is sourced from Kaggle and can be accessed at 
https://www.kaggle.com/datasets/meirnizri/covid19-dataset

The COVID19 dataset is taken from Kaggle and was provided by the Mexican government. This dataset contains an enormous number of anonymized patient-related information including pre-conditions. The raw dataset consists of 21 unique features and 1,048,576 unique patients. In the Boolean features, 1 means "yes" and 2 means "no". values as 97 and 99 are missing data.

Patients medical history, Covid test findings, any chronic diseases and other healthy habits can be used to determine if the patient is at high risk or not. 

##### Exploratory data analysis: 
There are no null values in this data but there are few values where numbers 99, 97, 98 missing records for that specific records. We did cleaned up these things case by case.

##### Cleaning and preparation: 
After the correlation matrix, several columns are dropped as they dont have lot of impact on COVID risk. 
Several columns like SEX,PREGNANT,COPD,ASTHMA,INMSUPR,OTHER_DISEASE,CARDIOVASCULAR,OBESITY,TOBACCO are dropped as they have less correction with the Covid19 risk. 

##### Preprocessing
Preprocessing includes combining on the DEATH, INTUBED and ICU as AT_RISK. Also,label some of the values to 0 or 1 based on the column data. We also used some random sampling technique to have a more balanced data set,

##### Final Data set
Finally, we have balanced data set necessary for training several models.

![Screenshot 2023-07-07 at 2 37 22 AM](https://github.com/sureshgv/UCB-CapStone-Project/assets/1572856/1552038a-7ba0-4744-ba9a-8d2c809e85fc)


#### Methodology
The models were trained on the training set and evaluated using the test set. To optimize the performance of each model, RandomizedSearchCV was employed to fine-tune the hyperparameters, aiming to maximize the accuracy score. Accuracy was chosen as the evaluation metric because we have a balanced dataset, and it quantifies the proportion of correctly predicted observations out of the total number of observations.

* Logistic Regression
A pipeline object is created to standardize the data using Standardscalar and instantiate a Logistic Regression model. RandomizedSearchCV is used to find (1) the optimal penlaty, with the options being ['l2'] and (2) whether an intercept term should be included (options: [True, False]). The best model has l2 penalty and an intercept term.
* K-Nearest Neighbors
A pipeline object is created to standardize the data using Standardscalar and instantiate a Knearest Neighbor  model with neighbors [3, 5, 7], weights as [uniform, distance]. The best model has uniform and p as 1.
* Decision Tree
A pipeline object is created to standardize the data using Standardscalar and instantiate a Decision Tree Classifier with criterian [gini, entropy], max depth [None, 1, 2, 3 4] and sample split [1,2,3,4]. 
* Random Forests
  Similarly, a pipeline object created with select k best (10), Standard Scalar and Random Forest Classfier with max_depth [None, 5, 10], min samples split [2,5,10] and criterion [gini, entropy]. 
* Naive Bayes
  A pipeline object created using GaussianNB model, this model does not have lot of turning params.

#### Results

 **Random Forest Tree model** with an accuracy of 0.89, a recall 0.95 of and F-1 of 0.89. Out of all models, Random Forest has better acuuracy, precision and recall values. We can also see the confusion matrix below.
 ![Screenshot 2023-07-07 at 2 29 27 AM](https://github.com/sureshgv/UCB-CapStone-Project/assets/1572856/498cab9c-1f41-4af3-bec0-4bfe1c4b194d)

 **Decision Tree Model** comes next with accuracy of 0.88, a recall of 0.94 and F-1 score 0.89
 ![Screenshot 2023-07-07 at 2 30 08 AM](https://github.com/sureshgv/UCB-CapStone-Project/assets/1572856/bf6958ab-552e-411f-8303-0d372e0ad730)

Other metrics can be found here:
![Screenshot 2023-07-07 at 1 44 03 AM](https://github.com/sureshgv/UCB-CapStone-Project/assets/1572856/108ecff8-febb-4451-81d8-bc90964ba3c0)

Additional findings from the analysis indicate that certain groups are at higher or lower risk for COVID-19:

Older individuals have a higher risk of contracting COVID-19.
People with pneumonia are also at an increased risk.
Individuals with chronic diseases such as diabetes and hypertension have a higher susceptibility to COVID-19.
Interestingly, pregnant women are found to have a lower risk of COVID-19.
These findings provide valuable insights into the risk factors associated with COVID-19 and can help guide targeted prevention and mitigation strategies for different populations.


#### Next steps
Furthermore, there is room for additional improvements in enhancing the performance of the selected classification model. The best model can be extended by exploring further fine-tuning options or considering alternative algorithms and techniques. For instance, ensemble methods or recurrent neural networks could be incorporated to potentially yield better results. It would be beneficial to investigate the importance of features and their weights assigned not only by the Random Forest model but also by the Logistic Regression, Decision Tree, and Naive Bayes models, thus ensuring robustness and reliability of the findings. By delving into these avenues, we can gain a deeper understanding of the predictive power of different models and potentially uncover new insights.

#### Outline of project

- [Analysis & Model selection Notebook](https://github.com/sureshgv/UCB-CapStone-Project/blob/main/covid19-high-risk-prediction.ipynb)


##### Contact and Further Information
gvs.114@gmail.com
