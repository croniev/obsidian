---
tags: Knowledge
aliases: ["!People"]
---
```timeline-vis
tags=Person
startDate= -1000
endDate= 3000,10,10
divHeight=300
minDate= -2000
maxDate= 3500
```
[[!Geschichte]]
```dataview
table geburtsdatum, tod, thema
FROM #Person and !"Templates"
SORT geburtsdatum desc
```