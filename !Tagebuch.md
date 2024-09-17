---
tags: personal
aliases: ["!TB"]
---
`types`: gemacht, goodfeel, badfeel, neutral, traum, zsf

```dataview
calendar file.ctime
FROM #TB and !"Templates"
where type != "gedanke"
And type != "einsicht"
```

>[!example]- List
> 
> ```dataview
> table type, date, time
> FROM #TB and !"Templates"
> where type != "gedanke"
> And type != "einsicht"
> SORT date desc, time desc
> ```


`types`: gedanke, einsicht

```dataview
calendar file.ctime
FROM #TB and !"Templates"
where type = "gedanke"
or type = "einsicht"
```

>[!example]- List
> ```dataview
> table type, date, time 
> FROM #TB and !"Templates"
> flatten type
> where type = "gedanke" 
> Or type = "einsicht"
> SORT date desc, time desc
> ```