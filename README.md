# Credit-Card-Fraud-Detection

# Credit Fraud Detector

**Note:**

 There are still aspects of this kernel that will be subjected to changes. I've noticed a recent increase of interest towards this kernel so I will focus more on the steps I took and why I took them to make it clear why I took those steps.

**Before we Begin:**

If you liked my work, please upvote this kernel since it will keep me motivated to perform more in-depth reserach towards this subject and will look for more efficient ways so that our models are able to detect more accurately both fraud and non-fraud transactions.

## Introduction
In this kernel we will use various predictive models to see how accurate they are in detecting whether a transaction is a normal payment or a fraud. As described in the dataset, the features are scaled and the names of the features are not shown due to privacy reasons. Nevertheless, we can still analyze some important aspects of the dataset. Let's start!

**Our Goals:**
- Understand the little distribution of the "little" data that was provided to us.
- Create a 50/50 sub-dataframe ratio of "Fraud" and "Non-Fraud" transactions. (NearMiss Algorithm)
- Determine the Classifiers we are going to use and decide which one has a higher accuracy.
- Create a Neural Network and compare the accuracy to our best classifier.
- Understand common mistaked made with imbalanced datasets.


### Outline:

**I. Understanding our data**
- a) Gather Sense of our data

**II. Preprocessing**
- a) Scaling and Distributing
- b) Splitting the Data


**III. Random UnderSampling and Oversampling**
- a) Distributing and Correlating
- b) Anomaly Detection
- c) Dimensionality Reduction and Clustering (t-SNE)
- d) Classifiers
- e) A Deeper Look into Logistic Regression
- f) Oversampling with SMOTE


**IV. Testing**
- a) Testing with Logistic Regression
- b) Neural Networks Testing (Undersampling vs Oversampling)

**Correcting Previous Mistakes from Imbalanced Datasets:**

- Never test on the oversampled or undersampled dataset.
- If we want to implement cross validation, remember to oversample or undersample your training data during cross-validation, not before!
- Don't use accuracy score as a metric with imbalanced datasets (will be usually high and misleading), instead use f1-score, precision/recall score or confusion matrix.

**Gather Sense of Our Data:**

The first thing we must do is gather a basic sense of our data. Remember, except for the transaction and amount we dont know what the other columns are (due to privacy reasons). The only thing we know, is that those columns that are unknown have been scaled already.

**Summary:**

- The transaction amount is relatively small. The mean of all the mounts made is approximately USD 88.
- There are no "Null" values, so we don't have to work on ways to replace values.
- Most of the transactions were Non-Fraud (99.83%) of the time, while Fraud transactions occurs (017%) of the time in the dataframe.


**Feature Technicalities:**

- **`PCA Transformation`**: The description of the data says that all the features went through a PCA transformation (Dimensionality Reduction technique) (Except for time and amount).

- **`Scaling:`** Keep in mind that in order to implement a PCA transformation features need to be previously scaled. (In this case, all the V features have been scaled or at least that is what we are assuming the people that develop the dataset did.)
