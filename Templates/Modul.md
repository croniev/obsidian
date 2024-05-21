---
tags: Modul
date: <% tp.file.creation_date("YYYY-MM-DD") %>
semester: M1
alias: "!<% tp.file.cursor(1) %>"
---
<% tp.file.cursor(0) %>
## <font color="teal">Knowledge</font>
```dataview
table sitzung
FROM !"Templates" AND #<% tp.file.cursor(1) %>
SORT sitzung desc
```

## <font color="green">Texte</font>
```query
path:Master_TechPhil/<% tp.file.cursor(3) %>/Reads
```