# PowerBI

## DAX

### IsDateRange

Used to denote date range


```
IsDateRange = AND(DATEDIFF(MAX(Project[Date End]),'Calendar'[Date],DAY)<1,
DATEDIFF(MIN(Project[Date Start]),'Calendar'[Date],DAY)>-1)
```

## Power Query
