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
![](https://lh3.googleusercontent.com/pw/ACtC-3d8pbx-i-iuBGOJD8cI6Z0WZ66N1_qXi8VBc2o5RZe224EVCM3uuSwfuT9b89c6OB398FR35nAiSQyu_wppwxv5C3Of2ZRmF6F8VtnSJGqK-HI9-O7Z1yeirePEuKOIICE0Ih7tmOOQbaIQdC51mcg3=w660-h359-no?authuser=0)

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
![](https://lh3.googleusercontent.com/pw/ACtC-3eoTO5MfxweNjZdYdVMK2e7PnnDDRVJvLUn4FHgBnCkMc_7bA_n3bXNPPXyCYcU2PN6RIiO00uK84wG6hYekqEZ9l3SdYUtCzCYHrqnY4eMj8LsrpKq9HP7f2g2q6AI7W0oCqWVhKQnlt3ja5n1W7h4=w661-h394-no?authuser=0)

