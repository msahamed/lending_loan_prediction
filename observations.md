## Lending Club Loan Analysis and Prediction

### Feature engineering:
<li> Removing application type improves the score a little bit

### Model improvement observations
One hotcoding (95 features):
                A) Logistic regression: 69.99
                B) Random forest: 71.34 (roc-auc: 79%)
                
Without one hot coding (35 features):
                A) Logistic regression: 66.4
                B) Random forest: 73.57 (roc-auc: 81.0%)
                
Without application_type feature:
                A) Logistic regression: 66.38
                B) Random forest: 73.66 (roc-auc: 81.17%)

Without issue_year feature:
                A) Logistic regression: 66.38
                B) Random forest: 73.18 (roc-auc: 80.82%)

Without fico_range_low feature:
                A) Logistic regression: 66.40
                B) Random forest: 73.05 (roc-auc: 80.68%)
                
Without ['funded_amnt','funded_amnt_inv', 'loan_diff'] feature:
                A) Logistic regression: 66.40
                B) Random forest: 73.13 (roc-auc: 80.74%)

Without earliest_cr_year feature:
                A) Logistic regression: 66.35
                B) Random forest: 73.20 (roc-auc: 80.77%)


<li> Raw data without up/downsampling model accuracies is pretty high almost 90 percent. However model underperforms on minority class (charged off).
    
<li> I then undersampled the majority class (fully paid off). The overall scores are a bit low (66.43% in linear logistic regression and 66.63% on random forest model) but perform well on minority class (Recall for both minority, and majority call are more than 66 %).
    
<li> I then tuned random forest hyperparameters (n_estimators, max_depth). Tuning these parameters improves the RF score little bit which is not significant.
    
<li> I oversampled the minority class, which improves the overall accuracies to from 67% to 73%.

<li> I tried with and without hot-codded features. Tree-based RF does not perform very well with hot codded features. Maybe neural network can perform well with hot encoded features.