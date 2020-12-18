<div align="center">

**Instituto Tecnológico de Tijuana**

Departamento de Ciencias y Computación

Ingeniería en Sistemas Computacionales
 
 [![](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)](https://upload.wikimedia.org/wikipedia/commons/2/2e/ITT.jpg)

**Title:**
Evaluation 4

**Subject:**
BDD-1703 SC9A Minería de Datos

**Unit:**
 IV

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
Tijuana, Baja California, December 18, 2020. 
</div>


## Introduction
In the following documentation we will apply the K means model to a data set called iris in which the graphs and final results will be revealed.

We will solve the following instructions to be evaluated in the corresponding unit:
- Implement the K-Means grouping model with the Iris.csv dataset found at https://github.com/jcromerohdz/iris using the kmeans () method in R. Once the grouping model is obtained do the corresponding data visualization analysis.
- At the end of the development, explain in detail what the K-Means grouping model consists of and what were your observations in the data visualization analysis.


## Development

##### 1. First we store the path of our folder to get the csv we are looking for in an easier way.
```r
getwd()
setwd("C:/Users/Carlos Bojorquez/Desktop/Noveno semestre/Datos Masivones/iris-master")
getwd()
```

##### 2. We import the dataset and tell it that we are only going to use vectors from 1 to 4.
```r
dataset = read.csv('iris.csv')
dataset = dataset[1:4]
```

##### 3. We install the cluster library.
```r
install.packages("cluster")
library(cluster)
```

##### 4. We put our seed of randomness, in the kmeans function, it is necessary to establish the center, which is the number of groups we want and they are grouped. In this case, we know that this value will be 3 and that is going to be set.
```r
set.seed(101)
irisCluster <- kmeans(df[,1:4], center=3, nstart=20)
irisCluster
```

##### 5. We plot the clusters.
```r
library(cluster)
clusplot(iris, irisCluster$cluster, color=T, shade=T, labels=0, lines=0)
```

![](https://lh3.googleusercontent.com/pw/ACtC-3e2QaKZJfm8ZIWW0CvwwqN5yRp17RaHnT-uzYGkGESzD2ZsCpXiR-fSk7V6X6B_HwHrpOBhCe6ceIIcryAVKvb3RLtCmNpdaZXEzL2p_2DP-6ALcU9_Bep0O83H4tPMerOoZMIhkmcap5Di8lA0YrOP=w1259-h801-no?authuser=1)

##### 6. We apply the elbow method to better see the implementation of the data.
```r
tot.withinss <- vector(mode="character", length=10)
for (i in 1:10){
        irisCluster <- kmeans(df[,1:4], center=i, nstart=20)
        tot.withinss[i] <- irisCluster$tot.withinss
}
```

##### 7. We visualize the method
```r
plot(1:10, tot.withinss, type="b", pch=19)
```

![](https://lh3.googleusercontent.com/pw/ACtC-3dvnQbTtm6nxLtFWbdsyNojZ5kxk90WJBjRpN3wEwOjirzQH6jZMSMNt0iQ3s-xrk5PZINd0MoUu3Nw9wMMlD9q4ZD5Pwao1m_vs6mvLu8PWnPz9cH9PUZnaCyRW4hBlVKXQ3tjUtY65OSmYx9xfdbG=w1104-h518-no?authuser=1)

## Conclusion
As we can see, the k means method is to be able to group similar data and find out what they are compatible with and therefore it needs a fixed number that will be the divided groups of certain data that are similar. As we could see at the end of the graph, the breaking point was 3 and those are the groups that were used in the first graph where we could appreciate the difference between the setosa and the verginica, versicolor groups that had a lot of noise as they came together .
