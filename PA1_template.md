

## What is mean total number of steps taken per day?

![plot of chunk TotalStepsNoNA](figure/TotalStepsNoNA-1.png) 

The mean total is 10766.2.  The median total is 10765.

---

## What is the average daily activity pattern?

![plot of chunk DailyActivity](figure/DailyActivity-1.png) 

Interval 835 on average across all the days in the dataset, contains the maximum number of steps.

---

## Inputing missing values

The total number of rows with 'NA's is 2304.

'NA's are present in the steps column only.  The strategy for replacing 'NA's is to use the mean value for that interval across all days as follows:

```r
allData$steps <- ifelse( is.na(allData$steps), 
                         intervalMeans$steps[ match(allData$interval, intervalMeans$interval) ], 
                         allData$steps )
```

![plot of chunk TotalStepsWithNA](figure/TotalStepsWithNA-1.png) 

The mean total is 10766.2.  The median total is 10766.2.

As the NA replacement algorithm substituted the interval mean, the mean total has not changed but the median total has.

---

## Are there differences in activity patterns between weekdays and weekends?

![plot of chunk WeeklyActivity](figure/WeeklyActivity-1.png) 




