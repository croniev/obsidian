---
tags: Knowledge
---
##### <font color="purple">Frei</font>
```dataview
table Autor, Erscheinungsdatum as Datum, Ende, seiten
FROM #Reads AND !"Templates"
Where contains(join(thema), "Frei")
SORT Ende desc
```

##### <font color="orange">Notes</font>
```dataview
table Autor, Erscheinungsdatum as Datum, seiten, thema
FROM #Reads AND !"Templates"
Where !contains(join(thema), "Frei")
SORT Erscheinungsdatum desc
```
##### Phil
```query
path:Reads/Phil/
```
##### Pol
```query
path:Reads/Pol/
```
##### Wiss
```query
path:Reads/Wiss/
```
##### Tech
```query
path:Reads/Tech/
```
##### Free
```query
path:Reads/Free/
```
##### ZSFs
```query
path:Reads/ZSFs/
```