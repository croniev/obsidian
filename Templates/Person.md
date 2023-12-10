<%*
// Prompt Title
let title = tp.file.title
if (title.startsWith("Untitled")) {
	title = await tp.system.prompt("Name");
	await tp.file.rename(`${title}`);
} 
-%>
---
tags: Person, timeline, test
date: 2023-12-08
---
Thema:: <% tp.file.cursor(0) %>
Aliases:: <% tp.file.cursor(1) %>

 
## Leben
<span class='ob-timelines' data-date='<% tp.file.cursor(2) %>-01-01-00' data-end='<% tp.file.cursor(3) %>-01-01-00' data-type='range' data-class='person1'></span>

## Themen
<% tp.file.cursor(4) %>
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