<%*
// Prompt Title
let title = tp.file.title
if (title.startsWith("Untitled")) {
	title = await tp.system.prompt("Title");
	await tp.file.rename(`${title}`);
} 
-%>
---
tags: system, lev
date: <% tp.file.creation_date("YYYY-MM-DD") %>
aliases: []
---
Thema:: <% tp.file.cursor(0) %>

---
## <%* tR += title.split('(S) ')[1] -%>

<% tp.file.cursor(1) %>

## Verwandt:
<% tp.file.cursor(2) %>

##
<% tp.file.cursor(3) %>

## <font color="teal">Begriffe</font>
<%* tR += `
\`\`\`dataview
TABLE date
FROM #lev and !#Oldies
WHERE contains(join(system), "${title}")
SORT file.name asc
\`\`\`
`-%>

<%* tR += `
>[!example]- Old
>\`\`\`dataview
> TABLE date
> FROM #Oldies
> WHERE contains(join(system), "${title}")
> SORT date desc
> \`\`\`
`-%>

## <font color="bb44dd">Einsichten</font>
<%* tR += `
\`\`\`dataview
TABLE date
FROM #TB
WHERE contains(join(type), "einsicht")
WHERE contains(join(system), "${title}")
SORT date desc
\`\`\`
`-%>

## <font color="44d044">Backlinks</font>

```dataview
TABLE date
FROM !#lev and [[]]
SORT date desc
```