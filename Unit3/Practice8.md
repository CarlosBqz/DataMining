### K-MEANS

##### We import our csv file
```r
dataset <- read.csv(file.choose())
```

##### We import the range of data
```r
dataset = dataset[3:5]
```

##### We apply the elbow method preparing the vector for the cycles and obtaining the clusters and we apply our seed together with the
```r
set.seed(6)
wcss = vector()
for (i in 1:10) wcss[i] = sum(kmeans(dataset, i)$withinss)
plot(1:10,
     wcss,
     type = 'b',
     main = paste('The Elbow Method'),
     xlab = 'Number of clusters',
     ylab = 'WCSS')
```
    
##### Graphic
![](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.definicionabc.com%2Fcomunicacion%2Fgrafica.php&psig=AOvVaw3Kx5uG6F7xrPhz3CIKeP-4&ust=1608059005446000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCMCqwOSUzu0CFQAAAAAdAAAAABAD.jpg)

##### The K-means method is adjusted to the data set
```r
set.seed(29)
kmeans = kmeans(x = dataset, centers = 5)
y_kmeans = kmeans$cluster
```

##### We import the cluster library and plot the results
```r 
library(cluster)
clusplot(dataset,
         y_kmeans,
         lines = 0,
         shade = TRUE,
         color = TRUE,
         labels = 2,
         plotchar = FALSE,
         span = TRUE,
         main = paste('Clusters of customers'),
         xlab = 'Annual Income',
         ylab = 'Spending Score')
        ```
        
##### Graphic
![]()

