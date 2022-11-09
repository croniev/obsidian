---
tags: sonstiges
---

> [!info]+ Themenbereiche
> ```dataview
> table 
> FROM #themenbereich AND !"Templates"  and #Phil
>SORT file.name asc
> ```

## <font color="Teal">Konzepte</font>
```dataview
table thema, date
FROM !#Person and !#Reads AND #Phil AND !#lev and !#themenbereich
SORT thema
```

## <font color="yellow">Autoren</font>
```dataview
table Geburtsdatum, Tod, Aliases
FROM #Person 
flatten gebiet
where gebiet = [[!Philosophie]]
SORT geburtsdatum asc
```

## <font color="green">Reads</font>
```dataview
table Erscheinungsdatum as Datum, Autor, thema, seiten
FROM #Reads and !"Templates"
FLATTEN gebiet
where gebiet = [[!Philosophie]]
SORT Autor, erscheinungsdatum asc
```