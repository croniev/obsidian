---
tags: Knowledge
---
> [!info]+ <font color="cc55cc" size=4px>Themen</font>
> ```dataview
> table 
> FROM !"Templates"
> WHERE startswith(file.name, "(P)")
>SORT file.name asc
> ```

## <font color="Teal">Knowledge</font>
```dataview
table Thema, date
FROM !#Person and !#Reads AND !#lev
WHERE contains(join(thema), "(P)") OR contains(join(thema), "!Philosophie") 
SORT thema
```

## <font color="#ffdf00">Autoren</font>
```dataview
table Geburtsdatum, Tod, Thema, Aliases
FROM #Person
WHERE contains(join(thema), "(P)") OR contains(join(thema), "!Philosophie")
SORT geburtsdatum desc
```

## <font color="#339955">Reads</font>
```dataview
table Erscheinungsdatum as Jahr, Autor, Thema, seiten
FROM #Reads and !"Templates"
WHERE contains(join(thema), "(P)") OR contains(join(thema), "!Philosophie")
SORT erscheinungsdatum desc, autor
```
### Files
```query
path:Reads/Phil
```