# Clustering \(k-means\)

Power of R is wide range of packages with advanced algorithms ready-to-use. In this example we'll use **k-means** for custom users segmentation.

> **Unsupervised learning: k-Means**
> _k-means clustering aims to partition n observations into k clusters in which each observation belongs to the cluster with the nearest mean \(Source: __****[Wikipedia](https://en.wikipedia.org/wiki/K-means_clustering)****__\)
> _

Because this example needs custom instalation of Google Analytics tracking \(content grouping, fingerprint\), I've prepared special dataset for thus purpose. You can find complete code below.

```r
# K-Means Cluster Analysis

# load data into R
# you can download data from Google Analytics API or download sample dataset
# source('ga-connection.R')

# download and preview sample dataset
download.file(url="https://raw.githubusercontent.com/michalbrys/R/master/users-segmentation/sample-users.csv",
              "sample-users.csv",
              method="curl")
gadata <- read.csv(file="sample-users.csv", header=T, row.names = 1)
head(gadata)

# clustering users in 3 groups
fit <- kmeans(gadata, 3)

# get cluster means 
aggregate(gadata,by=list(fit$cluster),FUN=mean)

# append  and preview cluster assignment
clustered_users <- data.frame(gadata, fit$cluster)
head(clustered_users)

# visualize results in 3D chart

#install.packages("plotly")
library(plotly)

plot_ly(clustered_users, 
        x = clustered_users$beginner_pv, 
        y = clustered_users$intermediate_pv, 
        z = clustered_users$advanced_pv, 
        type = "scatter3d", 
        mode = "markers", 
        color=factor(clustered_users$fit.cluster)
)

# write results to file
write.csv(clustered_users, "clustered-users.csv", row.names=T)
```

## Results

Result visualized in `plotly` package:

![](/assets/5_clustering.gif)

## Results - clustered users

In addition to chart you get `.csv` file with userId \(fingerprint\) and created label \(number of segment\). You can use the results uploading it to your marketing systems. Example results:

```
> clustered_users

               Beginner     Intermediate     Advanced  fit.cluster
266876                 9                 45            4           1
965265                 9                 51            7           1
...
981924                19                 10            8           2
732529                19                 16            1           2
...
377795                2                   7            38           3
918083                2                   8            28           3
```

## Source code

Complete code for this example in GitHub repository:

[github.com\/michalbrys\/R-Google-Analytics\/blob\/master\/5\_users\_segmentation.R](https://github.com/michalbrys/R-Google-Analytics/blob/master/5_users_segmentation.R)

