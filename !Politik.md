---
tags: Knowledge
---
### [[!Philosophie]]
### [[!Soziologie]]
> [!info]+ <font color="cc55cc" size=4px>Themen</font>
> ```dataview
> table 
> FROM !"Templates"
> WHERE startswith(file.name, "(Pol)")
>SORT file.name asc
> ```
## <font color="Teal">Knowledge</font>
```dataview
table Thema, date
FROM !#Person AND !#Reads AND !#lev
WHERE contains(join(thema), "!Politik") OR contains(join(thema), "(Pol)")
SORT date asc
```
## <font color="#339955">Reads</font>
```dataview
table Autor, Erscheinungsdatum as Datum, Ende, seiten
FROM #Reads
WHERE contains(join(thema), "!Politik") OR contains(join(thema), "(Pol)")
SORT Erscheinungsdatum asc
```
### Files
```query
path:Reads/Pol
```
## <font color="#ff3500">Personen</font>
```dataview
table Geburtsdatum, Aliases
FROM #Person 
WHERE contains(join(thema), "!Politik") OR contains(join(thema), "(Pol)")
SORT geburtsdatum asc
```
