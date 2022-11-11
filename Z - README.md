---
tags: orga
---
# Dieses System
## Features
- Jede Datei hat **Metadaten**. Diese werden benutzt um in den Übersichtsdateien (mit dataview) zu filtern und die entsprechenden Dateien + Informationen aufzulisten.
	- Entweder im Dateikopf (zwischen `---`) 
	- oder inline (mit zwei Doppelpunkten)
	- Die meisten Dateien kriegen das `date` Attribut. Das hilft einfach der zeitlichen Nachverfolgung
	- Es können auch mehrere Werte für ein Attirbut übergeben werden
		- z.B. mit `att: [a,b]`
		- oder mehrmals inline machen
		- oder bei inline mehrere links in einer Zeile

- **Aliases**: Wenn als metadata z.B. `aliases: Darwin` übergeben wird, kann die Datei auch mit der Suche nach "Darwin" gefunden werden, egal was der eigentlich Name ist.
- Konzept-Dateien besitzen ein `vorlesung: x` Attribut, zur besseren zeitlichen Zuordnung.
	- Bei Text-basierten Veranstaltungen gibt es zusätzlich ein `Text:: xxx` Attribut, welches auf den Haupttext verweist. 
- **Timelines**-Plugin
	- Benötigt `timeline` tag in der Datei die Elemente enthalten soll
		- Und `test` falls die timeline eine horizontale sein soll
	- Im Template [[timeline]] ist der `<span>`-Block der benötigt wird. 
	- Bitte die `xxxx` zu validen Daten ändern. 
	- class kann aktuell eine der folgenden sein: `background, person1, geschix, geschio, geschi1-geschi4`
	- Es können mit einem command dann die Daten extrahiert werden und als metadata `Geburtsdatum:: ,Tod:: ` bzw. `Start:: ,Ende:: ` eingefügt werden (damit man es nicht doppelt eingeben muss).
		- Extrahiertes Datum: `xxxx`oder`xxxx-xx-xx`, je nachdem ob die letzten zwei Zahlen `00` sind oder nicht
		- Plug-In `croniev/obsidian-timelines-parse-dates`; Gesamten `span` block auswählen,  parse-dates command ausführen.
- **Blöcke** (siehe [[Z - Syntax]]): V.A. bei mathematischeren Dateien nützlich, aber kann überall verwendet werden zur übersichtlichen differenzierung von Definitionen, Zielen, Erklärungen, Beispielen, Problemen, etc...
### Kommentieren von fremdem Wissen
Ich will ja trennen können was die Quelle sagt und was ich dazu sage. Daher sind eigene Kommentare mit diesen Mitteln gekennzeichnet:
- Ausführungen/Erklärungen, Quellen, oder längere direkte Kommetare mit Fußnote[^1]
- Direkte Kommentare hintendran als code: `so wie das hier`
- Direkte Kritik oder Frage in rot: <font color="red">so wie hier</font>
- Stellenbezogene Frage als block: mit `>[!question]`
## Struktur
- [[README]] ist die **landing page**. Diese Datei ist die Übersicht über das **Wissen-Sammeln** System. Für das **Wissen-Generieren** System siehe [[Z - README2]].

- In [[Z - Syntax]] ist eine Cheat sheet für Markdown und Obsidian Text- und Code-Möglichkeiten.
- In `/Templates` befinden sich die **Vorlagen**.
- Der "**Universität**"-Ordner ist im Obsidian Ordner, d.h. alle PDFs sind in Obsidian enthalten und können direkt verlinkt werden.
- Es gibt eine **[[!TODO]]** Datei. Dort werden andere Dateien aufgelistet, die ein `todo: xxx` in den metadaten haben.
- In **[[!Inbox]]** landen Dateien mit dem tag `in`, diese sollen nochmal angeschaut und überarbeitet oder richtig eingeordnet werden.
- **Übersichtsdateien** fangen mit `!` an. [[!A]] ist die Übersicht der Übersichten.
	- Übersichten über alle Themenbereiche und Perioden (`(T)` und `(P)` Dateien) sind in [[!Philosophie]] bzw. [[!Geschichte]]

## Uni-Sachen
- Ich habe eine Datei für jedes Modul, mit der Info, von welchem Semester es ist.
	- Dort werden die gelesenen Texte (`/Uni/Modul/Reading`) und die wichtigen Konzepte aufgelistet. Ebenso eine Sammlung der Aufgaben (`/Uni/Modul/Aufgaben`).
- Für jedes Modul gibt es ein eigenens Template, damit die Konzepte leicht erstellt und eingeordnet werden können.

