---
tags: themenbereich, Phil
date: <% tp.file.creation_date("YYYY-MM-DD") %>
aliases: 
---
>[!example]-  ### <font color="cc2299">Systeme</font>
> ```dataview
> table
> FROM #system
> FLATTEN thema
> WHERE thema = [[<% tp.file.title %>]]
> SORT date asc
> ```
## <font color="teal">Konzepte</font>
```dataview
table tags,date
FROM !#Reads and !#Person and !#system
FLATTEN thema
WHERE thema = [[<% tp.file.title %>]]
SORT date asc
```

## <font color="red">Reads</font>
```dataview
table tags,date
FROM #Reads and !"Templates"
FLATTEN thema
WHERE thema = [[<% tp.file.title %>]]
SORT date asc
```

## <font color="yellow">People</font>
```dataview
table tags,date
FROM #Person
FLATTEN thema
WHERE thema = [[<% tp.file.title %>]]
SORT date asc
```