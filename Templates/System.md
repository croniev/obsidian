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

###### Quellen

#
---
<%* tR += `
>[!example]- Old
>\`\`\`dataview
> TABLE date
> FROM #Oldies
> WHERE contains(join(system), "${title}")
> SORT date desc
> \`\`\`
`-%>

<% tp.file.cursor(2) %>

## Verwandt:
<% tp.file.cursor(1) %>

## <font color="teal">Begriffe</font>
<%* tR += `
\`\`\`dataview
TABLE date
FROM #lev
WHERE contains(join(system), "${title}")
SORT file.name asc
\`\`\`
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