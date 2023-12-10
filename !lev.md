---
tags: personal
---
#### Siehe auch: [[!Tagebuch]], [[!Projekte]]

>[!example]+  <font color="cc55cc" size=4px>Systeme</font>
> ```dataview
> table
> FROM #system AND !"Templates"
> Sort file.name asc
> ```
## <font color="ee88cc">Cherry-Picked</font>
Specially important files

## Diskurse
Das sind Fragen/Themen wo noch Diskussionsbedarf besteht
```dataview
table System, Solved, date
FROM #Diskurs and !"Templates"
SORT Solved asc, date desc
```