---
tags: Knowledge
---
### [[!Philosophie]]
### [[!Politik]]
> [!info]+ <font color="cc55cc" size=4px>Themen</font>
> ```dataview
> table 
> FROM !"Templates"
> WHERE startswith(file.name, "(Soz)")
>SORT file.name asc
> ```
## <font color="Teal">Knowledge</font>
```dataview
table Thema, date
FROM #Soz
SORT date desc
```
## <font color="#339955">Reads</font>
```dataview
table Erscheinungsdatum as Jahr, Autor, Thema, seiten
FROM #Reads
WHERE contains(join(thema), "!Soziologie") OR contains(join(thema), "(Soz)")
SORT Erscheinungsdatum desc
```
## <font color="#ff3500">Personen</font>
```dataview
table Geburtsdatum, Tod, Thema, Aliases
FROM #Person 
WHERE contains(join(thema), "!Soziologie") OR contains(join(thema), "(Soz)")
SORT geburtsdatum asc
```

