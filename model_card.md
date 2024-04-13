# <span style="color:#4285F4;">Online Payment Fraud Detection Model Card</span>

Our model is designed to analyse online payment transactions to detect potential fraud. By examining features like transaction amounts, account balances before and after transactions, and the timing of these activities, it applies a combination of machine learning techniques to predict fraudulent behavior. This model utilises statistical analysis and classification algorithms, including RandomForest and DecisionTree classifiers, optimised through methods like GridSearchCV, BayesSearchCV and RandomizedSearchCV, to identify patterns indicative of fraud. Its performance is evaluated based on accuracy, precision, recall, and the area under the precision-recall curve, providing a comprehensive understanding of its effectiveness in distinguishing between legitimate and fraudulent transactions. This analytical approach allows for enhanced security in online financial activities by identifying and flagging suspicious transactions.
<br/><br/>
## <span style="color:#4285F4;">MODEL DESCRIPTION</span>
![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/fraudDectionIcon.jpg)


**Input:** 
The model inputs include various features from a financial dataset, specifically focusing on online payment transactions. These features include,
- step: maps 1 hour of time
- type of transaction
- transaction amount
- customer who started the transaction
- account balances before and after the transactions
- customer who is the recipient of the transaction
- recipient balances before and after the transactions

**Output:**
- Binary classification: `0` for legitimate, `1` for fraudulent

**Model Architecture:**

[RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html) fromScikit-learn(Python).

<br/><br/>
## <span style="color:#4285F4;">PERFORMANCE</span>

The model's performance is evaluated using accuracy, precision, recall, and the area under the precision-recall curve (PR AUC). Performance metrics are provided for multiple models, with additional insights from confusion matrices and precision-recall curves. From the table below, the recommended model demonstrated high accuracy in fraud detection, with further details on performance metrics such as the model accuracy score, which reflects the model's effectiveness in classifying fraudulent transactions.

* **Accuracy**: Although all our models show accuracy over 90%, this figure might not tell the whole story in a dataset where frauds are rare. Such high accuracy could merely echo the prevalent class distribution.
* **Precision, Recall, & F1-Score**: Perfect scores in these metrics might typically signal top-notch performance. But again, we must be wary; it's possible that the models might just be echoing the majority class—a sign of potential overfitting.
* **PR AUC**: A standout result is the PR AUC score, which is particularly telling in the context of imbalanced datasets. Our Random Forest model, refined with BayesSearchCV, has achieved an impressive PR AUC, indicating its strength in honing in on the less frequent fraudulent transactions.
* **ROC AUC**: Similarly, our models fare well with ROC AUC scores, indicating a good distinction between classes across different thresholds. Notably, the Random Forest model tuned with BayesSearchCV reached the highest ROC AUC of 0.96.
<br/><br/>  

![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/performanceMatrix.jpg?raw=true)
<br/><br/>

![alt text](https://github.com/jdchen5/imperialMLnAI_CSproject/blob/main/images/precison-Recall-Curve-RandomForestClassifier-withBalancedDS.png?raw=true)

<br/><br/>
When we introduced balance to the dataset, aiming for a fair representation of both classes, our Random Forest model (optimised with BayesSearchCV) demonstrated its reliability. The PR AUC soared to 0.98, underscoring its proficiency in detecting fraud even when fraudulent transactions are less frequent than legitimate ones.

This balanced view of the dataset is crucial. While our models might seem to excel across all fronts, the true test of their value lies in their ability to sniff out fraud accurately—minimising false positives — rather than simply recognising the majority class of legitimate transactions.
<br/><br/>

## <span style="color:#4285F4;">LIMITATIONS</span>
- **Data Imbalance**: The dataset contains a much higher proportion of non-fraudulent transactions compared to fraudulent ones, potentially biasing the model.
- **Feature Selection**: The removal of certain features based on hypothesis testing could overlook complex interactions between variables that might be predictive of fraud.
- **Generalisation**: The model's performance on data outside the provided dataset is uncertain, especially concerning different types of online payment fraud.
<br/><br/>

## <span style="color:#4285F4;">TRADE-OFFS</span>
- **Complexity vs. Interpretability**: Advanced models like Random Forest classifiers offer improved accuracy but at the cost of interpretability, making it harder to understand the model's decision-making process.
- **Sampling Strategy**: Addressing the data imbalance through under-sampling or over-sampling techniques can improve model sensitivity to fraud cases but may also increase the false positive rate.
- **Feature Engineering**: The choice to simplify the model by removing features or combining categories within features can improve model manageability but may reduce the overall predictive power.

