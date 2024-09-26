---
tags: personal
aliases: ["!TB"]
---
>[!summary]- `types`: gemacht, goodfeel, badfeel, neutral, traum, zsf
> 
> ```dataview
> calendar file.ctime
> FROM #TB and !"Templates"
> where type != "gedanke"
> And type != "einsicht"
> ```

>[!example]- List
> 
> ```dataview
> table type, date, time
> FROM #TB and !"Templates"
> where type != "gedanke"
> And type != "einsicht"
> SORT date desc, time desc
> ```

[[Lustige Geschichten]]

---

>[!summary]- `type`: gedanke
> 
> ```dataview
> calendar date
> FROM #TB and !"Templates"
> where type = "gedanke"
> ```

>[!example]- List
> ```dataview
> table date, time 
> FROM #TB and !"Templates"
> flatten type
> where type = "gedanke" 
> SORT date desc, time desc
> ```

---

>[!summary]- `type`: einsicht
> 
> ```dataview
> calendar date
> FROM #TB and !"Templates"
> where type = "einsicht"
> ```

>[!example]- List
> ```dataview
> table date, System 
> FROM #TB and !"Templates"
> flatten type
> where type = "einsicht" 
> SORT date desc, time desc
> ```