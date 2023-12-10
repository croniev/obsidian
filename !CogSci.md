---
tags: Knowledge
---
---
Eine Wissenschaft die sich mit der mathematischen Modellierung von Kognitionsprozessen beschäftigt. 

---
> [!info]+ <font color="cc55cc" size=4px>Themen</font>
> ```dataview
> table 
> FROM !"Templates"
> WHERE startswith(file.name, "(CS)")
>SORT file.name asc
> ```
## <font color="Teal">Knowledge</font>
```dataview
table Thema, date
FROM !#Person AND !#Reads AND !#lev
WHERE contains(join(thema), "!CogSci") OR contains(join(thema), "(CS)")
SORT date asc
```
## <font color="#339955">Reads</font>
```dataview
table erscheinungsdatum as Jahr, Autor, Thema, seiten
FROM #Reads and !"Templates"
WHERE contains(join(thema), "!CogSci") OR contains(join(thema), "(CS)")
SORT thema, erscheinungsdatum desc
```
## <font color="#ff3500">Personen</font>
```dataview
table Geburtsdatum, Tod, Thema, Aliases
FROM #Person
WHERE contains(join(thema), "(CS)") OR contains(join(thema), "!CogSci")
SORT geburtsdatum desc
```
## <font color="yellow">Module</font>
- [[!CogSciIII]]
- [[!Topics - Multisensory perception and action]]
- [[!ExPra]]
- [[!Statmod]]