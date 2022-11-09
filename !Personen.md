---
tags: sonstiges
aliases: ["!People"]
---
```timeline-vis
tags=test
tags=Person
startDate= -1000
endDate= 3000,10,10
divHeight=300
minDate= -2000
maxDate= 3500
```
```dataview
table geburtsdatum, tod, Gebiet
FROM #Person and !"Templates"
SORT geburtsdatum desc
```