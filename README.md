## Comparing classification algorithms using Kaggel's Fraudulent Transactions dataset 

**Important**: Kaggles dataset can be downloaded in https://www.kaggle.com/datasets/chitwanmanchanda/fraudulent-transactions-data.

Here i used Kaggel's dataset to evaluate the precision accuracy of logistic regression, CatBoost and XGBoost classification strategies on detecting fraudulent transactions.

Three questions where addressed: which classificator performs better? how precision accuracy and accuracy differ across the results? which features best predict frauds using the best-performing classficator as model?

I have conducted 10 kfold rounds for each classification method and recorded it's associated precision accuracy and plain accuracy. Then i used the recorded precision and plain accuracies to compare mean and variance accross the three methods. Also, coeficients for the best performing model was calculated in order to discover which feature predicts frauds best.

