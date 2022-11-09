---
tags: orga
todo: ==**Check Inbox**==
date: 3000
---
>[!example]  ## Inbox
> ```dataview
> table 
> (date(today) - file.cday).day as "Age"
> FROM #in
> SORT date desc
> ```