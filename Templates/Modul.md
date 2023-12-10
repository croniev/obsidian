---
tags: Modul
semester: 6
---

## <font color="teal">Knowledge</font>
```dataview
table vorlesung
FROM !"Templates" AND #<% tp.file.cursor(0) %>
SORT vorlesung desc
```

## <font color="green">Texte</font>
```query
path:Universität/<% tp.file.cursor(1) %>/Reading
```

## Aufgaben
```query
path:Universität/<% tp.file.cursor(2) %>/Aufgaben
```