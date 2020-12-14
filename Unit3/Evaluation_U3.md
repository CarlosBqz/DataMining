<div align="center">

**Instituto Tecnológico de Tijuana**

Departamento de Ciencias y Computación

Ingeniería en Sistemas Computacionales
 
 [![](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)

**Title:**
Evaluation 3

**Subject:**
BDD-1703 SC9A Minería de Datos

**Unit:**
 III

**Professor:**
JOSE CHRISTIAN ROMERO HERNANDEZ

**Student:**

Bojórquez Vargas Carlos Francisco
16211977

Garcia Rincon Daniel Gerardo 
16212002

**Group:**
SC9A

**Date:**
Tijuana, Baja California, December 14, 2020. 
</div>


### Evaluation 3 Naive Bayes

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

##### Install e1071 library and ElemStatLearn
##### ElemStatLearn is not available at the moment, so we decided to install the package manually.
```r
install.packages("e1071")
install.packages("ElemStatLearn")
library(e1071)
library(caTools)
library(ElemStatLearn)
```

##### Applying the factor function to the column named Purchased
```r
dataset$Purchased = factor(dataset$Purchased, levels = c(0, 1))
```

##### Setting the seed and making the split for the test and training set.
```r
set.seed(123)
split = sample.split(dataset$Purchased, SplitRatio = 0.75)
training_set = subset(dataset, split == TRUE)
test_set = subset(dataset, split == FALSE)
```

##### Applying scale to the dataset to standarize the data.
```r
training_set[-3] = scale(training_set[-3])
test_set[-3] = scale(test_set[-3])
```

##### Setting naiveBayes using the training set data.
```r
classifier = naiveBayes(formula = Purchased ~ .,
                        data = training_set,
                        type = 'C-classification',
                        kernel = 'linear')
```

##### Making predictions of Naive Bayes
```r
y_pred = predict(classifier, newdata = test_set[-3])
y_pred
```
![](https://lh3.googleusercontent.com/pw/ACtC-3e946GObo202ZYsqGpJlHF7aIMZHsgLxsUFLf_9G_iQGn3ObCl2tFPYw87BUNI7mdjiNM887YiaFwMDNjYX2-8gqErXk0u0YCYqZbdnd01KbzprvRHMCOnB2kgTTR-3G3W5lNBGgkZsOKgyRhqsk3yw=w1035-h87-no?authuser=1)
##### Confusion Matrix.
```r
cm = table(test_set[, 3], y_pred)
cm
```
![](https://lh3.googleusercontent.com/pw/ACtC-3dpMErQBDQ0R9SPFsLwmXvfcK8Zwik-KzpNfF3bD5U3eisIUePgQsALLUoqk3ElfH7pWPY6lMxPmdFIHrnOrmzsOWzRCG90Kkt-wnHENeYB4xoF8NRLkfXiOQ4FD1wbuzYjiQ8_x9g6R3yhTxcECXJu=w114-h113-no?authuser=1)
##### Visualization of the results of the Training Set
```r
set = training_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = predict(classifier, newdata = grid_set)
plot(set[, -3],
     main = 'Naive Bayes (Training set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![](https://lh3.googleusercontent.com/pw/ACtC-3dADTUWSFEtKowuc24PuvP_bUqB8EPxdsmZbFBp1wkPHs3XMaiApNzVmQaxrX9-um3ejWrfOO8iFo1h_eD1CfrpqMqGjwpdouMuAytmuW2s03lJx-KXlGJRwbq3tH4N2U6fzU5U-F5wvp9hdJ7j5g2M=w739-h484-no?authuser=1)
##### Visualization of the results of the Test set.
```r
set = test_set
X1 = seq(min(set[, 1]) - 1, max(set[, 1]) + 1, by = 0.01)
X2 = seq(min(set[, 2]) - 1, max(set[, 2]) + 1, by = 0.01)
grid_set = expand.grid(X1, X2)
colnames(grid_set) = c('Age', 'EstimatedSalary')
y_grid = predict(classifier, newdata = grid_set)
plot(set[, -3], main = 'Naive Bayes (Test set)',
     xlab = 'Age', ylab = 'Estimated Salary',
     xlim = range(X1), ylim = range(X2))
contour(X1, X2, matrix(as.numeric(y_grid), length(X1), length(X2)), add = TRUE)
points(grid_set, pch = '.', col = ifelse(y_grid == 1, 'springgreen3', 'tomato'))
points(set, pch = 21, bg = ifelse(set[, 3] == 1, 'green4', 'red3'))
```
![](https://lh3.googleusercontent.com/pw/ACtC-3daDUpZapcP5fQDKNFMgLPv9CJqK2itSJmQV_UCfYravGwzNnJQ6Fyyl5LB566DB7DviK93VwXnXYHjqeBLAQxcoXRQzZPAGmM-qjj8h7rAjbZO2nyP9lNs-DWwotGubxrSUP2RB-oSlEuPc3TeQlQC=w739-h484-no?authuser=1)
