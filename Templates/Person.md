---
tags: Person, timeline, test
date: <% tp.file.creation_date("YYYY-MM-DD") %>
---
Thema:: <% tp.file.cursor(0) %>
Aliases:: <% tp.file.cursor(2) %>

 
## Leben<%* 
title = await tp.system.prompt("Name");
let tSplits = title.split(", ")
let url = `https://api.wikimedia.org/core/v1/wikipedia/en/search/page?q=${tSplits.join("")}&limit=1`;
var response = await tp.user.curl({url: url});
let data = JSON.parse(response)
let page = data.pages[0]
if (tSplits.length == 1){title += `, ${page.title.split(" ")[0]}`}
try{await tp.file.rename(`${title}`);}
catch(e){await tp.file.rename('Duplicate!')}
let excerptMatch = page.excerpt.match(/[0-9]{3,4}/g)%>
<span class='ob-timelines' data-date='<%excerptMatch[0]%>-00-00-00' data-end='<%excerptMatch[1] ? excerptMatch[1] : "2100"%>-00-00-00' data-type='range' data-class='person1'>
Geburtsdatum:: <%excerptMatch[0]%>

Tod:: <%excerptMatch[1] ? excerptMatch[1] : "2100"%>
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