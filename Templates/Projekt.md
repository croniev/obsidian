---
date: <% tp.file.creation_date("YYYY-MM-DD") %>
---
Thema:: [[(<% tp.file.cursor(1) %>]]
System:: [[(S)<% tp.file.cursor(2) %>]]
Aliases:: <% tp.file.cursor(3) %>
date-started:: 
date-finished:: 
<%*
// Add Tag
tag = await tp.system.suggester((item) => item.split("/")[1], ["#Projekt/Tech", "#Projekt/Essay", "#Projekt/Materiell", "#Projekt/Musik", "#Projekt/Digital", "#Projekt/Schriftlich"])
tR += tag
// Link to kanban board
const proj_file = tag.replace("#Projekt/", "''");
tR += ` | [[${proj_file}]]\n`

// Prompt Title
let title = tp.file.title
if (title.startsWith("Untitled")) {
	title = await tp.system.prompt("Title");
	await tp.file.rename(`${title}`);
} 

// Add template
if (tag == "#Projekt/Essay" || tag == "#Projekt/Schriftlich"){
tR += `\n
**[[Fließtext_${title}]]**

---

## Kernaussage/Ziel
\<\% tp.file.cursor(4) \%\>

## Argumentationsgang

## Quellen
`;
}
else{
tR += `\n
---
## Idee
\<\% tp.file.cursor(4) \%\>
### Inspiration

## Prozess
- [ ] `;
}

// Add card to Kanban board
const pfile = tp.file.find_tfile(proj_file);
var content = await app.vault.read(pfile);
var content_list = content.split("\n")
content_list.splice(8, 0, `- [ ] [[${title}]]`)
await app.vault.modify(pfile, content_list.join("\n"))
-%>