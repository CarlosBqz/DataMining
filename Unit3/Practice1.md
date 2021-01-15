### Simple Linear Regression

##### First we store the path of our folder to get the csv that we are looking for in an easier way.
```r
getwd()
setwd("C:/Users/Carlos Bojorquez/Desktop/Noveno semestre/Mineria/MachineLearning/SimpleLinearRegression")
getwd()
```

##### Importing the dataset
```r
dataset <- read.csv('Salary_Data.csv')
```

##### Splitting the dataset into the Training set and Test set and running the following install: Install.packages('caTools')
```r
Install.packages('caTools')
library(caTools)
set.seed(123)
split <- sample.split(dataset$Salary, SplitRatio = 2/3)
training_set <- subset(dataset, split == TRUE)
test_set <- subset(dataset, split == FALSE)
```

##### Fitting Simple Linear Regression to the Training set
```r
regressor = lm(formula = Salary ~ YearsExperience,
               data = dataset)
summary(regressor)
```

![Summary](https://lh3.googleusercontent.com/pw/ACtC-3cWS9KMvWw1-B91aYwEG6VRMpTXxlV2QIUOJIbcN1Buqahh0MqlL5JOf_c7OJY376sZOckZTmkb3-XRgihBiFDkS58llil0pqrX1wHbjBPVbWxT2Yc3OweiNSD8krLECRNFNZ6mx9g5yPi_vI-6zCCq=w615-h373-no?authuser=1 "Summary")

##### Predicting the Test set results
```r
y_pred = predict(regressor, newdata = test_set)

```
##### Visualising the Training set results using ggplot2
```r
library(ggplot2)
ggplot() +
  geom_point(aes(x=training_set$YearsExperience, y=training_set$Salary),
             color = 'red') +
  geom_line(aes(x = training_set$YearsExperience, y = predict(regressor, newdata = training_set)),
            color = 'blue') +
  ggtitle('Salary vs Experience (Training Set)') +
  xlab('Years of experience') +
  ylab('Salary')
```
![Training Set](https://lh3.googleusercontent.com/pw/ACtC-3eTfyX0Fz29qWW90TCgt-vK6R-D6HUXzMYsmqQXLwcs6falnhoRtnEL9Jb95ooNoyn7g7mFtq6OPowrVuagTiE-qxBUOkgrERJItR_PZCp8tFn3GogNvLiILzN51OHxL3JQdZ8CwxK6QMgA2o0f3BgH=w1200-h866-no?authuser=1 "Training Set")

##### Visualising the Test set results
```r
ggplot() +
  geom_point(aes(x=test_set$YearsExperience, y=test_set$Salary),
             color = 'red') +
  geom_line(aes(x = training_set$YearsExperience, y = predict(regressor, newdata = training_set)),
            color = 'blue') +
  ggtitle('Salary vs Experience (Test Set)') +
  xlab('Years of experience') +
  ylab('Salary')
  ```
![Test Set](https://lh3.googleusercontent.com/pw/ACtC-3cttLnBNDfH_espDeUGVRKFEefK5Rc_4oL5Pn7fKbst0IbKSjihxLiR75nmnplSMZOo6eSPoFsENmLaFDfixJBjo0nAoIpnUPK0dqzTMoukosI1S7ivqBZp0xlNS_9Ye8LNOm6F1wTpUAupRK1LVfaw=w1200-h866-no?authuser=1 "Test Set")

#### Analyzing
We can appreciate in both plots two important things:
- Both of the plots behave in the same way, following a straight line that gets higher based on the years of experience.
- People with more years of experience gets a higher salary.
