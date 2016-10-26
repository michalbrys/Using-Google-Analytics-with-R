# Exploratory data analysis

Download your data and save it in data frame `gadata`

```r
# Get the Sessions by Month in 2014
query.list <- Init(start.date = "2014-01-01",
                   end.date = "2014-12-31",
                   dimensions = "ga:date",
                   metrics = "ga:sessions",
                   table.id = "ga:00000000")
```

Let's do some basics operations

## Min

Check what is minimum number of sessions in 2014?

```r
min(gadata$sessions)
```

```r
[1] 0
```

### Number of days with 0 sessions recorded

It seems like error in tracking and no data for some day. When it was? Display days with 0 sessions.

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

How many days with 0 sessions? Use function `nrow()` to count rows with this condition.

```r
nrow(subset(gadata, ga.data$sessions == 0))
```

```r
[1] 9
```

So it was 9 days with 0 sessions.

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

So the highest traffic is 204 sessions in 1 day. When it was?

```r
subset(gadata, gadata$sessions == 204)
```

```r
       date sessions
59 20140228      204
```

You can reach this data in one function, replacing value with `max()`. It is shorter but harder to read:

```r
subset(gadata, gadata$sessions == max(gadata$sessions))
```

```r
       date sessions
59 20140228      204
```

## Mean

What is mean number of sessions per day? To calculate this, use `mean()` function.

```r
mean(gadata$sessions)
```

```r
[1] 27.6
```

So average number of sessions per day is equal 27.6.

## Standard deviation

You can check diversity of number sessions per day. Use `sd()` function.

```r
sd(gadata$sessions)
```

```r
[1] 22.12984
```

So average number of sessions is equal 27.6 +\/- 22.12984. This dataset has big diversity and in your case is better not to trust only average value.

## Median

If dataset has high standard deviation its better to calculate median \(the most popular value in dataset\).

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

Complete code for this example in GitHub repository:

[github.com\/michalbrys\/R-Google-Analytics\/blob\/master\/2\_eda.R](https://github.com/michalbrys/R-Google-Analytics/blob/master/2_eda.R)

