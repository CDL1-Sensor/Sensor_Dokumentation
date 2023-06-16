# Bewertungsbogen Praxismoule
Dieses Readme befasst sich mit dem Bewertungsbogen von der Sensor Based Activity Recoginition Challenge.   
Wir gehen hier in die Allgemeine Lernziele ein, beschreiben und verlinken dabei die einzelnen Punkte.

# Domänverständnis

## Zentrale Aspekte und Konzepte der Domäne recherchieren, verstehen und erklären können 

Das Domänverständnis wird durch das Repository [Sensor_Domaenverstaendnis](https://github.com/CDL1-Sensor/Sensor_Domaenverstaendnis) abgedeckt.   
Im Readme sind alle wichtigen Aspekte und Konzepte der Domaene vorhanden und werden mit einer jeweiligen kurzen Beschreibung gegebenenfalls Beispielen erklaert.    
Dieses Repo dient ebenfalls als Lern Transfer vom Team untereinander und auch als Vorbereitung der Challenge Verteidigung. 

## Vorhandene Daten und Resultate entsprechend der Domäne korrekt interpretieren, einordnen, erläutern und visualisieren und gegebenenfalls erweitern können

Die Ueberpruefung der Qualitaet der selbst gesammelten Daten ist im Repository [Sensor_Data-Wrangling-und-EDA](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA) vorhanden.   
Einige der gesammelten Sensorddaten werden in diesem [Folder](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/tree/master/plots/raw-vs-trimmed) visualisiert.   
Dort sind die Unterschiede von den Sensoredaten von Person zu Person deutlich zu erkennen. Auch den Einfluss des Trimmen ist dort zu sehen. 
Weiter wurden die Sensoraten durch Aggregationen erweitert, diese ist im [data-wrangling](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/blob/master/data-wrangling.ipynb) Notebook zu finden. 

## Fragestellung (und Zielsetzung) verstehen, klären & konkretisieren und gegebenenfalls anpassen/weiterentwickeln können

Die Zielsetzung sowie Aufgabenstellung wurden in der [Planung und Konzeption](https://github.com/CDL1-Sensor/Sensor_Planung_Konzeption) konkretisiert.   
Im Verlaufe der Challenge wurden zusätzlich weitere Metriken als nur die Accuracy in der Auswertung mit berücksichtigt. 
(Siehe [ML-](https://github.com/CDL1-Sensor/Sensor-Klassifikation-ohne-Deep-Learning/blob/main/ML-Modelle.ipynb) und [DL-Notebook](https://github.com/CDL1-Sensor/Sensor_Klassifikation-mit-Deep-Learning/blob/main/DL-Modelle.ipynb))

# Lösungsstrategien, Vorgehensweisen und Methoden

## Analyse der Fragestellung, Anforderungen und Risiken

Ein grosses ist Risiko ist die Qualität der Daten. Damit das Risiko von schlechten Daten vermindert wird, wurde Gruppenübergreifend gemeinsam an einer [Policy](https://github.com/CDL1-Sensor/Sensor_Dokumentation/tree/master/Datenerhebung) der Datenerhebung erarbeitet. Im Verlaufe der Challenge wurde jedoch festgestellt, dass die Qualität der Smartphones ausschlaggebend für die Qualität der Daten sind. Entsprechend mussten wir uns mit den typischen Data Science herausforderung herumschlagen, dazu gehörte die Verarbeitung der Daten, die Modellierung und Nachvollziehbarkeit der Modelle sowie die Auswertung und das Fazit. Da wir ein vierer-Team sind ist auch hier die klare Struktur des Repository wichtig, damit es zu wenigen Merge-Konflikten kommt. Um dieses zu umgehen wurde vor der Challenge eine GitHub Organization erstellt mit den jeweiligen Repositoies. Dies ermöglichte uns einen Reibungslose Zusammenarbeit.

## Methodenkenntnisse und Transfer aus den Modulen

### Kombiniert verschiedenste Methoden und Vorgehensweisen adäquat und effizient und/oder entwickelt neue Methoden oder Vorgehensweisen, die eine innovative Lösung der Aufgabe ermöglichen 


### Vergleicht und beurteilt mehrere Methoden auf Basis von statistischen Tests (mehrfache Ausführung, Crossvalidation, Fehlerabschätzung der Experimente, zB t-test). Kann diese Tests richtig interpretieren 


### Kennt Methoden, die nachgewiesenermassen State of the Art sind, und wendet mindestens eine Methode zur Lösung der Aufgaben an 


## Vorgehensweise und Experimentdesign (Ausführung eines Data Science Projektes)

### Vergleicht Ergebnisse mit einem unterschiedlichen Baseline Ansatz 

### Implementiert verschiedene Vergleichsalorithmen zur Lösung und Optimierung der Fragestellung

### Vergleicht und beurteilt mehrere Modellansätze (Baseline, SotA1, SotA2) auf der Basis von statistischen Tests (mehrfache Ausführung, Crossvalidation, Fehlerabschätzung der Experimente, zB t-test). Kann diese Tests richtig interpretieren. 

## Code Struktur und Testing

### Entwirft und implementiert die Pipeline, den Code und die Modellierung mit Fokus auf Effizienz 

### Gebraucht objektorientierte und/oder funktionale Programmierung um den Code noch wartbarer, einfach zu erweitern und effizienter zu machen 

# Dokumentation, Wissenschaftlichkeit, Reproduzierbarkeit

## Dokumentation der Arbeit

### Dokumentiert in einer Art und Weise, dass die Lösung von fachlichen bzw nicht-fachlichen Personen installiert und genutzt werden kann 


## Analyse und Evaluation von Strategie, Methoden und Resultaten

### Diskutiert Evaluationsmethoden und daraus erhaltene Resultate 

### Analysiert Ergebnisse umfassend und kritisch, zieht klare Schlussfolgerungen und macht Vorschläge zur Weiterführung/ Vertiefung 


## Code Dokumentation und Versionierung

### Dokumentiert den Code vollständig, adäquat und adressatengerecht und verwendet eine Lösung zur automatischen Erstellung einer Dokumentation 

### Dokumentiert den Bezug zwischen Code (Architektur) und/oder Software-Architektur

### Verwendet Pull-requests, Code Reviews, Kommentare und andere fortgeschrittene Techniken des Git Repositories 

## Reproduzierbarkeit und Deployment

### Verwendet ein Framework für Reproduzierbarkeit der Experimente (zB mlflow oder Experiment Beaconing, Weight&Biases) 

### Beschreibt und strukturiert das Projekt so, dass alle Experimente, insbesondere Machine Learning Experimente, reproduzierbar sind und die erarbeitete Lösung einfach zu benutzen ist (zB Dockerized) 

### Trennt Artefakte und Modelle nach Development, Test, Production 

# Allgemeines Projektmanagement

## Methodenwahl, Dokumentation und Evaluation

### Wählt eine passende Projektmanagement- Methode oder kombiniert Teile verschiedener Methoden und kann diese Kombination kritisch erklären und begründen 

### Hinterfragt kontinuierlich das Vorgehen, passt es situativ an und setzt permanent Massnahmen zur Verbesserung der gemeinsamen Arbeit um. 


## Planung des Projektes

### Kennt und nutzt unterschiedliche Methoden zur Aufwandschätzung von Aufgaben 


## Durchführung des Projektes

### Nutzt das Planungstool professionell und umfassend 

### Nutzt verschiedene Reports zur Überprüfung des Projektes (zB Burndown, Velocity) 

### Geht konstruktiv mit unstrukturierten Situationen um und passt die Planung bei neuen Erkenntnissen an 

### Reagiert sofort bei eingetroffenen Risiken, passt gegebenenfalls das Projektziel an und kommuniziert dies den Interessenvertretern 


## Wissenserwerb als Projektaufgabe

### Organisiert im Team explizit Formate für den Wissenstransfer 

### Bewahrt und organisiert das für die Lösung der Aufgabe notwendige Wissen ein, in einer systematischen und nachhaltigen Form (zB mit Beschreibung des Inhaltes, Relevanz für die Aufgabe), sodass sich neue Personen rasch und gut in die Aufgabe einarbeiten könnten. 


# Kommunikation und Zusammenarbeit

## Kommunikation und Zusammenarbeit mit Beteiligten (Kunden, Owner, Coaches, etc) für einzelne Studierende oder Teams

### Kommuniziert höflich, klar, mit Fachkompetenz und lösungsorientiert 

### bereitet Meetings so vor, dass diese effizient, zielorientiert und in einem angenehmen Klima stattfinden können 

### Bespricht beziehungsweise erarbeitet mögliche Lösungen und Vorgehensweisen mit den Beteiligten und passt gegebenenfalls die Lösungsstrategie und Methoden an 


## Präsentationen (mündlich und schriftlich) von Zwischen- resultaten und Endresultaten

### Die Präsentation ist prägnant und abwechslungsreich und wird souverän vorgetragen 


## Kommunikation im Team

### Ermöglicht effektive Meetings durch überzeugende Kommunikation von alternativen Lösungen und Vorgehensweisen 

### Bindet alle Teammitglieder ein und bewirkt, dass sich jede/r beteiligen kann 

### Sorgt dafür, dass Erkenntnisse aus der Teamarbeit dokumentiert werden und für andere/für spätere Projekte zur Verfügung stehen 


## Zusammenarbeit im Team

### Verbessert die Arbeiten anderer Teammitglieder durch konstruktives und lösungsorientiertes Feedback, bindet selbst solches in seine Arbeiten ein und berücksichtigt andere Meinungen. Stellt die Erfüllung der Aufgabe über den eigenen Beitrag 

### Erkennt aufkommende Konflikte, spricht sie an und trägt zu ihrer Lösung bei, so dass die Zusammenarbeit effizient und konstruktiv weitergeführt werden kann 


# Kreativität und kritisches Denken

## Kreativität und innovatives Denken

### Nimmt das Problem auf verschiedene Weise wahr oder nähert sich ihm auf unterschiedliche Weise. Listet viele Ideen und Antworten auf 

### Berücksichtigt ungewöhnliche Ansätze oder hat eigene, neue Ideen oder kombiniert Ideen auf neue Weise, die über die Vorgaben der Aufgabe hinausgehen 

### Entwickelt nach einer Auswahl von Alternativen einen logischen, konsistenten Plan zur Lösung des Problems 


## Kritisches Denken und Handeln

### Legt die Fragestellung oder dafür erhaltene oder recherchierte Informatione in eigenen Worten klar dar und beschreibt sie umfassend, liefert die dazu nötigen Informationen und erstellt eine eigene kritische Analyse 

### Hinterfragt die Standpunkte der Experten, eigene und fremde Annahmen kritisch. Zieht andere Perspektiven oder Hypothesen mit ein. 

### Bewertet die eigenen Ergebnisse und Schlussfolgerungen im Kontext der Fragestellung und relevanter Informationen logisch, kritisch und umfassend 

# Professionalität und Reflexionsfähigkeit

## Zuverlässigkeit, Eigeninitiative und Motivation

### hält Besprechungs- und Abgabetermine ein und hält sich zuverlässig an Vereinbarungen im Team oder mit anderen Beteiligten 

### erfüllt die zugeteilten Aufgaben proaktiv, leistet einen wesentlichen eigenen Beitrag und nutzt die Gelegenheit, Neues zu lernen und anzuwenden 

### Protokolliert die eigene Arbeit in einer Art und Weise, dass er daraus Schlüsse für zukünftige Arbeiten ziehen kann (siehe Reflexionsfähigkeit) 

### erarbeitet ein Thema gründlich und interessiert

## Lernbereitschaft

### Erkennt eigene Wissenslücken und füllt sie selbstständig und proaktiv 

### Erkennt Probleme rechtzeitig, kann sie klar formulieren und sucht zu deren Lösung passende Hilfe (Team, Studierende, Coach, Kunde, FE) 



## Reflexionsfähigkeit

### Reflektiert die geleistete Arbeit, den eigenen Beitrag, neu Gelerntes und mögliche Verbesserungen 

### geht konstruktiv mit eigenen Fehlern um: anerkennt eigene Fehler und sieht sie als Lerngelegenheit 

### Arbeitet transparent, so dass er/sie Feedback erhalten und in einen Austausch treten kann

### Erkennt den Nutzen von Feedback, kann Feedback systematisch abholen und in die Arbeit integrieren 

# Aufgabenspezifische Lernziele				

## Datensammlung

### Erstellt ein Konzept zur Datensammlung 

### Führt die Datensammlung so aus, dass die Datenqualität stimmt

### Prüft die Qualität der Daten

### Speichert die Daten in geeigneter Form und kann die Wahl begründen

## Modellierung

### Es werden verschiede Modellideen getestet, mindestens aber:, Ein Modell zur Klassifizierung ohne Deep Learning, Ein Modell zur Klassifizierung mit Deep Learning

### Vergleich und Beurteilung der verschiedenen Modellansätze werden festgehalten

### Auch negative Ergebnisse werden dokumentiert


## Präsentation

### Es werden folgende Punkte in der Präsentation besprochen: Aufgabenstellung und Vorgehen, Modelle, Modellevaluation, Lessons learnt

### Die Präsentation ist nachvollziehbar und hat einen roten Faden. (Story-telling)

