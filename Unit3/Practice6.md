## Logistic Regression

##### First we store the path of our folder to get the csv that we are looking for in an easier way.

```r
getwd()
setwd("C:/Users/Carlos Bojorquez/Desktop/Noveno semestre/Mineria/MachineLearning/LogisticRegression")
getwd()
```

##### Importing the dataset

```r
dataset <- read.csv('Social_Network_Ads.csv')
dataset <- dataset[, 3:5]
```

##### Setting the seed and splitting the dataset into the Training set and Test set

```r
library(caTools)
set.seed(123)
split <- sample.split(dataset$Purchased, SplitRatio = 0.75)
training_set <- subset(dataset, split == TRUE)
test_set <- subset(dataset, split == FALSE)
```

##### Feature scaling

```r
training_set[, 1:2] <- scale(training_set[, 1:2])
test_set[, 1:2] <- scale(test_set[, 1:2])
```

##### Fitting Logistic Regression to Training set

```r
classifier = glm(formula = Purchased ~ .,
                 family = binomial,
                 data = training_set)
```

##### Predicting the Test set results

```r
prob_pred = predict(classifier, type = 'response', newdata = test_set[-3])
prob_pred
y_pred = ifelse(prob_pred > 0.5, 1, 0)
y_pred
```
![Prob Predict](https://lh3.googleusercontent.com/pw/ACtC-3fL2hM4M6C_Zf11wGykcTZI_5yQ_zxwAKdM7BGtGKWSgTWBnnNxtKFfw5f4kDIoHnXp95jgG59mUtakUAI4QGyrTuzwh_kszhsnwDBOqNcL3CUMZ-TQ1OHHQK9ug_seoWHxlGjz0dXqLGt8laIPEXk2=w1042-h571-no?authuser=1 "Prob Predict")

![Y Predict](https://lh3.googleusercontent.com/pw/ACtC-3eb2i5H1yK_9Tu35nzVVSTVIkBDzxF88VxOf7lBBmmAPrDdqaS6RQnLHJp7aAhEg02sejZPbGm6tvIc3BpgZdxySlwYrjeVPF-QDUNjMJMCEgsH569g9Qfne1TZa3wGl_PZTml89EPVJihzrZBpjNHz=w1020-h195-no?authuser=1 "Y Predict")
##### Making the Confusion Metrix
```r
cm = table(test_set[, 3], y_pred)
cm
```
![CM](https://lh3.googleusercontent.com/pw/ACtC-3eHRuS9yeXeDXQfwkm_g3oZ_xX5ntzl1XrdqwyVCjEqH_Lwv2K_-krJLmYfc8btGX3uOCCg1nreJVskN75CX7zPtEsbaFvE1yja6nssCY5EBMFCfcyf645u4KNgF4NTq8FhKo2OMazpxLwaIfRLC3Di=w116-h115-no?authuser=1 "CM")

##### Generating different plots to visualize the behavior of both test and training set, we can appreciate that all the plots almost follows the same behavior.

```r
library(ggplot2)
ggplot(training_set, aes(x=EstimatedSalary, y=Purchased)) + geom_point() + 
        stat_smooth(method="glm", method.args=list(family="binomial"), se=FALSE)
```
![](https://lh3.googleusercontent.com/pw/ACtC-3dro5hHNBg0M6bNxBzkHJqQ3mFRcNc7vXkAqOmEm7cZo9nO9VKG_joUaMHAEN_22BZgUkxUF1MvDpbdHh5lU-9pVngsmEthzE7pstVGgOMiAibrRRK7UXFU3E6PL66NMDBFpISDiY4nHenm-5Qlod-G=w739-h484-no?authuser=1)
```r
ggplot(training_set, aes(x=Age, y=Purchased)) + geom_point() + 
        stat_smooth(method="glm", method.args=list(family="binomial"), se=FALSE)
```
![](https://lh3.googleusercontent.com/pw/ACtC-3cmlJ_JuGYsb6NxLnEKKCJDKKnyw_34_DubgJpJF_zcjBjHdg3kBtKi_h1AbYeZjMI_yoWMpx05mNh5KAH2FxQELGDWlkk2MP2qjLBaQFHRwRmUW_9OyjrU-QwV3hfgBjrApHVG_r-12IYWl-JspIzB=w739-h484-no?authuser=1)
```r
ggplot(test_set, aes(x=EstimatedSalary, y=Purchased)) + geom_point() + 
        stat_smooth(method="glm", method.args=list(family="binomial"), se=FALSE)
```
![](https://lh3.googleusercontent.com/pw/ACtC-3c5gtWXDs_X6zQ9Rl6bZ6NI9VNdSHrB8hcmOw4lXzErFM4bjLKnL4KKT0VZHJGyF87vC_GOfAVnoRxjhiJNwQdKPpq72HQZz0V_2RrliDNdUfsa4o2OVyiN03ipzK7OIFhZDMjSBSPOvl-477Y_UHTX=w739-h484-no?authuser=1)
```r
ggplot(test_set, aes(x=Age, y=Purchased)) + geom_point() + 
        stat_smooth(method="glm", method.args=list(family="binomial"), se=FALSE)
```
![](https://lh3.googleusercontent.com/pw/ACtC-3fiD3ojZTfx4eW0PXUJYr71sspVBLyuSCvdGavHXco4TxjjwdSIz_Mza3C8vh4yeWJkliCPjGPhmyrK36eUcJY0463Q0HbaoTs_TUid1gTpmJA2c379I7P4r24Qfo4qyWb_rOvPw5XmL4CZFUBZHYym=w739-h484-no?authuser=1)

##### Visualization the Training set result

```r
library(ElemStatLearn)
set = training_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
prob_set = predict(classifier, type = 'response', newdata = grid_set)
y_grid = ifelse(prob_set > 0.5, 1, 0)
plot(set[, -3],
     main = 'Logistic Regression (Training set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![](https://lh3.googleusercontent.com/pw/ACtC-3doxfttzDw2Vx7GAg8Y8INNJURQ9zflt1J-ZVQjoRmI9mnMlxZNckhracsUueW5delLoKb3Xir_tD3Gu5dPv9GoELlDwaEACap0McFJNmvQtGlQwJ7lpM4xHEzy3UlVhkznFvfd6sOJfcr8mODFa-u2=w739-h484-no?authuser=1)
##### Visualising the Test set results
```r
library(ElemStatLearn)
set = test_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
prob_set = predict(classifier, type = 'response', newdata = grid_set)
y_grid = ifelse(prob_set > 0.5, 1, 0)
plot(set[, -3],
     main = 'Logistic Regression (Test set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![](https://lh3.googleusercontent.com/pw/ACtC-3ca8kOq859qmOQxOPjQ4FklFb9miOGBB3Q0Lw5nut9oze-H3Od-mV21lAteo2DOlHVbZ9benBn4bt_gRt-UwVwCVRLuvDLZykes9Q829keTZVn2BBqfgjoT0gd21TOM1UAr36poSrjNRBw8OWlJR6B7=w739-h484-no?authuser=1)