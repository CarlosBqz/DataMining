### Multiple Linear Regression

### Multiple Linear Regression

##### First we store the path of our folder to get the csv that we are looking for in an easier way.
```r
getwd()
setwd("C:/Users/Carlos Bojorquez/Desktop/Noveno semestre/Mineria/MachineLearning/MultipleLinearRegression")
getwd()
```

##### Importing the dataset
```r
dataset <- read.csv('50_Startups.csv')

```
##### Encoding categorical data. Filtering the data in 3 states, New York, California, Florida
```r
dataset$State = factor(dataset$State,
                       levels = c('New York', 'California', 'Florida'),
                       labels = c(1,2,3))
```
##### Showing the dataframe
```r
dataset
```

##### Splitting the dataset into the Training set and Test set, we already have installed caTools in our R environment.
```r
library(caTools)
set.seed(123)
split <- sample.split(dataset$Profit, SplitRatio = 0.8)
training_set <- subset(dataset, split == TRUE)
test_set <- subset(dataset, split == FALSE)
```

##### Fitting Multiple Linear Regression to the Training set regressor = lm(formula = Profit ~ R.D.Spend + Administration + Marketing.Spend + State)
```r
regressor = lm(formula = Profit ~ .,
               data = training_set )
```

##### Showing the summary of our model
```r
summary(regressor)

```
![Summary](https://lh3.googleusercontent.com/pw/ACtC-3dsrWmAkTeN4r-6c61RM7SKCwhq4QcGwuSAn2UL9U8pWos1tUWychLpKgN4H4y2EzzX1AxFEZ6CkeOgiBsoc_4D7tVgtkP101v92EW33V6wLVn6nsu49T38B0S6_TGJG49rrKWocPWkOqqI72J3ZDTB=w617-h460-no?authuser=1 "Summary")

##### Prediction the Test set results
```r
y_pred = predict(regressor, newdata = test_set)

```
##### Showing our prediction of the test results
```r
y_pred
```
![Predict Y](https://lh3.googleusercontent.com/pw/ACtC-3cUaAuTR77JrCCRDBhH_-756HuMKPm5eE4o_yZ8WYxa0Lmba-H6aAhQbQdHXywUcU02lMbP1SCZ5WyjuVPZJSfxy2WTpSLrjO63YHi0ZzOBRNIvbUYtx20AJt1GiQt_DvrnrLq_iWMOTxyRb6FCO1up=w986-h88-no?authuser=1 "Predict Y")

##### Assigment: visualize the siple liner regression model with R.D.Spend 

##### Building the optimal model using Backward Elimination
```r
regressor = lm(formula = Profit ~ R.D.Spend + Administration + Marketing.Spend + State,
               data = dataset )
summary(regressor)
```
![Summary 1](https://lh3.googleusercontent.com/pw/ACtC-3cziLkz1tp51orpakQCTzTNWOnxUs0_8Eu6IYWH6nyvQK1Wo2ZbUlctU0h1jo7FixYN3fQWwlWQWytGJJEyWo7LUbcMi6LnZle8TcSoC_4enclIMOtseXFNaUNAhWsS9uR21lG4x_wrYrvm97_Ew5kI=w687-h477-no?authuser=1 "Summary 1")

```r
regressor = lm(formula = Profit ~ R.D.Spend + Administration + Marketing.Spend,
               data = dataset )
summary(regressor)
```
![Summary](https://lh3.googleusercontent.com/pw/ACtC-3dArR-m4xuXY2BNkpGF3YioYvMkeoT8X6ZahFTyaKcwq_Ka_1rslAcm466NHdCcu1iR6Z_czxPS9reVcyETjac8Nzs8tZX0aWzV6ZUbJf0V9n_z8lxZ1-fSfhBJstFI2bvATMLSDk48Rf9d_Jp_-JcO=w668-h431-no?authuser=1 "Summary")

```r
regressor = lm(formula = Profit ~ R.D.Spend + Marketing.Spend,
               data = dataset )
summary(regressor)
```
![Summary 3](https://lh3.googleusercontent.com/pw/ACtC-3ft6ez4Q-gIm6h552r5maxQjC5G_lGdWQEPG8nBGok0Zs5oaTtdwD4hm-VboEXPmPx7l04QlDoHxjwGvzxhn3HvpPH7kYNs25lTvvVapCg-UsVikYuCbC612fDJS9xPV-OG6ulU7LHDO2aQz4ftsxug=w648-h390-no?authuser=1 "Summary 3")

```r
regressor = lm(formula = Profit ~ R.D.Spend + Marketing.Spend,
               data = dataset )
summary(regressor)
```
![Summary 4](https://lh3.googleusercontent.com/pw/ACtC-3fSrogDcARlvmbvvL5j6ZK2MNjQkhPXGaRYyFNfPyYf4xt92TWrQe2-liAlBQQ4gzZGZKNrEsUAUGuCj6JjfSUABH4bb4CSpWBDwsM9dgU3kpLHkXCAAG-rFeG6zlm9-r02sjVVcQzAP81kz3B4sb-c=w659-h384-no?authuser=1 "Summary 4")
```r
y_pred = predict(regressor, newdata = test_set)
y_pred
```
![Predict Y ](https://lh3.googleusercontent.com/pw/ACtC-3dA5q0D3jvAezpVgH6_L5iiLx44hITh_4AwxLLrz060ZbY1fBelnaKuS44cDq8z4UTsQRlfieh3JsbP6Z4DlUabfQwSHRLrKzcgwlHzSMdFLwx9HExPewmvTz3DDN313dre_6rLOPVMlPNazhiOE-MA=w986-h86-no?authuser=1 "Predict Y ")


##### Homework analise the follow atomation backwardElimination function 
```r
backwardElimination <- function(x, sl) {
  numVars = length(x)
  for (i in c(1:numVars)){
    regressor = lm(formula = Profit ~ ., data = x)
    maxVar = max(coef(summary(regressor))[c(2:numVars), "Pr(>|t|)"])
    if (maxVar > sl){
      j = which(coef(summary(regressor))[c(2:numVars), "Pr(>|t|)"] == maxVar)
      x = x[, -j]
    }
    numVars = numVars - 1
  }
  return(summary(regressor))
}

SL = 0.05
```
##### dataset = dataset[, c(1,2,3,4,5)]
```r
training_set
backwardElimination(training_set, SL)
```
##### Result of applying backward elimination to the training set
![Training set](https://lh3.googleusercontent.com/pw/ACtC-3fY_y4Jp800ATV7wwSoHe9KFVf1_o78l9vhDM2ML4vbCyot1Kf4XkfI3zOMq5rVEfV4LtWaCdJ2EGWA2aSWXSIpKjQO0OQR6jxRHYyq1Mg9oZSpcJ1i3XR2cgK6qGKMW9ygccCTb79looDEGndL1K8y=w617-h370-no?authuser=1 "Training set")
