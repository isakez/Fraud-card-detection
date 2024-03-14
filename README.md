# Fraud-card-detection experiments
In this project we are going to recognize fraudulent credit card transactions so the customers are not charged for items that they did not purchase  

The data can be downloaded from: https://www.kaggle.com/mlg-ulb/creditcardfraud


# Why?

The main goal of this project is to learn how to deal with inbalanced datasets, and how to minimize the total fraudulent cards transactions classified as valid transactions. I choose this topic because one of my long term dreams is to diminish the financial corruption of the world, so this is a first little step.

# Quick start

Basically anyone can run the **Fraudcards notebook** cell by cell, along the notebook I explain what I do.
In this Readme I'm going to discuss some experiments and takeaways from the project.

### First insights of the data

As we can see our fraud data is stongly less than the Not fraud

´´´
Not fraud    284315
Fraud           492
Name: Class, dtype: int64
´´´

In this histograms we can see how the features are like long-tail distributions with a high frequency around 0 value and few elements of large values.

![histograms](https://github.com/isakez/Fraud-card-detection/assets/42270381/7888ae11-9d57-4969-913f-5db74f89ed0d)

These charasteristics of the data suggest me that a normalization and techniques of under or over-sample will be interesting to apply.

### First result 

Un model very consistent with his results along all the process was the *DecisionTreeClassifier*. As we can see the first results are pretty good
´´´
                precision    recall  f1-score   support

           0       1.00      1.00      1.00     56870
           1       0.82      0.79      0.81        92

´´´

![first_decision_tree_classifier](https://github.com/isakez/Fraud-card-detection/assets/42270381/7d503a4b-84c3-4f99-96b1-3706841cf0e0)

Now our objective is to improve the recall and minimize this 19 false positives

### Undersample
