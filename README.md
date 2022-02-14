# DAX

## Calculated Columns

### IsDateRange

Used to denote date range


```
IsDateRange = AND(DATEDIFF(MAX(Project[Date End]),'Calendar'[Date],DAY)<1,
DATEDIFF(MIN(Project[Date Start]),'Calendar'[Date],DAY)>-1)
```

### YoY

```
YoY = SWITCH (TRUE,
    ISINSCOPE ( Fact_Incident[Open_DateHour] ),
        CALCULATE (
            [# Received],
            DATEADD ('Calendar'[Date], -1, YEAR ),
            ALL('Calendar'),
            ALL('DatePeriod')
        ),
    ISINSCOPE ( 'Calendar'[Date] ),
        CALCULATE (
            [# Received],
            FILTER(ALL('Calendar'),'Calendar'[DWY] = MAX ( 'Calendar'[DWY] ) - 1),
            ALL('DatePeriod')
        ),
    ISINSCOPE ( 'Calendar'[Week Month Year]),
        CALCULATE (
            [# Received],
            FILTER(ALL('Calendar'),'Calendar'[WY] = MAX ( 'Calendar'[WY] ) - 1),
            ALL('DatePeriod')
        ),
        CALCULATE ( [# Received],
            ALL('Calendar'),
            ALL('DatePeriod'),
            DATEADD ( 'Calendar'[Date], -1, YEAR ) ))
```

# Useful Links

## Videos

[Design Thought Process](https://youtu.be/dhHL0Uo3Wgs) - Miguel Myers talks about Power BI report design from requirements to release

[15 UI Principles](https://youtu.be/-tdkUYrzrio) - Marco Russo discusses 15 rules to follow when designing good Power BI user interfaces

[Data Mesh part 1](https://www.starburst.io/resources/datanova-2021/?submissionGuid=f8acec13-88e4-4772-b76e-f83714e0eaed&wchannelid=d4oyeh306b&wmediaid=1z50qr8fh6)

[Data Mesh part 2](https://www.starburst.io/resources/datanova-2021/?submissionGuid=f8acec13-88e4-4772-b76e-f83714e0eaed&wchannelid=d4oyeh306b&wmediaid=3sb7nbjc7f)

## Blogs

[Understanding Star Schema](https://docs.microsoft.com/en-us/power-bi/guidance/star-schema)

[SUMMARIZE vs SUMMARIZECOLUMNS](https://www.sqlbi.com/articles/introducing-summarizecolumns/)

[Power BI Cleaner](https://www.thebiccountant.com/2021/08/23/power-bi-cleaner-gen2-now-covers-analysis-services-models-as-well/)

## Github

[Power BI Themes](https://github.com/deldersveld/PowerBI-ThemeTemplates)

## DAX

[Return 0 instead of BLANKS](https://www.sqlbi.com/articles/how-to-return-0-instead-of-blank-in-dax/)
[Calculation groups to selectively replace measures](https://www.sqlbi.com/articles/using-calculation-groups-to-selectively-replace-measures-in-dax-expressions/)
