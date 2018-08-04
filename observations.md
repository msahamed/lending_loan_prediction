## Lending Club Loan Analysis and Prediction

### Feature engineering:


### Model improvement observations
One hotcoding (95 features):
                A) Logistic regression: 69.99
                B) Random forest: 71.34 (roc-auc: 79%)
                
Without one hot coding (35 features):
                A) Logistic regression: 66.4
                B) Random forest: 73.57 (roc-auc: 81.0%)


<li> Raw data without up/downsampling model accuracies is pretty high almost 90 percent. However model underperforms on minority class (charged off).
    
<li> I then undersampled the majority class (fully paid off). The overall scores are a bit low (66.43% in linear logistic regression and 66.63% on random forest model) but perform well on minority class (Recall for both minority, and majority call are more than 66 %).
    
<li> I then tuned random forest hyperparameters (n_estimators, max_depth). Tuning these parameters improves the RF score little bit which is not significant.
    
<li> I oversampled the minority class, which improves the overall accuracies to from 67% to 73%.

<li> I tried with and without hot-codded features. Tree-based RF does not perform very well with hot codded features. Maybe neural network can perform well with hot encoded features.