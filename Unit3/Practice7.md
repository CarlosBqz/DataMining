### KNN

##### First we load our csv file with:
```r
mydata <- read.csv(file.choose())
```

##### Assign set to data
```r
dataset = dataset[3:5]
```

##### Coding of the target function as a factor
```r
dataset$Purchased = factor(dataset$Purchased, levels = c(0, 1))
```

##### Import caTools library, implement random seed and separate training and test set data.
```r
library(caTools)
set.seed(123)
split = sample.split(dataset$Purchased, SplitRatio = 0.75)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)
```

##### We standardize data
```r
training_set[-3] = scale(training_set[-3])
test_set[-3] = scale(test_set[-3])
```

##### We add the KNN function to the training data and the prediction of the test results.
```r
library(class)
y_pred = knn(train = training_set[, -3],
             test = test_set[, -3],
             cl = training_set[, 3],
             k = 5,
             prob = TRUE)
```

##### We make the matrix of confusion
```r
cm = table(test_set[, 3], y_pred)
```

##### We visualize the results of our training set by defining the x1 and x2 variables together with our two grids defining the parameters of ranges between points as well as their identification colors and thickness.
```r
library(ElemStatLearn)
set = training_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = knn(train = training_set[, -3], test = grid_set, cl = training_set[, 3], k = 5)
plot(set[, -3],
     main = 'K-NN (Training set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
##### Graphic
![](https://lh3.googleusercontent.com/pw/ACtC-3fTLGp54MdlQLGRpvWdOh6vI4ml-N9hIiqeZWcDRkFFG6grutmqrrL5XpeZnVXV2xKnNpq9RnQ1NQ-jhfjQu7IWWNwNE9KmFNAAYBRwtl1p4UP9-QdipOnD3I-cSegGg9heaPLjzvjIemKNvWW6yj39=w634-h370-no?authuser=0)

##### We do the same but now with the test set data
```r
library(ElemStatLearn)
set = test_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = knn(train = training_set[, -3], test = grid_set, cl = training_set[, 3], k = 5)
plot(set[, -3],
     main = 'K-NN (Test set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```

##### Graphic
![](https://lh3.googleusercontent.com/pw/ACtC-3eigcSR4gtnm3FxaSIRqs41wLEVxloSnG5bMB3cvN6-WB-sn1jvYcPQHayh6t1gqymS507LPNUCxPhakgEjkNqJIqyCGzsdQn3uROXpBvOc2ZeUeypFglyRPZpzdOxKtbDNjvbdPGJGtZrJfd2qocC_=w641-h421-no?authuser=0)
