### SVM

##### First we load our csv file with:
```r
mydata <- read.csv(file.choose())
```

###### Once we have the csv Social Network Ads loaded we will occupy the Estimated Salary and Purchased columns
```r
dataset = read.csv('Social_Network_Ads.csv')
dataset = dataset[3:5]
```

##### We code the characteristic of the target as a factor
```r
dataset$Purchased = factor(dataset$Purchased, levels = c(0, 1))
```

##### We load the Catools library and we put the seed to be able to create the split to the data of a 0.75 and thus also to have the variables of training and test.
```r
library(caTools)
set.seed(123)
split = sample.split(dataset$Purchased, SplitRatio = 0.75)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)
```

##### The data is normalized between -1 and 1, in the Age and Estimated Salary columns
```r
training_set[-3] = scale(training_set[-3])
test_set[-3] = scale(test_set[-3])
```

##### We load the package e1071 and place the classifier of our svm function
```r
library(e1071)
classifier = svm(formula = Purchased ~ .,
                 data = training_set,
                 type = 'C-classification',
                 kernel = 'linear')
svm
```

##### We make the prediction with the test data
```r
y_pred = predict(classifier, newdata = test_set[-3])
y_pred
```

##### We have the matrix of confusion
```r
cm = table(test_set[, 3], y_pred)
cm
```

##### We used "ElemStatLearn" on X1 and X2 this section creates the red / green background region. In plot it finishes the background, it would be the real data of the graph, in contour it creates the limits of the plotted values, it means that it creates the division line between red and green. Then we have Point here we review all data from y_pred and use ifelse to color the data points.
```r
library(ElemStatLearn)
set = training_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = predict(classifier, newdata = grid_set)
plot(set[, -3],
     main = 'SVM (Training set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
