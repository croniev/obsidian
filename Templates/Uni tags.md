<%* /* Used when there is already a file for the subject of the lecture, and I merely want to add the existing file into the database of the Module*/-%>
#Modul
Vlsg:: <% tp.file.cursor(0) %>
Datum:: <% tp.date.now("YYYY-MM-DD") %>
- [[Folien / Video links <% tp.file.cursor(2) %>]]