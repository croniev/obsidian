---
tags: orga
todo: ==**Check Inbox**==
date: 3000
---
>[!example]  ## Inbox
> ```dataview
> table 
> (date(today) - file.cday).day + " d" as "Age"
> FROM #in
> SORT (date(today) - file.cday).day asc
> ```