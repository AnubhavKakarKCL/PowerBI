# PowerBI

## DAX

### Calculated Columns

#### IsDateRange

Used to denote date range


```
IsDateRange = AND(DATEDIFF(MAX(Project[Date End]),'Calendar'[Date],DAY)<1,
DATEDIFF(MIN(Project[Date Start]),'Calendar'[Date],DAY)>-1)
```

## Useful Links

[Design Thought Process](https://youtu.be/dhHL0Uo3Wgs)
[15 UI Principles](https://youtu.be/-tdkUYrzrio)
