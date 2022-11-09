---
tags: Person, timeline, test
date: <% tp.file.creation_date("YYYY-MM-DD") %>
---
Gebiet:: 
Thema:: 
Aliases::

 
## Leben
<span class='ob-timelines' data-date='xxxx-01-01-00' data-end='xxxx-01-01-00' data-type='range' data-class='person1'></span>

## Themen

## Werke
```dataview
table Erscheinungsdatum
FROM #Reads
Where Autor=[[<% tp.file.title %>]]
SORT erscheinungsdatum asc
```