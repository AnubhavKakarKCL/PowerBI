# PowerBI

## DAX

### IsDateRange

```
IsDateRange = AND(DATEDIFF(MAX(Project[Date Start]),'Calendar'[Date],DAY)<1,
DATEDIFF(MIN(Project[Date Start]),'Calendar'[Date],DAY)>-1)
```

## Power Query
