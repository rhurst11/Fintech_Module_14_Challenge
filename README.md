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

#### Model with 4 day SMA and 30 day SMA, 3 month training offset 

              precision    recall  f1-score   support

        -1.0       0.40      0.09      0.15      1826
         1.0       0.56      0.89      0.68      2321

    accuracy                           0.54      4147
   macro avg       0.48      0.49      0.42      4147
weighted avg       0.49      0.54      0.45      4147

#### Model With 20 day SMA and 50 day SMA, 3 month 

####



### Tuning SMA Windows in Conjunction with Training Window Variation


#### Long SMA Window = 30, Short SMA Window = 4, training duration = 24 months

#### Long SMA Window = 30, Short SMA Window = 4, training duration = 30 months

#### Long SMA Window = 30, Short SMA Window = 4, training duration = 45 months




#### Long SMA Window = 50, Short SMA Window = 7, training duration = 24 months

#### Long SMA Window = 50, Short SMA Window = 7, training duration = 30 months

#### Long SMA Window = 50, Short SMA Window = 7, training duration = 45 months




#### Long SMA Window = 100, Short SMA Window = 30, training duration = 24 months

#### Long SMA Window = 100, Short SMA Window = 30, training duration = 30 months

#### Long SMA Window = 100, Short SMA Window = 30, training duration = 45 months


## Tuned Model With Best Results

