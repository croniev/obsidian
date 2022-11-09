---
tags: Periode, Gesch, timeline, test
date: <% tp.file.creation_date("YYYY-MM-DD") %>
aliases: 
---
Davor:: 
Danach:: 
<span class='ob-timelines' data-date='xxxx-01-01-00' data-end='xxxx-01-01-00' data-type='background' data-class='periode'></span>

---
## <font color="teal">Konzepte, Ereignisse</font>
```dataview
table start, ende
FROM !#Person
FLATTEN periode
WHERE periode = [[<% tp.file.title %>]]
SORT start desc
```

## <font color="red">Personen</font>
```dataview
table geburtsdatum, tod
FROM #Person
FLATTEN periode
WHERE periode = [[<% tp.file.title %>]]
SORT geburtsdatum desc
```