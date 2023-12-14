# FraudClassification

```
Abstract:

This report presents a comprehensive analysis of a dataset of 17,058 financial transactions, incorporating factors such as transaction amount, FICO score, account balance, income, and fraud status. Utilizing advanced statistical and machine learning techniques, we delved into the data to uncover significant patterns and insights, particularly in relation to fraudulent activities. The project’s main focus was to leverage these insights to enhance the effectiveness of machine learning models in detecting and preventing fraud within financial transactions. Key findings reveal critical predictors of fraud and nuances in financial behaviors, offering valuable implications for enhancing transaction security. This analysis not only deepens our understanding of the data’s intrinsic characteristics but also serves as a critical resource for stakeholders aiming to mitigate fraudulent activities in financial systems. Our study highlights the necessity of balancing accuracy and interpretability in predictive models, underscoring the significant role of data analytics in shaping future fraud prevention strategies.

Analysis of Data:

Transaction Amount: The analysis of transaction amounts shows an average of $228.10, but with a significantly high standard deviation of $857.30. This discrepancy suggests a diverse range of transaction values, from relatively small purchases to substantially larger ones. The maximum transaction recorded is $25,949.65, while the minimum is a modest $16.75. Notably, the median value of $131.77 is considerably lower than the average, indicating a skewness in the data towards lower transaction amounts. This skewness could be indicative of a larger volume of small to medium-sized transactions in the dataset.

FICO Score: The FICO scores in the dataset have a mean value of 637.39, reflecting a moderate credit standing among the individuals. The scores range widely from 276 to 850, encompassing the entire spectrum of creditworthiness. A standard deviation of 96.64 points to a varied credit profile of the dataset's population. The median FICO score is 640, closely aligning with the mean, suggesting a relatively balanced distribution of credit scores.

Account Balance: The account balance aspect of the dataset presents an interesting picture with an average balance of $3,697.43. However, the high standard deviation of $3,983.91 indicates significant variation in account balances among individuals. The range of balances extends from negative values (-$2,545.88) to $34,049.94, highlighting the presence of both overdrawn and substantially positive account balances. The median account balance is $2,121.45, suggesting that a significant portion of the dataset comprises accounts with modest balances.

Income: Income levels exhibit a broad range from $2,000 to $779,000, with an average income of $88,371.85. The considerable standard deviation of $81,556.96 underscores the wide disparity in income levels among the individuals in the dataset. The median income of $78,000 is lower than the average, indicating a skew towards lower income brackets. This disparity in income levels could be a critical factor in understanding spending patterns and financial behavior.

Fraud Analysis: The dataset indicates that approximately 8.2% of the transactions are fraudulent. This relatively small but significant proportion of fraudulent transactions necessitates a closer examination to discern any underlying patterns or correlations. Analyzing the relationship of fraudulent activities with variables such as transaction amounts, FICO scores, account balances, and income levels could yield crucial insights for fraud detection and prevention.

The dataset presents a comprehensive view of financial transactions, encompassing a wide range of economic behaviors. The diversity in transaction amounts, coupled with the varied credit and income profiles, paints a detailed picture of the financial landscape. The presence of fraudulent transactions, though a small fraction, adds a critical dimension to the analysis, inviting further investigation into the predictors and characteristics of such activities.

Modeling 1: Logistic Specify an Interpretable Model and Interpret:

For an effective predictive model in binary classification scenarios, Logistic Regression is a solid and reliable choice. This model is particularly known for its simplicity and interpretability, often serving as a baseline in binary classification tasks. In our case, our Logistic Regression model stands out with a high ROC AUC score of 0.83, demonstrating its strong predictive capabilities.

Logistic Regression is efficient in estimating the probabilities of a binary outcome, making it highly suitable for cases where understanding the likelihood of an event is crucial. This model excels in balancing false positives and false negatives, which is essential in many practical applications. Its linear approach to decision-making, while less complex than ensemble methods, provides a clear and understandable model structure.
The analysis of feature importance is straightforward in Logistic Regression, as the model coefficients directly relate to the influence of each predictor on the outcome. This transparency is invaluable for understanding what drives the predictions and for communicating the model's decision-making process to stakeholders who might not be well-versed in machine learning.

Despite its simplicity, Logistic Regression can be quite powerful, especially when the relationship between the independent variables and the dependent binary variable is approximately linear. Its ability to provide probabilities for the outcomes makes it a versatile tool for various binary classification problems. However, it's important to note that Logistic Regression may not perform as well as more complex models like Random Forests when dealing with highly nonlinear data or interactions between features.

Modeling 2 – Specify a Model That Predicts Well and Discuss

The RandomForest model seems to be the best performer with a ROC AUC score of 0.9678. RandomForest, an ensemble of Decision Trees, usually outperforms a single Decision Tree because it reduces overfitting by averaging multiple trees. This explains its superior performance to the DecisionTree in classifying the test data. Considering that the is relatively large, relatively high in dimensionality, and contains a decent mix of both numerical and categorical (dummy) data, the model is theoretically an ideal choice.

In practice too, the model performs exceptionally well. If classification success is the only metric given importance or the metric given the most importance, The RandomForest seems an ideal choice, its only drawback being that  it's less interpretable than a single Decision Tree due to its complex ensemble structure.

Concerning Interpretation of our High Interpretability and High Performance Model:

A noteworthy aspect to consider is the variable importance plots derived from both the Decision Tree and RandomForest models. It is intriguing to note that while these plots are largely similar between the two models, there are differences that merit attention. We’ve considered both models as capable of providing us information about the importance of certain variables in classification.

In the case of the Decision Tree model, the variable importance plot is directly linked to the structure of the tree. Each node in the tree represents a decision based on a specific variable, and the depth at which a variable is used in the tree can be indicative of its importance. This approach offers a clear and straightforward understanding of which variables are most influential in the model's decision-making process. However, this simplicity can also be a limitation, as it might not capture the full complexity of interactions between variables.

On the other hand, the RandomForest model, being an ensemble of numerous decision trees, offers a more nuanced view of variable importance. In RandomForest, each tree in the ensemble may use a different subset of variables for decision-making, leading to a more distributed and diversified understanding of variable importance. This can result in slight variations in the importance rankings of variables compared to a single Decision Tree.

These variations are important to consider because they can highlight the robustness of certain variables across different models and also point out where models might disagree on the importance of certain features. For instance, a variable that ranks highly in both models can be considered a consistently strong predictor across different modeling approaches. Conversely, a variable that is important in the Decision Tree but less so in the RandomForest might be an indicator of model-specific biases or overfitting.

In practical terms, understanding these differences in variable importance plots can guide us in refining our models and in making more informed decisions about feature selection and engineering. It's crucial to strike a balance between the interpretability offered by the Decision Tree and the robustness and generalization capabilities of the RandomForest.

Model Comparison:

Decision Tree: We have considered how the high ROC AUC (0.9594), accuracy (0.9496), and interpretability of this specific model make it a strong choice for general use, it's crucial to note that Decision Trees can sometimes suffer from a lack of robustness to small variations in the data. This means that slight changes in the training data can lead to significantly different tree structures. This lack of stability might be a concern in dynamic environments where data is continually updated. However, in more static datasets, this may not be a significant issue.

RandomForest: Its ROC AUC score of 0.9625 demonstrates that this model is both very accurate and robust. It's worth noting that RandomForest models have the ability to handle large data sets and maintain accuracy even when a significant proportion of the data is missing. This makes RandomForest particularly useful in real-world scenarios where incomplete data is a common challenge. However, the complexity and computational demands of RandomForest models, as well as their lower interpretability, remain significant considerations.The fact that our data is Bank data and is therefore lacks the incomplete rows of data that other forms of data are prey to make the robustness and benefits offered by the random forest model not significantly better than a simple decision tree.

Ridge Regression: Although it has a decent ROC AUC of 0.8267, one must consider that Ridge Regression is particularly effective when dealing with data that has numerous features, as it applies shrinkage, which helps to reduce model complexity and prevent overfitting. However, since overfitting and multicollinearity were not major concerns in our dataset, the benefits of Ridge Regression are not fully capitalized on in this scenario.

Lasso Regression: With a lower ROC AUC of 0.8302, Lasso Regression's main advantage lies in its feature selection capability, which simplifies models by eliminating some variables entirely. This can be particularly advantageous in scenarios where model simplicity and interpretability are paramount, and where data features are numerous and potentially redundant. However, given that our dataset did not exhibit significant multicollinearity and the higher performance models were already quite interpretable, Lasso's trade-off for performance doesn't seem justifiable.

ElasticNet: Having a ROC AUC similar to Ridge Regression (0.8260), ElasticNet provides a balance between Lasso and Ridge. ElasticNet is particularly beneficial in situations where there are correlations between multiple features, since it blends feature elimination from Lasso and feature shrinkage from Ridge. However, in our case, since the advantages of both Lasso and Ridge are not particularly relevant to our dataset's characteristics, ElasticNet's utility is similarly limited.

KNN (K-Nearest Neighbors): Lowest ROC AUC (0.5666). K-Nearest Neighbors would not be our first choice due to the relatively high dimensionality of the data. The simplicity of the model makes it very prey to a high bias considering the data. Statistically, the classification success is very much better than random guessing. The cumulative probability of getting at least 9632 successes using the python prompt 1 - binom.cdf(9631, 17058, 0.5) returns 0.0, indicating that the probability of such a high classification rate by random chance is effectively zero.

However, in practical terms, a .5666 classification success rate does not create a significant increase in our ability to confidently classify fraud, as it is practically only a 6.66% increase in success from random guessing. We can conclude that the model is significantly biased, as to be expected from relatively high dimensional data in a KNN Model.

This is an example where statistical significance does not imply practical significance or value; the low statistical probability is almost completely a result of a very high sample size, a 1000+ deviation from which is very unlikely.


Feature Importance:

Analyzing the variable importance plots from both the RandomForest and Decision Tree models gives us insights into the features that are most influential in predicting the target variable in our dataset.

In the RandomForest model, we observe that 'fico' scores are given the highest importance, followed by 'income' and 'month.' These features are likely good predictors of the outcome variable due to their high variance and potential correlations with the target. It's interesting to note that the 'fico' score, which is often a measure of creditworthiness, ranks as the most significant predictor, suggesting that creditworthiness is highly indicative of the outcome.

The Decision Tree model prioritizes 'amount' as the most important feature, followed by 'income' and 'products_Shopping.' The disparity between 'amount' in the Decision Tree and the RandomForest could suggest that while 'amount' is a critical decision node in a single tree, its influence may be averaged out across the multiple trees in the RandomForest, highlighting different aspects of the data.

These differences in feature importance between the models can be attributed to their respective mechanisms for assessing importance. RandomForest considers the average decrease in impurity from each feature across all trees, while the Decision Tree considers the total decrease in node impurity (like Gini impurity or entropy) from splits on each feature.

Regarding the dummy variables created from 'products,' 'US,' 'card,' and 'state,' we can see their varied levels of influence on the models. For instance, 'products_Travel' and 'card_Discover' are considered more important in the RandomForest model, while 'products_Shopping' stands out in the Decision Tree model. This variation indicates that different models may leverage different aspects of the categorical data when making predictions.

The eigenvalues and correlation matrix provided are indicative of the multicollinearity within our dataset. The eigenvalues, all being significantly greater than zero, suggest that there is no multicollinearity. This is supported by the correlation matrix, which shows relatively low correlation coefficients between the variables, indicating that multicollinearity is not a significant issue in our dataset. This means that the importance given to variables in the models is less likely to be inflated due to multicollinearity, lending credibility to the interpretations of the variable importance plots.

The variable importance plots reveal that different models may prioritize different features based on their unique methodologies and the data's structure. These insights are valuable for understanding the underlying patterns in the data and for making informed decisions about feature engineering and selection in future model iterations.

Conclusion:

In summary, the analysis of this dataset, encompassing over 17,000 transactions with variables such as transaction amounts, FICO scores, account balances, income, and fraud status, has yielded significant insights into financial behaviors and the prevalence of fraud. The study leveraged diverse machine learning models, including Random Forest, Decision Tree, Ridge Regression, Lasso Regression, ElasticNet, and K-Nearest Neighbors, each contributing unique perspectives to the understanding of the data. Notably, the Random Forest model demonstrated superior performance with a high ROC AUC score, highlighting its robustness and accuracy in managing the complexity of the dataset. The examination of feature importance across models revealed key variables like FICO scores, income, and transaction amounts as crucial predictors. These insights are pivotal for enhancing predictive models and understanding financial behaviors, particularly in fraud detection and prevention, emphasizing the necessity of a balance between model accuracy and interpretability in the field of predictive analytics.
```
