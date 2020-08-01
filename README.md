# Credit-Fraud-Dealing-with-imbalanced-dataset
Kaggle project

Tips and tricks to avoid overfitting during undersampling/oversampling with imbalanced datasets.

In this notebook, I explain a very interesting point that I discover recently :

Cross Validation Overfitting Mistake

If you want to undersample or oversample your data you should not do it before cross validating. Why because you will be directly influencing the validation set before implementing cross-validation causing a "data leakage" problem.

If we get the minority class ("Fraud) in our case, and create the synthetic points before cross validating we have a certain influence on the "validation set" of the cross validation process. Remember how cross validation works, let's assume we are splitting the data into 5 batches, 4/5 of the dataset will be the training set while 1/5 will be the validation set. The test set should not be touched! For that reason, we have to do the creation of synthetic datapoints "during" cross-validation and not before

For good measure I will show, in this notebook, the undersampling before cross-validation and the undersampling during cross validation

## Table of Contents
<details open>
<summary>Show/Hide</summary>
<br>

1. [ File Descriptions ](#File_Description)
2. [ Technologies Used ](#Technologies_Used)    
3. [ Structure ](#Structure)
4. [ Future Development ](#Executive_Summary)
</details>

## File Descriptions
<details>
<a name="File_Description"></a>
<summary>Show/Hide</summary>
<br>
  
The datasets contains transactions made by credit cards in September 2013 by european cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.
</details>

## Technologies Used:
<details>
<a name="Technologies_Used"></a>
<summary>Show/Hide</summary>
<br>
    
* <strong>Python</strong>
* <strong>Pandas</strong>
* <strong>Numpy</strong>
* <strong>Matplotlib</strong>
* <strong>Seaborn</strong>
* <strong>XGBoost</strong>
* <strong>LightGBM</strong>
* <strong>Scikit-Learn</strong>
* <strong>Keras</strong>
* <strong>Tensorflow</strong>
* <strong>LIME</strong>
</details>

## Structure of Notebooks:
<details>
<a name="Structure"></a>
<summary>Show/Hide</summary>
<br>
  




    
1. Introduction

2. Gather Sense of Our Data

3. Scaling and Distributing

4. Random Under-Sampling

5. Correlations and outliers

6. Dimensionality Reduction and Clustering

7. Modeling with Undersampling

   * 7.1 /!\ IMPORTANT NOTE /!\
   * 7.2 Undersampling before cross validation (prone to overfit)
   * 7.3 Undersampling during cross validation
   * 7.4 Second Submission to Kaggle


8. Oversampling with SMOTE techniques
    * 8.1 SMOTE before cross-validation
    * 8.2 SMOTE during cross-validation

9. Neural Networks Testing Random UnderSampling Data vs OverSampling (SMOTE)
10. Conclusion


</details>  


<a name="Executive_Summary"></a>
## Future Development
    
* I would like to deploying the model for actionnable use like I did for other project like "What's Cooking".


