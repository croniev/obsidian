---
tags: orga
---
# Obsidian
Das Ziel ist es, sowohl meine Notizen und den konsumierten Inhalt, als auch meine eigenen Gedanken didaktisch zu speichern und dynamisch miteinander zu verbinden.
Dabei unterscheide ich in Module ([[#Uni-Sachen]]) und persönliche ([[#Arschlachs]]) sachen.
## Orga 
### Mittel
- Jede Datei hat **Metadata** (mit den `---` ganz oben). Diese wird benutzt um in den Übersichtsdateien (mit dataview) zu filtern und die entsprechenden Dateien + Informationen aufzulisten.
- In `/Templates` befinden sich Vorlagen, welche mit Ctrl+T eingefügt werden können.
- Textsnippets sparen Zeit und nerven um Kästchen zu erstellen und text zu färben. (Habe Arturs ganze LaTeX snippets)
- In [[Z - Syntax]] ist eine Aufzählung von Markdown bzw. Obsidian-Formatierungsoptionen.
### Dateien
- Der "Universität"-Ordner ist im Obsidian Ordner, d.h. alle PDFs sind in Obsidian enthalten und können direkt verlinkt werden.
- Es gibt eine [[!TODO]] Datei. Dort werden auch Dateien aufgelistet, die ein `todo: xxx` in der Metadata haben.
- Übersichtsdateien fangen mit `!` an. [[!A]] ist die Übersicht der Übersichten.
	- Ausnahme sind die Themenbereiche für Philo, diese werden aber in [[!Philosophie]] aufgezählt.
- Konzept-Dateien besitzen ein `vorlesung: x` Attribut, zur besseren Zuordnung.
	- Bei Text-basierten Veranstaltungen gibt es zusätzlich ein `Text:: xxx` Attribut, welches auf den Haupttext verweist. 
		- Gibt es mehrere Texte zu einem Konzept, müssen diese als Anmerkung hinzugefügt werden

## Uni-Sachen
### Struktur
- Ich habe eine Datei für jedes Modul, mit der Info, von welchem Semester es ist.
	- Dort werden die gelesenen Texte (`/Uni/Modul/Reading`) und die wichtigen Konzepte aufgelistet. Ebenso eine Sammlung der Aufgaben (`/Uni/Modul/Aufgaben`).
- Für jedes Modul ein eigenens Template, damit die Konzepte Leicht eingeordnet werden können.

### Workflow
###### Modul 1

## Arschlachs
#### Personen
Können mittels dem Template [[Person]] hinzugefügt werden, sind mit einer Timeline dargestellt in [[!Personen]]. Nach dem eintragen von geburtsdatum und tod in das template (Jahre) den `span`-Eintrag auswählen und mit `Alt+P` das Date-Parsing kommando ausführen, welches Geburtsdatum und Tod als metadata-Text hinzufügt.
#### Philosophie
In [[!Philosophie]] ist eine Sammlung von Dingen die ich im Studium und privat gelernt habe. Hier sind Dinge anderer Autoren, "objektives" philosophisches Wissen, Bildung. 
- Dateien haben themen via dem `thema` attribut.  Damit gehören sie zu einem [[Themenbereich]].
	- Übersicht aller Themenbereiche ist in der Philo-Datei.
	- Systeme (siehe unten) gehören nicht direkt zu Themenbereichen, aber sind mit ihnen verwandt. Sie müssen manuell hinzugefügt werden. 
###### Soziologie und Politk
Haben ihre eigenen !-Dateien, aber verlinken auch auf Philo und auf den jeweiligen Philo-Themenbereich.
Manche Dateien werden dann eben eher Philosophisch sein und andere schon von der disziplin, daher die trennung. 
#### lev
`lev` ist die Bezeichnung für Philosophische (Politische, Soziologische, Private) überlegungen von mir selbst.
In [[!lev]] ist eine übersicht der [[System]]e, und zusätzlich eine Auswahl an Dingen die ich für wichtig halte, und Dilemmata die mich beschäftigen.
**Systeme** sind mein Weg, etwas Struktur in das Netzwerk meiner Philosophie zu bringen. Alles ist irgendwie miteinander verknüpft, aber es gibt doch spezifische Frames, Themen, etc. welche ich gewissermaßen abgrenzen möchte. Dazu sind Systeme da.
In einem System werden dann die Begriffe aufgelistet, die es aufspannen, die [[Problem]]e, welche die Motivation/den Leitfaden liefern, und [[Wegweiser]], welche andeuten in welche Richtungen weitergedacht werden kann. Diese Teile eines systems haben ein Attribut `system:` welches den Names des entsprechenden Sys. enthält.

- Bins: Wenn ich schnell etwas aufschreiben will was zu einem System gehört aber noch nicht organisiert ist, dann gebe ich der Datei bloß den #bin Tag und ein `system` Attribut. Bin-Dateien werden im System ganz oben gesammelt und können später durchgegangen werden.

Ebenso werden im System noch Kommentare auf Philo-Sachen, und Tagebuch-Einsichten gesammelt:
- Bei **Philo** sachen, zu denen ich Kritik oder eigene Gedanken habe, wird entweder 
	- eine **eigene Datei** erstellt, mit Vor- und Rückverlinkung, 
	- oder es werden die Punkte **Fußnotenmäßig** (Kommentarisch) ergänzt, und 
		- die Datei bekommt ein System-Attribut 
		- und den Tag #levK.
- Bei **Tagebuch** einträgen, welche sich um eine Einsicht drehen, das 
	- thema #einsicht 
	- und ein System-Attribut geben.

#### Tagebuch
- In [[!Tagebuch]] sind die Einträge gesammelt, welche unterschiedliche Typen haben können.
- Gedanken, welche nicht wirklich in die Typen passen, aber auch nicht in ein lev-System, können den Typ `gedanke` kriegen und landen in einer separaten sammlung.

#### Lesen
In [[!Reads]] sind unterschiedliche Bereiche mit Büchern und Texten die ich lese.
#### Projekte, Blog
- Bei [[!Projekte]] sind unterschiedliche Bereiche, zu denen ich dort Projekte und Inspirationen sammle.
- Aufgelistet sind die fertigen Projekte
- Es gibt dazu Kanban boards (fangen mit `?` an), jede Karte soll ein Projekt sein. 
	- Für Prosa" gibt es keine Kanban boards weil das eher FETTE Projekte sind, wo nur eins am Stück läuft.
- Andere Dateien wie Workflows, Philosophien, etc. können einfach darunter hinzugefügt werden.
- Templates dafür sind [[Essay]] und [[Projekt]]. Die vielen attribute sind an sich nur für Blogposts relevant.
- Fertige Projekte können im Board archiviert werden und mit dem "Fertig"-Tag ergänzt werden, dann werden sie in der Übersicht aufgezählt.
- Soll etwas auf dem Blog geteilt werden, dann muss der Tag `Blog` hinzugefügt werden. Bei [[!Blog]] werden dann die fertigen und die unfertigen Projekte aufgelistet.
- Für Information/Theorie zu der Kunst gibt es dann Themendateien, wie z.B. [[!Musik]].
#### Sonst
- **Buchhaltung**: in [[_transactions]] werden Ausgaben notiert. Mit dem `Croniev Bookkeeping`-Plugin werden die Ausgaben zusammengefasst und in [[_ledger]] tabellarisch dargestellt.
- **Recherche**: in [[-Recherche]] werden Punkte gesammelt, die ich nachfroschen möchte. Dies ist gedacht für Momente wie Frühstück oder warten oder so, wenn ich nichts besseres zu tun habe.
- **Wissen**: in [[-Knowledge]] werden Dateien gesammelt, wo ich praktisches wissen festhalte, welches wichtig ist und nochmal nötig sein könnte, ich aber safe vergessen würde.