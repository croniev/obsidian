---
tags: TB
date: <% tp.file.creation_date("YYYY-MM-DD") %>
time: <% tp.file.creation_date("HH:mm") %>
---
Type:: <%*
const type = await tp.system.suggester((item) => item, ["goodfeel", "badfeel", "neutral", "traum", "gemacht", "zsf", "gedanke", "einsicht"], true);
var content = "";
var filename = "/Tagebuch/" + tp.date.now("DD.MM.YY") + " - "
if (type == "gedanke"){
filename += "Gedankentagebuch";
content += "\n#### Setting\n\n### Big Thonk\n\n### These\n"
}
if (type == "einsicht"){
content += "\nSystem:: [[(S)\<\% tp.file.cursor(0) \%\>]]\n"
}
await tp.file.move(filename);
tR += type + content
-%>


<% tp.file.cursor(1) %>