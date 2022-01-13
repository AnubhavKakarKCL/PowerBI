# DAX

## Calculated Columns

### IsDateRange

Used to denote date range


```
IsDateRange = AND(DATEDIFF(MAX(Project[Date End]),'Calendar'[Date],DAY)<1,
DATEDIFF(MIN(Project[Date Start]),'Calendar'[Date],DAY)>-1)
```

# Useful Links

## Videos

[Design Thought Process](https://youtu.be/dhHL0Uo3Wgs) - Miguel Myers talks about Power BI report design from requirements to release

[15 UI Principles](https://youtu.be/-tdkUYrzrio) - Marco Russo discusses 15 rules to follow when designing good Power BI user interfaces

## Blogs

[Understanding Star Schema](https://docs.microsoft.com/en-us/power-bi/guidance/star-schema)

[SUMMARIZE vs SUMMARIZECOLUMNS](https://www.sqlbi.com/articles/introducing-summarizecolumns/)
