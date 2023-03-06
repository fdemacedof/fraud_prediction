## Comparing classification algorithms using Kaggel's Fraudulent Transactions dataset 

**Important**: Kaggles dataset can be downloaded in https://www.kaggle.com/datasets/chitwanmanchanda/fraudulent-transactions-data. It is a big dataset and i was thus unable to upload it.

You can check the article I wrote in medium about this analysis here: https://medium.com/@fdemacedof/detecting-fraudulent-transactions-with-classification-algorithms-868934378cfe

### Business Understanding

Fraud is a main concern when dealing with huge amounts of daily transactions; Here i used Kaggel's dataset to evaluate the precision accuracy of logistic regression, CatBoost and XGBoost classification strategies on detecting fraudulent transactions. 

Three questions where addressed: 

#### 1: which classificator performs better? 
#### 2: how precision accuracy and accuracy differ across the results? 
#### 3: what is the false positive/false negative error rates for the best performing classificator?

### Data understanding

Dataset was originaly comprised of 6362620, 10 features and one outcome binary variable (1 means fraud).

#### Prepare data

I have chosen to drop “step” (step of the simulation, the time of each transaction), “nameDest” (name of destination account), “nameOrig” (name of origin account), and “isFlaggedFraud” features. I have also used dummy variables instead of the type of transaction feature. The dataset had no missing data.

![image](https://user-images.githubusercontent.com/8518620/161754364-af5dcc88-c589-47a8-82b1-7c6200513a58.png)

### Modeling

I have conducted 10 kfold rounds for each classification method and recorded it's associated precision accuracy and plain accuracy. Then i used the recorded precision and plain accuracies to compare mean and variance accross the three methods.
After deciding which was the best algorithm, i calculate the false positive and false negative rates for that classifier.##
### Question 1: which classificator performs better?

The recorded precision accuracy values, recorded for each classifier, are shown in the above boxplot: 

![image](https://user-images.githubusercontent.com/8518620/161754567-17c656e5-168d-4162-8ae6-60ffa097f5b4.png)

XGBoost and Catboost performed significantly better than the Logistic regression. XGBoost was the best performing model, but not significantly because reaults overlaps with Catboost's.

### Question 2: how precision accuracy and accuracy differ across the results? 

The following graph shows how biased the common accuracy is when dealing with imbalanced samples: for all methods it yielded almost perfect scores! It clearly contrasts with precision accuracy. 

![image](https://user-images.githubusercontent.com/8518620/161755169-d7e3d96a-57db-4520-a4fa-47a2f3b73f10.png)

### Question 3: what is the false positive/false negative error rates for the best performing classificator?

The XGBoost classifier (chosen as the best for the present problem) showed a close to 0 (0.000025) false positive rate and 0.24 false negative rates.

### Evaluation

Finally, XGBoost was the best performing algorithm when using precision accuracy as metric. 
We found that common accuracy is hugely biased when dealing with imbalanced samples.
False-negative rate of XGBoost was 24%; for real world purpuses, this means that the algorithm would fail to classify potential frauds 24 out of 100 times.