## Anderes Wissen
- Unter [[!A#Sonstiges]] befinden sich noch Übersichtsdateien für Wissen das nicht direkt zu Modulen gehört.

- Dazu gehört z.B. selbst angeeignetes wissen über [[!Informatik]], Übersicht über [[!Personen]], [[!Geschichte]] und [[!Philosophie]].
- Dort werden die Konzepte mit den entsprechenden Tags gesammelt, die weitere Struktur, wie z.B. Personen, Texte, Links, Themenbereiche, usw. kann pro Bereich nach Bedarf angepasst werden.
- Uni und Anderes Wissen schließt sich nicht aus. Es kann auch sowhol der Modul-tag als auch der Wissen-tag gegeben werden, dann taucht die Datei in beiden Übersichten auf
	- Dann halt darauf achten dass die metadata-Anforderungen beider Übersichten erfüllt werden.

Ein paar angepasste Strukturen werden hier erläutert:
### [[!Personen]]
#### Übersicht
- Horizontale Zeitleiste mit allen Personen (die die richtigen tags und span block haben)
- Auflistung der Personen sortiert nach Geburtsdatum, mit Tod und Gebiet
#### Konkrete Dateien
- tags: `Person` (`timeline` und `test` sind für Timelines nötig)
- metadata:
	- Gebiet:: z.B. [[!Philosophie]] oder[[!Psychologie]]
	- Thema:: z.B. [[Natural Language Processing]] oder [[(T) Psychoanalyse]]
	- Geburtsdatum und Tod (im span block)
- `<span>`-Element für Timelines
- Unter Leben steht Inline Geburtsdatum und Tod
- Unter Themen kann auf andere Dateien verlinkt werden, aber auch kurze Überblicke oder Erläuterungen derer Positionen gemacht werden. 
- Unter Werke stehen alle [[Reads]] die als Autor die Datei der Person gelinkt haben.
### [[!Reads]]
#### Überblick
- Reads: Texte, Bücher, Kapitel, Artikel, Essays, etc.
- Auflistung aller Notes die Reads zusammenfassen/kommentieren
- Auflistung der PDF-Dateien im `/Reads` Ordner
#### Konkrete Dateien
- tags: `Reads`
- metadata:
	- Gebiet:: siehe oben
	- Thema:: siehe oben
	- Erscheinungsdatum:: ist klar
	- Autor:: Link zu der [[Person]] die das Buch geschrieben hat
	- seiten: Länge des Textes
- Ein Link zur PDF-Datei bzw. URL
- Kurze und Knappe Zusammenfassung der Thematik und Thesen
- In Inhalt ein Mitschrieb mit Zitaten, erklärungen, usw. 
- In Gedanken Kritik oder allgemeinere Fragen zum Text/der Position.
### [[!Geschichte]]
#### Überblick
- Sammlung der [[Periode|Perioden]]
	- Haben immer (P) im Titel (einfacher zu finden)
	- Jede hat Start und Ende Attribut
	- Es werden die relevanten Konzepte/Ereignisse und Personen gesammelt 
		- Personen müssen dafür das Periode-Attribut erhalten
	- Zusätzlich gibt es Verweise auf die vorherige und die nächste Periode (bei bedarf kann es mehrere geben)
	- (Zeitstrahl funktioniert hier leider nicht)
- Zeitstrahl mit Perioden (background) und Konzepten/Ereignissen
	- Soll eine Person auch im Geschi-Zeitstrahl auftreten, dann dieser Person den `Gesch` tag geben
- Sammlung der Konzepte sortiert nach Start
#### Konkrete Dateien
- tags: `Gesch` (`timeline` und `test` sind für Timelines nötig)
- metadata:
	- Periode:: Link zu Periode; z.B. [[(P) Mittelalter]]
	- Start:: ist klar
	- Ende:: ist klar
- `<span>`-Element für Timelines
	- data-class:
		- `geschix`: Wichtiges Ereigniss
		- `geschi1-4`: Andere Ereignisse. Unterschiedliche Farbe pro Zahl damit etwas mehr differenziert werden kann (z.B. `geschi1` für Deutschland nutzen, `geschi2` für Europa und `geschi3` für Ostasien)
		- `geschio`: Eher unwichtige Ereignisse
### [[!Philosophie]]
#### Überblick
- Sammlung der [[Themenbereich|Themenbereiche]]
	- Haben immer (T) im Titel (einfacher zu finden)
	- Diese sind ähnlich wie Periode bei Geschichte
	- Systeme, Konzepte, Reads und Personen werden gesammelt (die das passende Thema Attribut haben)
	- Für Systeme siehe [[Z - README2]]
- Sammlung der Konzepte, Autoren und Reads
	- Wobei Autoren und Reads als Gebiet auf [[!Philosophie]] verlinken
#### Konkrete Dateien
- tags: `Phil`
- metadata: 
	- Thema:: wie gehabt, etwas mit (T)
---
# Add-Ons & Plug-Ins
- README-Datei lesen
- Settings einmal durchgehen
- Bei bedarf modifizieren (open-source)
- Funktionieren meistens auch auf Handy

---
###### (Syncthing)
- Kein Obsidian Plugin sondern ein Sync-Tool
- Kann gesamte Ordner zw. Geräten syncen
- Nicht cloud sondern abgleich
- empfehlung: `workspace*` in `.stignore` hinzufügen

---
###### [Dataview](https://github.com/blacksmithgu/obsidian-dataview)
- Tags und Metadata 
	- inline oder im Kopf der Note
- Notes sammeln und sortieren

---
###### [Templater](https://github.com/SilentVoid13/Templater)
- Einfügen von vorgefertigten Texten
- Mächtiger als normale Templates
- Neue Datei mit Template
- Kommandos
	- Datum einsetzen
	- Ordner verschieben
- Beispiele unter /Templates

---
###### [Snippets](https://github.com/ArianaKhit/text-snippets-obsidian)
- Abkürzungen für Kommandos
- höchst personalisierbar 
- $L^AT_EX$
- blocks
- html

---
###### [Footnotes](https://github.com/akaalias/obsidian-footnotes)
- Standard Funktionalität --> Praktischer

---
###### [Timelines](https://github.com/Darakah/obsidian-timelines)
- Für Zeitliche Sachen und Sequenzen praktisch
- Personalisierbar mit der `obsidian.css` datei in `/.obsidian/snippets`
- Beispiele: [[!Geschichte]], [[!Personen]]

---
###### [Kanban](https://github.com/mgmeyers/obsidian-kanban)
- Für organisation praktisch
- Übersichtlich

---
[^1]: Wie hier