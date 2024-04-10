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

Our model proved to be quite the sleuth in identifying fraudulent transactions. It could accurately spot a high percentage of frauds, significantly reducing the risk for everyone involved. We learned that even though no model is perfect, with the right data and settings, we can greatly minimize the threat of online payment fraud. Below is an example plot showing our model's accuracy:

<img src="https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/precision-Recall-Curve.png" alt="Performance Graph" width="500"/>

*Graph showing model performance across various metrics.*


## CONTACT DETAILS

If you're interested in learning more about our project or have suggestions for improvements, feel free to reach out or follow our work on GitHub at [my GitHub Repo Link](https://github.com/jdchen5/imperialMLnAI_CSproject.git). For direct inquiries or collaboration opportunities, reach out at [LinkedIn](https://www.linkedin.com/in/jingchen-ku/).
