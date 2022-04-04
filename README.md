## Comparing classification algorithms using Kaggel's Fraudulent Transactions dataset 

**Important**: Kaggles dataset can be downloaded in https://www.kaggle.com/datasets/chitwanmanchanda/fraudulent-transactions-data.

Here i used Kaggel's dataset to evaluate the precision accuracy of logistic regression, CatBoost and XGBoost classification strategies on detecting fraudulent transactions.

I have conducted 10 kfold rounds for each classification method and recorded it's associated precision accuracy. Then i used the recorded precision accuracies to compare mean and variance accross the three methods. We can vizualize the results in the following boxplot:

![boxplot](https://user-images.githubusercontent.com/8518620/161558749-7ab1b9af-ee7f-4c56-a1b1-5822c120d30c.png)
