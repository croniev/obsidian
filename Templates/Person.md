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
date: <% tp.file.creation_date("YYYY-MM-DD") %>
---
Thema:: <% tp.file.cursor(1) %><% tp.file.cursor(0) %>
Aliases:: <% tp.file.cursor(2) %>

 
## Leben
<span class='ob-timelines' data-date='@birthday-00-00-00' data-end='@deathday-00-00-00' data-type='range' data-class='person1'>
Geburtsdatum:: @birthday

Tod:: @deathday
</span><%* setTimeout(() => {app.commands.executeCommandById("obsidian-utils:fill-birthday")}, 7500) %>

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