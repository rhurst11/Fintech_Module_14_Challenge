# Fintech_Module_14_Challenge

## Original Model
4 day Short SMA 100 day Long SMA, trainiing window = 3 months

              precision    recall  f1-score   support

        -1.0       0.43      0.04      0.07      1804
         1.0       0.56      0.96      0.71      2288

    accuracy                           0.55      4092
   macro avg       0.49      0.50      0.39      4092
weighted avg       0.50      0.55      0.43      4092

### Performance


## Tuning Process

### Increasing Training Window Size 

#### Model with 24 month training window (alternative 1 ... roughly 40% of dataset used for training)


              precision    recall  f1-score   support

        -1.0       0.80      0.00      0.01      1229
         1.0       0.56      1.00      0.72      1565

    accuracy                           0.56      2794
   macro avg       0.68      0.50      0.36      2794
weighted avg       0.67      0.56      0.41      2794

#### Model with 30 month training window (alternative 2 ... roughly 50% of dataset used for training)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1029
         1.0       0.55      1.00      0.71      1280

    accuracy                           0.55      2309
   macro avg       0.28      0.50      0.36      2309
weighted avg       0.31      0.55      0.40      2309

#### Model with 45 month training window (Alternative 3 ... roughly 75% of dataset used for training)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00       476
         1.0       0.56      1.00      0.72       614

    accuracy                           0.56      1090
   macro avg       0.28      0.50      0.36      1090
weighted avg       0.32      0.56      0.41      1090

### Tuning SMA Windows 

#### Model with 4 day SMA and 30 day SMA, 3 month training offset  (A4)

              precision    recall  f1-score   support

        -1.0       0.40      0.09      0.15      1826
         1.0       0.56      0.89      0.68      2321

    accuracy                           0.54      4147
   macro avg       0.48      0.49      0.42      4147
weighted avg       0.49      0.54      0.45      4147

#### Model With 20 day SMA and 50 day SMA, 3 month 

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1826
         1.0       0.56      1.00      0.72      2321

    accuracy                           0.56      4147
   macro avg       0.28      0.50      0.36      4147
weighted avg       0.31      0.56      0.40      4147

####



### Tuning SMA Windows in Conjunction with Training Window Variation



#### Long SMA Window = 30, Short SMA Window = 4, training duration = 45 months (A6)

             precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00       555
         1.0       0.55      1.00      0.71       682

    accuracy                           0.55      1237
   macro avg       0.28      0.50      0.36      1237
weighted avg       0.30      0.55      0.39      1237



#### Long SMA Window = 10, Short SMA Window = 4, training duration = 45 months (A7)

           precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00       563
         1.0       0.55      1.00      0.71       700

    accuracy                           0.55      1263
   macro avg       0.28      0.50      0.36      1263
weighted avg       0.31      0.55      0.40      1263


#### Long SMA Window = 10, Short SMA Window = 4, training duration = 10 months (A8)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1676
         1.0       0.56      1.00      0.72      2148

    accuracy                           0.56      3824
   macro avg       0.28      0.50      0.36      3824
weighted avg       0.32      0.56      0.40      3824


#### Long SMA Window = 10, Short SMA Window = 4, training duration = 3 months (A9)

              precision    recall  f1-score   support

        -1.0       0.00      0.00      0.00      1834
         1.0       0.56      1.00      0.72      2328

    accuracy                           0.56      4162
   macro avg       0.28      0.50      0.36      4162
weighted avg       0.31      0.56      0.40      4162



## Tuned Model With Best Results

