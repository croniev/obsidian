---
tags: TB
date: <% tp.file.creation_date("YYYY-MM-DD") %>
time: <% tp.file.creation_date("HH:mm") %>
---
Type:: <%*const type = await tp.system.suggester((item) => item, ["goodfeel", "badfeel", "neutral", "traum", "gemacht", "zsf", "gedanke", "einsicht"], true); %><% type %>

<%* if (type == "einsicht"){ %>System:: [[(S)<% tp.file.cursor(0) %>]]

<%* }
var filename = "/Tagebuch/" + tp.date.now("DD.MM.YY") + " - "
if (type == "gedanke"){
filename += "Gedankentagebuch"; %>#### Setting
<% tp.file.cursor(1) %>
### Big Thonk

### These
<%* } else { %><% tp.file.cursor(1) %><%* } 
await tp.file.move(filename);%>