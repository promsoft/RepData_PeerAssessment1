# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
data <- read.table(unz("activity.zip", "activity.csv"), header = TRUE, sep = ",", 
    stringsAsFactors = F, colClasses = c("integer", "Date", "integer"))
```



## What is mean total number of steps taken per day?

```r
steps.per.day <- tapply(data$steps, data$date, sum, na.rm = T)
hist(steps.per.day, main = "total number of steps taken each day", xlab = "steps per day")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2.png) 

There is the mean total number of steps taken per day:  9354.23.
There is the median total number of steps taken per day: 10395.


## What is the average daily activity pattern?

```r
steps.per.interval <- aggregate(data$steps, by = list(data$interval), FUN = mean, 
    na.rm = T)
plot(steps.per.interval$x, type = "l")
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 

```r

max.interval <- which.max(steps.per.interval$x)
```


The 5-minute interval, on average across all the days in the dataset,
contains the maximum number of steps: 104-th, this one:  835.

Devise a strategy for filling in all of the missing values in the dataset. The
strategy does not need to be sophisticated. For example, you could use
the mean/median for that day, or the mean for that 5-minute interval, etc.
## Imputing missing values

```r
df2 <- data

for (row. in names(steps.per.day)) {
    
}
```


There were 2304 NA values.
## Are there differences in activity patterns between weekdays and weekends?


