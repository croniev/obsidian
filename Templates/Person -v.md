---
tags: Person, timeline, test
date: <% tp.file.creation_date("YYYY-MM-DD") %>
Aliases: "<% tp.file.cursor(2) %>"
---
Thema:: [[(<% tp.file.cursor(0) %>]]

 
## Leben<%* 
title = await tp.system.prompt("Name");
try{await tp.file.rename(`${title}`);}
catch(e){await tp.file.rename('Duplicate!')}%>
<span class='ob-timelines' data-date='<% tp.file.cursor(3) %>-01-01-00' data-end='<% tp.file.cursor(4) %>-01-01-00' data-type='range' data-class='person1'>
Geburtsdatum:: <% tp.file.cursor(3) %>

Tod:: <% tp.file.cursor(4) %>
</span>

## Themen
<% tp.file.cursor(5) %>
<%* tR += `
\`\`\`dataview
table date
Flatten Person
Where Person = [[${title}]]
SORT file.name asc
\`\`\`
`-%>

## Werke
<%* tR += `
\`\`\`dataview
table Erscheinungsdatum
FROM #Reads
Flatten Autor
Where Autor = [[${title}]]
SORT erscheinungsdatum asc
\`\`\`
`-%>