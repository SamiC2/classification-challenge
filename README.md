# classification-challenge
## By Sami Chowdhury

# Table of Contents

- [Summary](#summary)
- [Analysis](#analysis)
    - [Splitting and Scaling the Data](#splitting-and-scaling-the-data)
    - [Creating the Logistic Regression Model](#creating-the-logistic-regression-model)
    - [Creating the Random Forest Classifier Model](#creating-the-random-forest-classifier-model)
    - [Comparing the Two Models](#comparing-the-two-models)
- [Conclusion](#conclusion)
- [Further Work](#further-work)
- [Thoughts on the Assignment](#thoughts-on-the-assignment)
- [HOWTO RUN](#howto-run)
- [Repository Structure](#repository-structure)

## Summary

This assignment focused on utilizing two different machine learning models to figure out which one had the better accuracy score at making predictions for the data. In particular, were focused on predicting whether an email was spam or not (0 meaning it was legitimate, 1 meaning it was spam) based on data about the email provided. 

The two models used for comparison were Logistic Regression and Random Forest Classifier. In my experience, Random Forest Classifier models are usually more accurate models because they are ensemble learning models, made up of small Decision Tree models to create one large model. As such I predicted that the Random Forest Classifier Model would have the better accuracy score of the two.

## Analysis

### Splitting and Scaling the Data

From the data provided, I created a train-test split on the data from SKLearn. Since the data was not scaled, I also created a Standard Scaler to scale the training dataframes. I made sure that I fit the scaler to the training data so that the testing data did not influence the training data at all. Otherwise, this could result in a model that was skewed to overfitting. I then scaled the data using the **transform()** function of the Scaler class. 

### Creating the Logistic Regression Model

Afterwards, I created the Logistic Regression Model using a Random State of 1 to make future runs of the notebook more consistent. Below is a table of the Training and Testing Data accuracies of the model using **accuracy_score()** from SKLearn:

> TABLE 1: Accuracy Scores of Logistic Regression Model

| Data Type | Model Accuracy | Model Accuracy (%) |
| --------- | -------------- | ------------------ |
| Training Data | 0.937101 | 93.7101 % |
| Testing Data | 0.911381 | 91.1381 % |

From the above, we can see that the Logistic Regression Model was accurate about 91 % of the time in predicting emails as spam or legitimate based on the data provided. Overall this is a decent score

### Creating the Random Forest Classifier Model

Next, I created the Random Forest Classifier Model to fit the same data. Initially I had decided to use the *n_estimators* parameter of the model to try and see if having cutoffs for the roots would prevent overfitting and accuracy. When looking at the shape of the training data, I tried to make sure that my number of estimators was less than 10% of the data, and after seeing 3450 rows, I decided to use 300 estimators. I also created a Random Forest Classifier model without any estimators. Both were made with a random state of 1 to ensure reproducibility. After running the model accuracy scores on both versions, I found that since the training accuracy was the same, I decided to proceed forward with the random forest classifier model that did not specify estimators. As a result, the table below shows the accuracy scores for random forest classifiers model based on the training and testing data, using **accuracy_score()** from SKLearn:

> TABLE 2: Accuracy Scores of Random Forest Classifier Model

| Data Type | Model Accuracy | Model Accuracy (%) |
| --------- | -------------- | ------------------ |
| Training Data | 0.999710 | 99.9710 % |
| Testing Data | 0.943527 | 94.3527 % |

### Comparing the Two Models

> TABLE 3: Accuracy Scores of Both Machine Learning Models


| Model | Model Accuracy | Model Accuracy (%) |
| --------- | -------------- | ------------------ |
| Logistic Regression | 0.911381 | 91.1381 % |
| Random Forest Classifier | 0.943527 | 94.3527 % |

## Conclusion

Based on the accuracy scores calculated for both models, I found that the Random Forest Classifier Model was ~3% more accurate in predicting whether emails were spam or legitimate for this dataset. This matched my prediction and my experience, and supported my explanation as to why as well. 

## Further Work

In the future, I would have liked to figure out what were the other metrics for these models on the dataset. I would want to ensure that there was no overfitting, and that its precision and recall were high as well. 

## Thoughts on the Assignment

Overall I thought the assignment was very simple, almost too simple. I wish there was more that could be done, or that we focused on building a pipeline properly and tested it across multiple datasets for a specific theme. But in the end, I now know how to create machine learning models, how to scale data, how to create a train test split for machine learning models, and how to calculate the accuracy scores for machine learning models. 

## HOWTO RUN

To run the notebook, simply clone the repository and then run the **spam_detector.ipynb** file to calculate all the required analysis. Comments and notes have been made inside the notebook for clarity. 

# Repository Structure

```
├── spam_detector.ipynb
├── README.md
```