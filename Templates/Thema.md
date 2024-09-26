<%*
// Prompt Title
let title = tp.file.title
if (title.startsWith("Untitled")) {
	title = await tp.system.prompt("Title");
	await tp.file.rename(`${title}`);
} 
-%>
---
tags: thema
date: <% tp.file.creation_date("YYYY-MM-DD") %>
aliases: 
---
<%* tR += `
>[!example]-  <font color="cc2299">Systeme</font>
> \`\`\`dataview
> table
> FROM #system
> FLATTEN thema
> WHERE thema = [[${title}]]
> SORT date asc
> \`\`\`
`-%>

<% tp.file.cursor(0) %>

## <font color="teal">Knowledge</font>
<%* tR += `
\`\`\`dataview
table Thema,date
FROM !#Reads and !#Person and !#system and !"Templates"
WHERE contains(join(thema), "${title}")
SORT file.name asc
\`\`\`
`-%>

## <font color="#ee1144">Reads</font>
<%* tR += `
\`\`\`dataview
table Autor, Erscheinungsdatum as Date, Thema
FROM #Reads and !"Templates"
WHERE contains(join(thema), "${title}")
SORT Erscheinungsdatum desc
\`\`\`
`-%>

## <font color="#ffee33">People</font>
<%* tR += `
\`\`\`dataview
table Geburtsdatum, Tod, Thema
FROM #Person
WHERE contains(join(thema), "${title}")
SORT Geburtsdatum desc
\`\`\`
`-%>