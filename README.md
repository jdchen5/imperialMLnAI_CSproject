![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/fraudDectionIcon.jpg)

# ONLINE PAYMENT FRAUD DETECTION MODEL


## PROJECT DESCRIPTION

Our model acts as a digital detective, trained to distinguish between regular online payment transactions and potentially fraudulent ones. It scrutinises each transaction's details—such as the money involved, the account's historical balance, and the transaction's origin or destination — to determine its legitimacy. Utilising advanced algorithms, akin to a detective piecing together clues from a crime scene, the model predicts whether a transaction is genuine or if it's an attempt at fraud. This process helps safeguard online financial activities, ensuring users' transactions are secure and trustworthy. By analysing patterns from vast amounts of data, the model learns to identify the subtle signs of fraud that might escape the human eye, making it an essential tool in the fight against digital financial crimes.


## DATA

We used a dataset that contains information on hundreds of thousands of online transactions, including whether they were fraudulent or not. This data includes details like the amount of money involved, the accounts sending and receiving the money, and when the transactions took place. The dataset was generously made available by Kaggle, and you can find it [here](https://www.kaggle.com/datasets/pankajtiwari2003/fraudlent-transaction).


## MODEL 

This model serves as the brain of our digital detective, analysing complex financial data to make smart decisions swiftly. We tested several different "detective strategies" (machine learning models), with the RandomForestClassifier standing out among them. We fine-tuned the model with advanced techniques (GridSearchCV, BayesSearchCV, and RandomizedSearchCV) to ensure its accuracy and resilience in handling complex cases. It's particularly good at maintaining high precision and recall across different situations – that's critical for making the right calls in real-time.


We also take a close look at which bits of information are most helpful (feature importance analysis), and double-check our assumptions (hypothesis testing to validate predictor significance). We even combine different methods (stacked classifiers) for the best possible outcomes. Decision trees offer easy-to-follow reasoning, but Random Forest is our top choice for its adaptability and reliability, ensuring we can trust it to manage financial transactions efficiently.

Each model we tested is good at what it does. However, Random Forest is like assembling a whole team of detectives. This teamwork leads to more accurate and reliable results, making it the ultimate tool in our investigation kit.


## HYPERPARAMETER OPTIMSATION

Hyperparameters are like the settings on a detective's toolkit, adjusting how thorough or quick the investigation is. We utlised various methods such as BaySearchCV and RandomizedSearchCV, which systematically tries out different combinations of settings to find the optimal ones. This ensures our digital detective is not only smart but also efficient, using its resources wisely to catch fraudsters.

RandomForestClassifier (BayesSearchCV): to grow a magical forest where the trees are classifiers that help us decide between different choices
- 'max_depth'= 11: plant our trees with a certain depth (11 layers of branches)
- 'min_samples_leaf' = 1: each leaf has at least one piece of information before making a decision
- 'min_samples_split' =  10: split the branches when we have at least 10 pieces of information
- 'n_estimators' = 143: to grow 143 trees in our forest



## RESULTS

Given the prevalence of class imbalance in fraud detection datasets — where fraudulent transactions are significantly outnumbered by legitimate ones. This disparity often skews performance metrics, hence our focus on more discerning evaluation criteria:

![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/performanceMatrix.jpg?raw=true)


* Accuracy: Although all our models show accuracy over 90%, this figure might not tell the whole story in a dataset where frauds are rare. Such high accuracy could merely echo the prevalent class distribution.
* Precision, Recall, & F1-Score: Perfect scores in these metrics might typically signal top-notch performance. But again, we must be wary; it's possible that the models might just be echoing the majority class—a sign of potential overfitting.
* PR AUC: A standout result is the PR AUC score, which is particularly telling in the context of imbalanced datasets. Our Random Forest model, refined with BayesSearchCV, has achieved an impressive PR AUC, indicating its strength in honing in on the less frequent fraudulent transactions.
* ROC AUC: Similarly, our models fare well with ROC AUC scores, indicating a good distinction between classes across different thresholds. Notably, the Random Forest model tuned with BayesSearchCV reached the highest ROC AUC of 0.96.

![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/precison-Recall-Curve-RandomForestClassifier-withBalancedDS.png?raw=true)

*Graph showing model performance across various metrics.*

When we introduced balance to the dataset, aiming for a fair representation of both classes, our Random Forest model (optimised with BayesSearchCV) demonstrated its reliability. The PR AUC soared to 0.98, underscoring its proficiency in detecting fraud even when fraudulent transactions are less frequent than legitimate ones.

This balanced view of the dataset is crucial. While our models might seem to excel across all fronts, the true test of their value lies in their ability to sniff out fraud accurately—minimising false positives — rather than simply recognising the majority class of legitimate transactions.
## CONTACT DETAILS

If you're interested in learning more about our project or have suggestions for improvements, feel free to reach out or follow our work on GitHub at [my GitHub Repo Link](https://github.com/jdchen5/imperialMLnAI_CSproject.git). For direct inquiries or collaboration opportunities, reach out at [LinkedIn](https://www.linkedin.com/in/jingchen-ku/).
