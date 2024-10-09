---
tags: TB
date: <% tp.file.creation_date("YYYY-MM-DD") %>
time: <% tp.file.creation_date("HH:mm") %>
---
Type:: einsicht

System:: [[(S) <% tp.file.cursor(0) %>]]
<%*
let title = tp.file.title
var filename = "/Tagebuch/einsicht - "
if (!title.startsWith("Untitled")){
filename += title
}
await tp.file.move(filename);%>
<% tp.file.cursor(1) %>