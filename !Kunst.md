---
tags: Knowledge
---
Sachen die mir gefallen
## <font color="teal">Sachen</font>
```dataview
table thema, date
FROM !"Templates" and !#Person
WHERE contains(join(thema), "!Kunst")
SORT date desc
```

## <font color="yellow">Personen</font>
```dataview
table Geburtsdatum, Aliases
FROM #Person 
WHERE contains(join(thema), "!Kunst")
SORT geburtsdatum asc
```

## <font color="33cc66">Notizen</font>
