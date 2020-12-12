### Decision Trees

##### First we store the path of our folder to get the csv that we are looking for in an easier way.
```r
getwd()
setwd("C:/Users/Carlos Bojorquez/Desktop/Noveno semestre/Mineria/MachineLearning/DesicionThree")
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

##### Fitting Decision Tree Classification to the Training set and installing the rpart library
```r
install.packages('rpart')
library(rpart)
classifier = rpart(formula = Purchased ~ .,
                   data = training_set)
```

##### Predicting the Test set results
```r
y_pred = predict(classifier, newdata = test_set[-3], type = 'class')
y_pred
```

##### Making the Confusion Matrix
```r
cm = table(test_set[, 3], y_pred)
cm
```

##### Visualising the Training set results
```r
install.packages('ElemStatLearn')
library(ElemStatLearn)
set = training_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = predict(classifier, newdata = grid_set, type = 'class')
plot(set[, -3],
     main = 'Decision Tree Classification (Training set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![Training Set](https://lh3.googleusercontent.com/pw/ACtC-3d16NTpg1mFcyqj9oFR4BoaD3KnO2tHnYEC_fUD9YxKNHUWOs1IQ4VCyrB0tIFwwYrhSNxDPiYDK8KzwzjbpV1Q7SYqhmBXDKOW_dqnckv7h5upo-fqaqqAN0GhACh4lh3DWgcwEkZPOMaY1Qqdu4sZ=w1200-h866-no?authuser=1 "Training Set")

##### Visualising the Test set results
```r
set = test_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = predict(classifier, newdata = grid_set, type = 'class')
plot(set[, -3], main = 'Decision Tree Classification (Test set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![Test Set](https://lh3.googleusercontent.com/pw/ACtC-3feqMFC6zC9aC8ZSf4A9d0_qhye4dgnZ3n2g6x2msE9T1wgSqFtzPyNaDBcsaU0-5cpy8ej7DBtmtm5yRFGOWrmAA6NKScd8RBFE6ksJ9m589bd-ytq1c3TUMKhwRccrf4Gym4K6qg4VZFykjPdfBJJ=w1200-h866-no?authuser=1 "Test Set")

##### Plotting the tree
```r
plot(classifier)
text(classifier, cex=0.6)
```

##### In this last plot we can appreciate the decision tree generated in the end of our coding:
![Classifier](https://lh3.googleusercontent.com/pw/ACtC-3de7pYK1v3bTpA231Yj-IRlPIOxk2mouxnQFoFzd_h5IyTzdlMWLNfNywS9ApEz9udLoGILwLLRVOt-MfG8-veEanKnGJ5iVHlmt-pfDu9kSHqIyNlKwWp9OzsaYMnIAe2XUdkLie5nH8KXH3oecDyu=w1200-h866-no?authuser=1 "Classifier")

