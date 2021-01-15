### Random Forest

##### First we store the path of our folder to get the csv that we are looking for in an easier way.
```r
getwd()
setwd("C:/Users/Carlos Bojorquez/Desktop/Noveno semestre/Mineria/MachineLearning/RandomForest")
getwd()
```

##### Importing the dataset
```r
dataset = read.csv('Social_Network_Ads.csv')
dataset = dataset[3:5]
```

##### Encoding the target feature as factor
```r
dataset$Purchased = factor(dataset$Purchased, levels = c(0, 1))
```

##### Splitting the dataset into the Training set and Test set
```r
library(caTools)
set.seed(123)
split = sample.split(dataset$Purchased, SplitRatio = 0.75)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)
```

##### Feature Scaling
```r
training_set[-3] = scale(training_set[-3])
test_set[-3] = scale(test_set[-3])
```

##### Fitting Random Forest Classification to the Training set and installing the Random Forest library
```r
install.packages('randomForest')
library(randomForest)
set.seed(123)
classifier = randomForest(x = training_set[-3],
                          y = training_set$Purchased,
                          ntree =10)
```


##### Predicting the Test set results
```r
y_pred = predict(classifier, newdata = test_set[-3])
y_pred
```
![Y pred](https://lh3.googleusercontent.com/pw/ACtC-3coBTbgvNR74nBVaIxjKrSvsZtcTQ6a8DNhdLjzYhxDI-kE-4tr-4V1GY4I-fUW9VrQ5Vz6-wLAvlozvGl3BQxtTadhWIKIw2AIphiMCTH8rxNEkb2tFQT1Gt93VqUYCQXtDSwrdlp3TBH0EJKeTvyj=w1027-h228-no?authuser=1 "Y pred")

##### Making the Confusion Matrix
```r
cm = table(test_set[, 3], y_pred)
cm
```
![Cm](https://lh3.googleusercontent.com/pw/ACtC-3dLL2DBRPNaBjiZPyxX7-taI_xJB241MudE7Z2-LpTphC89LddIKmVSDcZEwwR7euGxrUbq_Ju-mxFv_W4-yhNcVwQtwsvuQ5ZHn92pr1U2RnwqrMBhP4u7LWT9pyqDLQx4VpxMdyZvU1Ib9orTZ9an=w364-h132-no?authuser=1 "Cm")

##### Visualising the Training set results
```r
library(ElemStatLearn)
set = training_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = predict(classifier, grid_set)
plot(set[, -3],
     main = 'Random Forest Classification (Training set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![Training Set](https://lh3.googleusercontent.com/pw/ACtC-3dPPXSLduWQA94yW0zoTok8zrKZFS8OHl_kTIqpypNGCJXA28MO-rSC53WzWpcoTMTCAUYYKEv-NkK067Xv_p1dMdwfy987BzDJ5UUqquXzzzfHa7X9x49pqg9tB3CGNY4Io2BD-KJFg6eL2dZx9qE0=w1200-h866-no?authuser=1 "Training Set")

##### Visualising the Test set results
```r
library(ElemStatLearn)
set = test_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = predict(classifier, grid_set)
plot(set[, -3], main = 'Random Forest Classification (Test set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![Test Set](https://lh3.googleusercontent.com/pw/ACtC-3fyVxLndl8hlcqbBiKZxPrFcvw0ccR1Bvn28IYOCvx-fNVQ6KRNavG-MNE4_5jdWTQWprAMMmmFSu32hcodm9E15v7Wm8X8z5gHuQPMJtbWzzWJmSX-8suYgZSA5iQT_xzht6uqyysS2dwjwFIFz_JM=w1200-h866-no?authuser=1 "Test Set")

##### Choosing the number of trees
```r
plot(classifier)
```
![Classifier](https://lh3.googleusercontent.com/pw/ACtC-3c9YlvKVZ6ClU4Cio_IfebFnuaYewd0mJv_JJmjvTB9E2vPt3gG24I_mK7SaHb2lo7CuuFLTbj6_lPFDqW7Tsak0zDLfCU7UFPBb6RVRj8UP6Ik3AvREMqGTkmJnG435XdWJg2LY6wwHCowXjoVg5Eu=w1200-h866-no?authuser=1 "Classifier")
