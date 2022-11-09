---
tags: sonstiges
---
>[!info]+ Perioden
> ```dataview
> table Start, Ende
> FROM #Periode AND !"Templates" 
>SORT start desc
> ```
```timeline-vis
tags=test
tags=Gesch
startDate= -2000
endDate= 3000,10,10
divHeight=300
minDate= -2000
maxDate= 3500
```
## <font color="teal">Konzepte</font>
```dataview
table Periode, Start, Ende
FROM #Gesch and !"Templates" and !#Periode
SORT start desc
```
