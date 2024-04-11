![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/fraudDectionIcon.jpg)

# ONLINE PAYMENT FRAUD DETECTION MODEL


## PROJECT DESCRIPTION

Our model acts as a digital detective, trained to distinguish between regular online payment transactions and potentially fraudulent ones. It scrutinises each transaction's details—such as the money involved, the account's historical balance, and the transaction's origin or destination — to determine its legitimacy. Utilising advanced algorithms, akin to a detective piecing together clues from a crime scene, the model predicts whether a transaction is genuine or if it's an attempt at fraud. This process helps safeguard online financial activities, ensuring users' transactions are secure and trustworthy. By analysing patterns from vast amounts of data, the model learns to identify the subtle signs of fraud that might escape the human eye, making it an essential tool in the fight against digital financial crimes.


## DATA

We used a dataset that contains information on hundreds of thousands of online transactions, including whether they were fraudulent or not. This data includes details like the amount of money involved, the accounts sending and receiving the money, and when the transactions took place. The dataset was generously made available by Kaggle, and you can find it here. [https://www.kaggle.com/datasets/pankajtiwari2003/fraudlent-transaction]


## MODEL 

This modesl serve as the brain of our digital detective, interpreting complex data to make smart decisions swiftly. We employ multiple machine learning models, including RandomForestClassifier and DecisionTreeClassifier, optimised via GridSearchCV, BayesSearchCV, and RandomizedSearchCV. Decision Tree model was chosen for its transparency in decision-making, which is crucial for establishing trust when managing financial transactions. 

A significant part of the analysis involves feature importance analysis, hypothesis testing for predictor significance, and stacking classifiers to improve prediction accuracy. All chosen models excel in classification tasks.


## HYPERPARAMETER OPTIMSATION

Hyperparameters are like the settings on a detective's toolkit, adjusting how thorough or quick the investigation is. We utlised various methods such as BaySearchCV and RandomizedSearchCV, which systematically tries out different combinations of settings to find the optimal ones. This ensures our digital detective is not only smart but also efficient, using its resources wisely to catch fraudsters.

RandomForestClassifier (BayesSearchCV): to grow a magical forest where the trees are classifiers that help us decide between different choices
- 'max_depth'= 11: plant our trees with a certain depth (11 layers of branches)
- 'min_samples_leaf' = 1: each leaf has at least one piece of information before making a decision
- 'min_samples_split' =  10: split the branches when we have at least 10 pieces of information
- 'n_estimators' = 143: to grow 143 trees in our forest



## RESULTS

Given the prevalence of class imbalance in fraud detection datasets—where fraudulent transactions are significantly outnumbered by legitimate ones—our evaluation metrics are chosen to provide insight into the model's true predictive power:

| Model                                | Accuracy (%) | Precision | Recall | F1-Score | PR AUC | ROC AUC |
|--------------------------------------|--------------|-----------|--------|----------|--------|---------|
| Logistic Regression (GridSearchCV)   | 99.89        | 1         | 1      | 1        | 0.02   | 0.92    |
|** RandomForest (BayesSearchCV) **        | 99.93        | 1         | 1      | 1        | 0.6    | 0.96  |
|** RandomForest (RandomizedSearchCV) **    | 99.93        | 1         | 1      | 1        | 0.57   | 0.89 |
| DecisionTree (GridSearchCV)          | 99.91        | 1         | 1      | 1        | 0.43   | 0.88    |
| Stacked Model                        | 99.9         | 1         | 1      | 1        | 0.54   | 0.95    |

* Accuracy: While all model variants report an accuracy exceeding 99.89%, this metric can be misleading in the context of a biased dataset. High accuracy might reflect the underlying class distribution rather than the model's ability to detect fraud.
* Precision, Recall, & F1-Score: Scores of 1 across these metrics indicate exceptional model performance; however, these should be interpreted with caution due to the possibility of overfitting to the majority class.
* PR AUC: The Random Forest model optimised with BayesSearchCV shows the highest PR AUC of 0.60. In imbalanced datasets, the PR AUC is a more informative metric as it focuses on the minority class's performance.
* ROC AUC: The high ROC AUC scores suggest that the models discriminate well between classes under various threshold settings. RandomForest (BayesSearchCV) model achieves the highest ROC AUC of 0.96.

![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/precison-Recall-Curve.png?raw=true)

*Graph showing model performance across various metrics.*

The potential bias in the dataset necessitates a careful interpretation of the model's performance. The perfection in precision and recall may partly stem from the model's ability to recognise the overwhelming majority class. However, in the real world, the efficacy of a fraud detection system is measured by its ability to correctly identify the minority fraudulent transactions without an excessive number of false positives.

## CONTACT DETAILS

If you're interested in learning more about our project or have suggestions for improvements, feel free to reach out or follow our work on GitHub at [my GitHub Repo Link](https://github.com/jdchen5/imperialMLnAI_CSproject.git). For direct inquiries or collaboration opportunities, reach out at [LinkedIn](https://www.linkedin.com/in/jingchen-ku/).
