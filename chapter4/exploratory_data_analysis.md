# Exploratory data analysis

Download your data and save it in a data frame called `gadata`

```r
# Get the Sessions by Month in 2014
query.list <- Init(start.date = "2014-01-01",
                   end.date = "2014-12-31",
                   dimensions = "ga:date",
                   metrics = "ga:sessions",
                   table.id = "ga:00000000")
```

Let's do some basic operations on the data.

## Min

What is the minimum number of sessions in 2014?

```r
min(gadata$sessions)
```

```r
[1] 0
```

### Number of days with 0 sessions recorded

It seems like there was an error in tracking and there is no data for some days. When was it? Display the days with 0 sessions.

```r
subset(gadata, ga.data$sessions == 0)
```

```r
        date sessions
7   20140107        0
8   20140108        0
129 20140509        0
130 20140510        0
131 20140511        0
132 20140512        0
133 20140513        0
134 20140514        0
135 20140515        0
```

How many days were there with 0 sessions? Use function `nrow()` to count rows with this condition.

```r
nrow(subset(gadata, ga.data$sessions == 0))
```

```r
[1] 9
```

There was 9 days with 0 sessions.

```r
summary(gadata)
```

## Max

When was the biggest traffic on your website? Use `max()` function.

```r
> max(gadata$sessions)
```

```r
[1] 204
```

The highest traffic is 204 sessions in 1 day. When was it?

```r
subset(gadata, gadata$sessions == 204)
```

```r
       date sessions
59 20140228      204
```

You can reach these results in just one step, replacing the value with `max()`. This way, it is shorter but harder to read:

```r
subset(gadata, gadata$sessions == max(gadata$sessions))
```

```r
       date sessions
59 20140228      204
```

## Mean

What is the mean number of sessions per day? To calculate this, use the `mean()` function.

```r
mean(gadata$sessions)
```

```r
[1] 27.6
```

The average number of sessions per day is equal to 27.6.

## Standard deviation

You can check the diversity of the number of sessions per day. Use the `sd()` function.

```r
sd(gadata$sessions)
```

```r
[1] 22.12984
```

The average number of sessions is equal 27.6 +/- 22.12984. This dataset has big diversity and in that case it is better not to trust only the average value.

## Median

If a dataset has high standard deviation it is better to calculate the median \(the most popular value in a dataset\).

```r
median(gadata$sessions)
```

```r
[1] 21
```

The most popular number of sessions id 21 sessions per day.

## Summary

If you want, you can get all of this statistics in one function: `summary`.

```r
summary(gadata)
```

```r
     date              sessions    
 Length:365         Min.   :  0.0  
 Class :character   1st Qu.: 12.0  
 Mode  :character   Median : 21.0  
                    Mean   : 27.6  
                    3rd Qu.: 40.0  
                    Max.   :204.0  
```

As a result you will get basic statistics for numeric variables and description for character variables.

## Source code

The complete source code of the examples showed above is in my GitHub repository:

[github.com/michalbrys/R-Google-Analytics/blob/master/2_eda.R](https://github.com/michalbrys/R-Google-Analytics/blob/master/2_eda.R)

