# Fintech_Module_14_Challenge

## Original Model Performance
4 day Short SMA 100 day Long SMA, trainiing window = 3 months

              precision    recall  f1-score   support

        -1.0       0.43      0.04      0.07      1804
         1.0       0.56      0.96      0.71      2288

    accuracy                           0.55      4092
   macro avg       0.49      0.50      0.39      4092
weighted avg       0.50      0.55      0.43      4092


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/Mod_14_Original_Mod_Perform.png)



### Conclusions of Original Model Performance (Question 1):

A few things become clear from looking at the classification report of the original model, as well as the visual comparison of strategy returns vs actual returns. First of all, the recall value for our sell-side indicators are quite low. This lacking recall should not be an issue as long our strategy returns perform well, but they do not in this instance, In fact, strategy returns woefully underperform our benchmarck actual returns. 



## Tuning Process

### Increasing Training Window Size 

#### Model with 24 month training window (alternative 1 ... roughly 40% of dataset used for training)


              precision    recall  f1-score   support

        -1.0       0.80      0.00      0.01      1229
         1.0       0.56      1.00      0.72      1565

    accuracy                           0.56      2794


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/Mod_14_A1_perform.png)


#### Model with 30 month training window (alternative 2 ... roughly 50% of dataset used for training)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1029
         1.0       0.55      1.00      0.71      1280

    accuracy                           0.55      2309


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/Mod_14_A2_perform.png)


#### Model with 45 month training window (Alternative 3 ... roughly 75% of dataset used for training)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00       476
         1.0       0.56      1.00      0.72       614

    accuracy                           0.56      1090


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/Mod_14_A3_perform.png)


### Tuning SMA Windows 

#### Model with 4 day SMA and 30 day SMA, 3 month training offset  (A4)

              precision    recall  f1-score   support

        -1.0       0.40      0.09      0.15      1826
         1.0       0.56      0.89      0.68      2321

    accuracy                           0.54      4147


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A4.png)



#### Model With 20 day SMA and 50 day SMA, 3 month (A5)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1826
         1.0       0.56      1.00      0.72      2321

    accuracy                           0.56      4147


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A5_final.png)


### Tuning SMA Windows in Conjunction with Training Window Variation



#### Long SMA Window = 30, Short SMA Window = 4, training duration = 45 months (A6)

             precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00       555
         1.0       0.55      1.00      0.71       682

    accuracy                           0.55      1237


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A6.png)


#### Long SMA Window = 10, Short SMA Window = 4, training duration = 45 months (A7)

           precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00       563
         1.0       0.55      1.00      0.71       700

    accuracy                           0.55      1263


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A7.png)


#### Long SMA Window = 10, Short SMA Window = 4, training duration = 10 months (A8)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1676
         1.0       0.56      1.00      0.72      2148

    accuracy                           0.56      3824


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A8.png)


#### Long SMA Window = 10, Short SMA Window = 4, training duration = 3 months (A9)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1834
         1.0       0.56      1.00      0.72      2328

    accuracy                           0.56      4162


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A9.png)


#### Model With 20 day SMA and 50 day SMA, 6 month (A11)


              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1757
         1.0       0.56      1.00      0.72      2244

    accuracy                           0.56      4001


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A11.png)


#### Model With 20 day SMA and 50 day SMA, 10 month (A10)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1631
         1.0       0.56      1.00      0.72      2098

    accuracy                           0.56      3729


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/A10.png)



## Conclusions of tuned SVC Model With Best Results (Question 2)

Interestingly, the majority of the changes I made in SMA window size impacted the strategy returns to a negligible degree. however, this was not always the case, especially when training duration was increased. The models that generated the best returns had training windows of between 50-80% of the entire dataset used for both training and testing. 

Models A2, A3, A6, AND A7 generate nearly-identical returns. They all follow a training window of at least 24 months, most are closer to 30-45 (all of this info is present up above in detail)

It seems that more trading indicators would be needed to generate any real deviation from the trend in strategy returns, regardless of SMA window size.



## Classifer Change: Logistic Regression

#### Model with 4 day SMA and 100 day SMA, 3 month training offset  (LogA1) (Original Training Data)

#### Model with 4 day SMA and 30 day SMA, 3 month training offset  (LogA2)

              precision    recall  f1-score   support

        -1.0       0.45      0.03      0.05      1834
         1.0       0.56      0.97      0.71      2328

    accuracy                           0.56      4162


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/LogA2.png)


#### Model With 20 day SMA and 50 day SMA, 3 month (LogA3)

              precision    recall  f1-score   support

        -1.0       0.43      0.24      0.31      1826
         1.0       0.56      0.75      0.64      2321

    accuracy                           0.53      4147


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/LogA3.png)


#### Model With 20 day SMA and 50 day SMA, 6 month (LogA4)

              precision    recall  f1-score   support

        -1.0       0.48      0.06      0.10      1757
         1.0       0.56      0.95      0.71      2244

    accuracy                           0.56      4001


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/LogaA4.png)


#### Model With 20 day SMA and 50 day SMA, 10 month (LogA5)

              precision    recall  f1-score   support

        -1.0       0.49      0.02      0.05      1631
         1.0       0.56      0.98      0.72      2098

    accuracy                           0.56      3729


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/LogA5.png)


#### Model With 20 day SMA and 50 day SMA, 10 month (LogA6)

              precision    recall  f1-score   support

        -1.0       0.55      0.03      0.06       535
         1.0       0.56      0.98      0.71       665

    accuracy                           0.56      1200


![alt text](https://github.com/rhurst11/Fintech_Module_14_Challenge/blob/main/Starter_Code/Resources/LogA6.png)

## Conclusions of Logistic Regression Model With Best Results (Question 3)

The logistic regression model with the best results was the model trained on roughly 75% of the dataset (45 months) (LogA6). It makes sense that training size is such a critical factor, but it is surprising that variation in our trade indicators had such little impact for both model types. It does seem that a more robust set of trading indicators could benefit strategy returns. 


## Final Evaluation: (Question 4)

Overall, it seems that more technical indicators would be needed to get more variety in model performance. However, it is interesting to see how heavily training size impacts the strategy returns, but almost all strategy returns seem to fall between 2 performance patterns. This duality in model performance makes me think that overfitting could certainly be forcing our models into a buy-side biased behavior. 
