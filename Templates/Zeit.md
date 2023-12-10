<%*
// Prompt Title
let title = tp.file.title
if (title.startsWith("Untitled")) {
	title = await tp.system.prompt("Title");
	await tp.file.rename(`${title}`);
} 
-%>
---
tags: zeit, timeline, test, Gesch
date: <% tp.file.creation_date("YYYY-MM-DD") %>
aliases: 
---
Davor:: <% tp.file.cursor(0) %>
Danach:: <% tp.file.cursor(1) %>
<span class='ob-timelines' data-date='<% tp.file.cursor(2) %>-01-01-00' data-end='<% tp.file.cursor(3) %>-01-01-00' data-type='background' data-class='periode'></span>

---
## <font color="teal">Knowledge, Ereignisse</font>
<%* tR += `
\`\`\`dataview
table Start, Ende
FROM !#Person
WHERE contains(join(zeit), "${title}")
SORT start desc
\`\`\`
`-%>

## <font color="#ee1144">Personen</font>
<%* tR += `
\`\`\`dataview
table Geburtsdatum, Tod
FROM #Person
WHERE contains(join(zeit), "${title}")
SORT geburtsdatum desc
\`\`\`
`-%>