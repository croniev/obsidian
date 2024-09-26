---
tags: Knowledge
---
Hier sollen Themen aus den Wissenschaften die weder
[[!CogSci]]
[[!Informatik]]
[[!Soziologie]]
[[!Psychologie]]
[[!Politik]] zuzuordnen sind.
Nicht zu verwechseln mit [[(P) Wissenschaftsphilosophie]] in der Philosophie.

---
> [!info]+ <font color="cc55cc" size=4px>Themen</font>
> ```dataview
> table 
> FROM !"Templates"
> WHERE startswith(file.name, "(W)")
>SORT file.name asc
> ```
## <font color="teal">Knowledge</font>
```dataview
table thema, date
FROM !"Templates"
WHERE contains(join(thema), "(W)") OR contains(join(thema), "!Wissenschaft")
SORT thema asc
```

## <font color="#339955">Reads</font>
```query
path:Reads/Wiss
```