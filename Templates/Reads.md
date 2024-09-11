<%* const tfile = await tp.system.suggester((item) => item.basename + '.' + item.extension, app.vault.getFiles().filter((file) => file.extension == "pdf"))
const splits = tfile.basename.split('_')
const isSplit = splits.length >= 3
const pdfjs = await tp.obsidian.loadPdfJs()
const pdfDoc = await pdfjs.getDocument(app.vault.getResourcePath(tfile)).promise 
let title = tp.file.title
if (title.startsWith("Untitled")) {
	try{await tp.file.rename(`'${isSplit ? splits.slice(2).join(" ") : splits[0]}'`);}
	catch(e){await tp.file.rename('Duplicate!')}
} %>---
tags: Reads
date: <% tp.file.creation_date("YYYY-MM-DD") %>
seiten: <% pdfDoc.numPages %>
aliases: 
---
Thema:: [[(<% tp.file.cursor(2) %>]]
Aliases:: 

---
***Erscheinungsdatum***:: <% isSplit ? splits[0] : "<% tp.file.cursor(0) %\>" %>
**Autor**:: <%* if(isSplit){
let finds = app.vault.getFiles().find((file) => file.basename.includes(`${splits[1]},`))
while (true){

}
try{%><% "[[" + app.vault.getFiles().find((file) => file.basename.includes(`${splits[1]},`) && this.app.metadataCache.getFileCache(file).fontmatter.tags.includes("Person")).basename + "]]" %><%*
} catch (e){ %>[[<% splits[1] %>]]<%*}
}else{%><% tp.file.cursor(1) %><%* } %>
Ende:: 

**[[<% tfile.basename + '.' + tfile.extension %>]]**

> [!Summary]+
> 

## Inhalt
<% tp.file.cursor(6) %>

## Gedanken
