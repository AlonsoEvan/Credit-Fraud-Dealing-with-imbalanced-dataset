# Credit-Fraud-Dealing-with-imbalanced-dataset
Kaggle project

Tips and tricks to avoid overfitting during undersampling/oversampling with imbalanced datasets.

In this notebook, I explain a very interesting point that I discover recently :

Cross Validation Overfitting Mistake

If you want to undersample or oversample your data you should not do it before cross validating. Why because you will be directly influencing the validation set before implementing cross-validation causing a "data leakage" problem.

If we get the minority class ("Fraud) in our case, and create the synthetic points before cross validating we have a certain influence on the "validation set" of the cross validation process. Remember how cross validation works, let's assume we are splitting the data into 5 batches, 4/5 of the dataset will be the training set while 1/5 will be the validation set. The test set should not be touched! For that reason, we have to do the creation of synthetic datapoints "during" cross-validation and not before

For good measure I will show, in this notebook, the undersampling before cross-validation and the undersampling during cross validation

