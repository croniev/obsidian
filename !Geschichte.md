---
tags: Knowledge
---

>[!info]+ Perioden
> ```dataview
> table Start, Ende
> FROM !"Templates" 
> WHERE startswith(file.name, "(Zeit)")
>SORT start desc
> ```
```timeline-vis
tags=Gesch
startDate= -800
endDate= 2200,10,10
divHeight=300
minDate= -2000
maxDate= 3500
```
[[!Personen]]
## <font color="teal">Knowledge</font>
```dataview
table Zeit, Start, Ende
FROM  !"Templates" and !#Zeit and !#Person
WHERE zeit
SORT start desc
```