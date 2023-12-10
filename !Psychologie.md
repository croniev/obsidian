---
tags: Knowledge
---

---
> [!info]+ <font color="cc55cc" size=4px>Themen</font>
> ```dataview
> table 
> FROM !"Templates"
> WHERE startswith(file.name, "(Psy)")
>SORT file.name asc
> ```
## <font color="teal">Knowledge</font>
```dataview
table Thema, date
FROM !#Person AND !#Reads AND !#lev
WHERE contains(join(thema), "!Psychologie") OR contains(join(thema), "(Psy)")
SORT date asc
```

## <font color="#339955">Reads</font>
```dataview
table Erscheinungsdatum as Jahr, Autor, Thema, seiten
FROM #Reads
WHERE contains(join(thema), "!Psychologie") OR contains(join(thema), "(Psy)")
SORT Erscheinungsdatum asc
```
## <font color="#ff3500">Personen</font>
```dataview
table Geburtsdatum, Tod, Thema, Aliases
FROM #Person
WHERE contains(join(thema), "(Psy)") OR contains(join(thema), "!Psychologie")
SORT geburtsdatum desc
```