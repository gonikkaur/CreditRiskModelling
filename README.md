# Credit Risk Modelling

Minimum Capital Requirements with a financial institution comes with 3 risks:
1. Credit Risk
2. Operational Risk
3. Market Risk

Here we will focu on the credit risk segment, they can be based on two approaches:
1. Standardized Approad (SA): Giving loan on the basis of Credit scores calculated by the external firms like FICO, CIBIL etc.
2. Internal Rating Based Approachs (IRB): 
   1. Foundation Internal Rating Based (F-IRB) Approach
   2. Advanced Internal Rating Based (A-IRB) Approach

Expected loss (EL) is the amount that an institution expects to lose on a credit exposure over a given time horizon.

Expected Loss = Probability of Default x Loss Given Default x Exposure at Default
To calculate the Expected Loss we use Logistic Regression, and for LGD and EAD we use Linear Regression (Because Python doesn't support Beta Regression, o.w.Prefer using Beta regression in R) 

Model Performance
Model assessment is the final step in the model building process. It consists of three distinctive phases: evaluation, validation, and acceptance.

Evaluation for Accuracy
Did I build the model right? is the first question to ask in order the test the model. The key metrics assessed are statistical measures including model accuracy, complexity, error rate, model fitting statistics, variable statistics, significance values, and odds ratios.

Validation for Robustness
Did I build the right model? is the next question to ask when moving from classification accuracy and statistical assessment for ranking ability and business assessment.

The choice of validation metrics depends on the type of the model classifier. The most common metrics for binary classification problems are gains charts, lift charts, ROC curves, and Kolmogorov-Smirnov charts. The ROC curve is the most common tool for visualizing model performance. It is a multi-purpose tool used for:

Champion-challenger methodology to choose the best performing model.
Testing the model performances on unseen data and comparing it to the training data.
Selecting the optimal threshold, which maximizes the true positive rate and minimizes the false positive rate.
The ROC curve is created by plotting sensitivity against the probability of false alarm (false positive rate) at different thresholds. Assessing performance metrics at different thresholds is a desirable feature of the ROC curve. Different types of business problems will have different thresholds based on a business strategy.

The area under the ROC curve (AUC) is a useful measure that indicates the predictive ability of a classifier. In credit risk, an AUC of 0.75 or higher is the industry accepted standard and prerequisite to model acceptance.
Credit Score:
Advances in technology have enabled financial lenders to reduce lending risk by making use of a variety of data about customers. Using statistical and machine learning techniques, available data is analysed and boiled down to a single value known as a credit score representing the lending risk. This value can help guide the decision process. The higher the credit score the more confident a lender can be of the customer’s creditworthiness. Credit scoring is a form of Artificial Intelligence, based on predictive modelling, that assesses the likelihood of a customer defaulting on a credit obligation, becoming delinquent or insolvent. The predictive model “learns” from by utilising a customer’s historical data together with peer group data and other data to predict the probability of that customer displaying a defined behaviour in future.
Credit scoring can be utilised throughout the customer journey, spanning the entire customer experience during the length of the relationship between a customer and an organisation.
Different credit scores are utilised at different stages of the customer journey:
1.	Application score assesses the risk of default of new applicants when making decision whether to accept or reject the applicant.

2.	Behavioural score assess the risk of default associated with an existing customer when making decisions relating to account management such as credit limit, over-limit management, new products, and the like.

3.	Collections score is used in collections strategies for assessing the likelihood of customers in collections paying back the debt.
Using the KS, AUC-roc we decide that upto which probability the loan should be given and there will be the lowest false positive and false negatives
a.	KS or Kolmogorov-Smirnov chart: It measures performance of classification models. The KS statistic gives the separation power of the model. It is calculated as the maximum of the absolute value of the difference between cumulative non-event and cumulative event. A good model will have a KS > 30. A high value of KS will depict over-prediction in the model.
b.	AUROC curve: It is a fundamental tool for diagnostic test evaluation. It is plotted as a graph between sensitivity and 1-specificity, which we can get from the confusion matrix. 
c.	An ideal model will have AUROC very close to 1. 
d.	Lift is dependent on total response rate of the population, ROC curve on the other hand is almost independent of the response rate.
e.	Gini coefficient: It is the ratio between area between the ROC curve and the diagonal line and the area of the above triangle. Gini = 2 x AUC – 1
