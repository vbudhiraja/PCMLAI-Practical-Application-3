# PCMLAI-Practical-Application-3

The dataset collected is related to 17 campaigns that occurred between May 2008 and November 2010, corresponding to a total of 79354 contacts. During these phone campaigns, an attractive long-term deposit application, with good interest rates, was offered. For each contact, a large number of attributes was stored and if there was a success (the target variable). For the whole database considered, there were 6499 successes (8% success rate).

 # Analysis based on the specified rubric

## Data cleaning steps included

### The data is related to the campaign regarding the long-term deposit application. The business objective of the task is to determine whether a bank client will subscribe to a long term deposit.

##  What is the baseline performance that our classifier should aim to beat?
#### The answer can discovered by simply taling the mean. No - 0 =   0.887346, Yes - 1 =   0.112654

## What is the accuracy of your simple Logistic Regression model?
#### 0.9104960750991341

## The next task is to compare the models.
#### To compare the models a list of models is setup and loop through using the default parameters. Logistic Regression model gave under fit warning. I increased the iterations to 7500 to address the warning.

### Results

#### Model Comparison for various models:
| Model                | Train Time | Train Accuracy | Test Accuracy | Precision | F1 Score | Recall   |
|----------------------|------------|----------------|---------------|-----------|----------|----------|
| Logistic Regression  | 7.996251   | 0.910201       | 0.910496      | 0.674390  | 0.500000 | 0.397270 |
| Decision Tree        | 0.109368   | 1.000000       | 0.889132      | 0.507703  | 0.514184 | 0.520833 |
| KNN                  | 0.000000   | 0.931046       | 0.905721      | 0.602529  | 0.533814 | 0.479167 |
| SVM                  | 4.223314   | 0.897471       | 0.898438      | 0.658933  | 0.311574 | 0.204023 |


Logistic Regression: Overall the model shows high accuracy of 91% and longest train time.
Decision Tree: Overfitting the training data because accuracy is 100%, Test accuracy is only 88%.. It also has lower precision and F1 score.                       
KNN: Has good accuracy of 90%.               
SVM: Has accuracy of 89%.

## Improving the Model
### To fine tune the hyper parameter parameters a list of various parameters was created and loop through and GridSearchCV was performed to find the best parameters.

### Training Results with Hyperparameter Tuning

#### Logistic Regression:
- **Hyperparameters:** `{'C': 1, 'penalty': 'l2', 'solver': 'liblinear'}`
- **Test Accuracy:** 0.9106579266812334
- **Training time for the best model:** 0.4003 seconds
- **Cross-validation details:** Fitting 4 folds for each of 4 candidates, totaling 16 fits
<h4 style="color: blue;">Accuracy stays almost same, training time is reduced.</h4>
<div style="border-top: 2px solid blue; margin-top: 20px;"></div>

### Test Summary:
#### Decision Tree:
- **Hyperparameters:** `{'max_depth': 10, 'min_samples_leaf': 4, 'min_samples_split': 10}`
- **Test Accuracy:** 0.9114671845917294
- **Training time for the best model:** 0.1538 seconds
- **Cross-validation details:** Fitting 4 folds for each of 36 candidates, totaling 144 fits
- <h4 style="color: blue;">Test accuracy increased.</h4>
<div style="border-top: 2px solid blue; margin-top: 20px;"></div>

#### KNN:
- **Hyperparameters:** `{'algorithm': 'auto', 'n_neighbors': 9, 'weights': 'uniform'}`
- **Test Accuracy:** 0.9079873755765963
- **Training time for the best model:** 0.0123 seconds
- **Cross-validation details:** Fitting 4 folds for each of 24 candidates, totaling 96 fits
- <h4 style="color: blue;">Accuracy stays almost same, training time is increased.</h4>
<div style="border-top: 2px solid blue; margin-top: 20px;"></div>

#### SVM:
- **Hyperparameters:** `{'C': 0.01, 'gamma': 'auto', 'kernel': 'linear'}`
- **Test Accuracy:** 0.9050740470988103
- **Training time for the best model:** 28.1303 seconds
- **Cross-validation details:** Fitting 4 folds for each of 2 candidates, totaling 8 fits
- <h4 style="color: blue;">Accuracy is better, training time is increased alot.</h4>
- <div style="border-top: 2px solid blue; margin-top: 20px;"></div>