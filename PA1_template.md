# Reproducible Research: Peer Assessment 1


```r
library(knitr)
opts_chunk$set(echo = TRUE)
```

## Loading and preprocessing the data

First we unzip the activity file and load the data.frame activity.csv.


```r
if (!file.exists("./activity.csv")) {
        unzip("./activity.zip")
}
df <- read.csv("./activity.csv")
```

Transform the date column into the date format, then group the data frame by
date.


```r
df$date <- as.Date(df$date, format = "%Y-%m-%d")
daily_df <- aggregate(steps ~ date, data = df, sum)
hist(daily_df$steps)
```

![](./PA1_template_files/figure-html/unnamed-chunk-2-1.png) 
## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
