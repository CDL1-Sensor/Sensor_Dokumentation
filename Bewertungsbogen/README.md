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
Im Verlaufe der Challenge wurden zusätzlich weitere Metriken als nur die Accuracy in der Auswertung mit berücksichtigt
(Siehe [ML-](https://github.com/CDL1-Sensor/Sensor-Klassifikation-ohne-Deep-Learning/blob/main/ML-Modelle.ipynb) und [DL-Notebook](https://github.com/CDL1-Sensor/Sensor_Klassifikation-mit-Deep-Learning/blob/main/DL-Modelle.ipynb)).

# Lösungsstrategien, Vorgehensweisen und Methoden

## Analyse der Fragestellung, Anforderungen und Risiken

Ein grosses ist Risiko ist die Qualität der Daten. Damit das Risiko von schlechten Daten vermindert wird, wurde Gruppenübergreifend gemeinsam an einer [Policy](https://github.com/CDL1-Sensor/Sensor_Dokumentation/tree/master/Datenerhebung) der Datenerhebung erarbeitet. Im Verlaufe der Challenge wurde jedoch festgestellt, dass die Qualität der Smartphones ausschlaggebend für die Qualität der Daten sind. Entsprechend mussten wir uns mit den typischen Data Science herausforderung herumschlagen, dazu gehörte die [Verarbeitung der Daten](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA), die Modellierung und Nachvollziehbarkeit der Modelle sowie die Auswertung und das Fazit. Da wir ein vierer-Team sind ist auch hier die klare Struktur des Repository wichtig, damit es zu wenigen Merge-Konflikten kommt. Um dieses zu umgehen wurde vor der Challenge eine [GitHub Organization](https://github.com/orgs/CDL1-Sensor/repositories) erstellt mit den jeweiligen Repositoies. Dies ermöglichte uns einen Reibungslose Zusammenarbeit.

## Methodenkenntnisse und Transfer aus den Modulen

Aus dem Wissen aus den Modulen Data Wrangling, Lineare und Logsitische Regression, Explorative Datenanalyse sowie Grundkompetenz Machine Learning konnten wir die verschiedensten Methoden aus diesen Modulen mit in die Challenge einfliessen lassen.   
Aus dem Modul Deep learning konnte zusätzlich der Umgang mit der MLOps Plattform Weights and Bias weiterentwickelt werden sowie mit dem Framework Tensorflow.  
Weiter wurde im Verlaufe der Challenge erkannt, dass die Fehlerabschätzung der Metriken bzw. der Split von Train und Test sehr relevant ist für die Metriken. Im ML Notebook wurden durch Weights and Bias die Hyperparamter Optimiert und anschliessend vom besten Model deren Fehlerabschätzung. 

## Vorgehensweise und Experimentdesign (Ausführung eines Data Science Projektes)

Die erstellten Modelle wurden jeweils mit einem Baseline Modell verglichen und anschliessend am Ende des Notebook auch visualisiert. Im ML Notebook wurden diverse Sklearn Klassizierungsalgorithmen genutzt und mit Weights and Bias integriert. Im DL Notebook wurden die Modelle mit Tensorflow erstellt und im Tensorboard visualisiert. 

## Code Struktur und Testing

Der Code ist jeweils im Notebook ersichtlich. Weiter wurden im Code zu den jeweiligen implementierten Funktionen eine kurze Beschreibung hinzugefügt. Auch im Markdown ist ersichtlich, warum wir welche Schritte machen. 
# Dokumentation, Wissenschaftlichkeit, Reproduzierbarkeit

## Dokumentation der Arbeit

Die Dokumentation der Arbeit wurde mit dem Challenge-Owner am Anfang abgesprochen, dass diese im [Markdown](https://github.com/CDL1-Sensor/Sensor_Dokumentation) zu den jeweiligen Repos gemacht werden. Weiter haben wir als Team ein Separates Repository erstellt, welches die [Dokumentation der Challenge](https://github.com/CDL1-Sensor/Sensor_Dokumentation) erleichtert. Vorzugsweise wurde in den Notebooks im Markdown jeweils dokumentiert. Somit haben wir die Mögichkeit, bei der Dokumentation auf die bestimmten Notebooks zu verweisen.

## Analyse und Evaluation von Strategie, Methoden und Resultaten

Die Hyperparameteroptimierung und Cross-Validation wurden jeweils ebenfalls mit ins Weights and Bias integriert. Dies ermoegltichte es uns die [Resultate](https://wandb.ai/fhnw-cdl1/projects) genauer zu betrachten und somit die besten Modelle auszuwaehlen. 

## Code Dokumentation und Versionierung

Der Code wir durch git vollständig versioniert und ist somit ersichtlich, wer was wann geändert hat. 
Das Arbeiten mit Branches wurde nur gemacht, wo es von nöten war. Sprich wenn mehrere Personen gleichzeitig an einem Repository gearbeitet haben. 
Ebenfalls wurden entsprechend dort wo nötig dann Pull Request mit Reviews gemacht, bevor diese ins Main gemerged wurden. Generell haben wir uns jedoch in den jeweiligen Wöchentlichen Sitzungen gegenseitig ausgetauscht, wie und wo der aktuelle Stand der Arbeit war. 

## Reproduzierbarkeit und Deployment

Die Reproduzierbarkeit ist durch [Weights and Bias](https://wandb.ai/fhnw-cdl1/projects), insbesondere bei den Machine Learning Experimente, gegeben. Sowohl der Randomstate für den Split, wie auch für das Modell wurden mit geloggt, um das Model zu reproduzieren. Auch das Deployment der App ist in den jeweiligen Repository ersichtlich.

# Allgemeines Projektmanagement

## Methodenwahl, Dokumentation und Evaluation

Als Team haben wir uns geeinigt eine abgespeckte Scrum Variante zu verwenden. Dabei als Zentraler Aspekt ist das Kanban-Board, welches eine einfache Handhabung der Aufgabenaufteilung uns ermöglicht. Wöchentliche Hybride Sitzungen im Teams wurden abgehalten, um den Fortschritt zu besprechen und die nächsten Schritte zu planen. Bei Problemen wurde diese direkt via im erstellten Whatsapp Chat kommuniziert. Wichtig dabei waren für uns das Scrum-Value Transparency und Openess, welches wir auch in der Challenge ausgelebt haben. 

## Planung des Projektes

Die Aufgaben wurden im [Taskboard](https://github.com/orgs/CDL1-Sensor/projects/1) zu kleineren Aufgaben heruntergebrochen, um den Aufwand von einzelnen in Grenzen zu halten. Damit man geauer weiss, was die anderen und man selbst zu tun hat, wurden Tickets jeweils in den Sitzungen den Teammitglieder zugewiesen und mit T-Shirt Label Size versehen, um den Aufwand besser abschätzen zu können. Weiter wurden die Tickets mit einem jeweiligen Label des bestimmten Repository versehen, um die Übersicht zu behalten.

## Durchführung des Projektes

Siehe [Kanban Board](https://github.com/orgs/CDL1-Sensor/projects/1).

## Wissenserwerb als Projektaufgabe

Damit ein Wissenserwerb unter den Teammitglieder gesichert ist, wurde einerseits das Repository [Domaenenverstaendniss](https://github.com/CDL1-Sensor/Sensor_Domaenverstaendnis) am Anfang des Projektes erstellt. Weiter haben wir uns im Verlaufe der Challenge uns drei mal vorort getroffen und uns den ganzen Tag der Challenge gewidmet sowie Fragn untereinander geklärt. Die Organisation ist dabei so Aufgebaut, dass man diese an eine weitere Gruppe weiter geben könnte, und diese durch eine kurze Einfürhung Wissen, wo sie ansetzen müssten. 

# Kommunikation und Zusammenarbeit

## Kommunikation und Zusammenarbeit mit Beteiligten (Kunden, Owner, Coaches, etc) für einzelne Studierende oder Teams

Die Kommunikation erfolgte via Teams mit dem Challenge-Owner. Es wurde immer im Vorfeld zuerst eine Nachricht geschrieben, dass man gerne eine Sitzung haben möchte, um Terminkolissionen mit anderen Teams zu vermeiden, bzw auch andere Teams und den Challenge-Owner zu informieren. Die Kommunikation mit dem Challenge-Owner fand immer höflich statt und Feedback von ihm wurde immer ernst genommen und versucht umzugesetzten. (Bsp. Beachten von Data Leakage, Fehlerabschätzung der Metriken etc...)

![image](https://github.com/CDL1-Sensor/Sensor_Dokumentation/assets/66916399/fa00bbc0-1f8a-479d-9aa8-88ac3f16dc67)


## Präsentationen (mündlich und schriftlich) von Zwischen- resultaten und Endresultaten

Zwischen Resultate wurden jeweils in den Sitzungen mit dem Challenge-Owner besprochen. Die Endresultate werden in der Verteidigung vorgestellt. Es wurde sichergestelt, dass der Challenge-Owner Zugriff auf die Organisation hat und sich somit zu jeder Zeit ein Bild vom Fortschritt machen konnte.

![image](https://github.com/CDL1-Sensor/Sensor_Dokumentation/assets/66916399/2de0637c-704c-462f-ba38-6a7ac20c5bd4)


## Kommunikation im Team

Die Kommunikation im Team erfolgte jeden Dienstag Hybrid von 1100 bis 1200, dabei wichtig war es uns, dass jeder zu Wort kommt und seine aktuellen Probleme, Sorgen den anderen Team Mitglieder mitteilen konnte. Somit konnte man alternative Lösungen und Ideen gemeinsam besprechen und umsetzen. 
Bei Kleinigkeiten wurde via Whatsapp kommuniziert, dazu gehörten, Terminabsagen, Krankheit, etc...

## Zusammenarbeit im Team

Die Zusammenarbeit im Team lief nicht immer rund, da andere Module im Studiengang unerwartet viel Zeit fressten. Jedoch haben wir uns immer gegenseitig unterstützt und versucht, dass jeder sein Teil zur Challenge beitragen konnte.
# Kreativität und kritisches Denken

## Kreativität und innovatives Denken

In Deep Learning wurden die verschiedenen Kreative Ideen jeweils in Form von einem Notebook dokumentiert. Ein Beispiel ist, das hinzufügen von Noise zu den Daten, um diese generalisierbarer auf neue Daten zu machen. Weiter wurden auch im Deep Learning Bereich diverse unterschiedliche [Experiemnte](https://github.com/CDL1-Sensor/Sensor_Klassifikation-mit-Deep-Learning/tree/main/DL-Experiments) gemacht. 
 
## Kritisches Denken und Handeln

Die ML und DL Modelle wurden jeweils am Ende des Notebooks dokumentiert. Code welches nicht funktionierte wurde ebenfalls dokumentiert und recherche betrieben warum diese so ist. Bsp. die Runtime von KNNClassifier zu lange war. Die fehlgeschalgenen Runs sind ebenfalls in [Weights and Bias](https://wandb.ai/fhnw-cdl1/projects) ersichtlich. 
# Professionalität und Reflexionsfähigkeit

## Zuverlässigkeit, Eigeninitiative und Motivation

Die Abgabetermine wurden mit dem Challenge-Owner immer eingehalten. Auch im Team wurden die mündlichen Vereinaberungen umgesetzt. 

![image](https://github.com/CDL1-Sensor/Sensor_Dokumentation/assets/66916399/66f89abe-ced5-4da3-a524-cde864268f66)


## Lernbereitschaft

Jedes Team Mitglied ist selbständig dafür Verantwortlich das Wissen aufzubauen. Um diese einfacher zu gestalten, existiert das [Domaenwissen Repository](https://github.com/CDL1-Sensor/Sensor_Domaenverstaendnis). 

## Reflexionsfähigkeit

Es gibt durchaus viel potential sich zu verbessern. Dabei gehört zum einen die Code Redundanz im ML-Notebook und DL-Notebook. Es wurde versucht das Feedback vom Challenge-Owner umzusetzen. Bsp die Fehlerabschätzung der Metriken wurde umgesetzt. 

# Aufgabenspezifische Lernziele				

## Datensammlung

### Erstellt ein Konzept zur Datensammlung 

Das Konzept ist [hier](https://github.com/CDL1-Sensor/Sensor_Dokumentation/tree/master/Datenerhebung) zu finden.

### Führt die Datensammlung so aus, dass die Datenqualität stimmt

Für die Datensammlung und die Qualität der Daten war jede beteiligte Person der Challenge selbst verantwortlich dafür. Es hat sich jedoch herausgestellt, dass die Datenqualität stark vom Smartphone abhängt (Apple vs. Andoid).   

### Prüft die Qualität der Daten

Die Datenqualität wird dabei im folgenden Repository genauer unter die Lupe genommen. [Data-EDA](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/blob/master/eda.ipynb)
### Speichert die Daten in geeigneter Form und kann die Wahl begründen

Die [Daten](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/blob/master/README.md) wurden in einem CSV-Format gespeichert und im Picoshare ebenfalls abgelegt. Im Nachinein wäre ein Parquet-Format besser gewesen, da dieses komprimiert ist und somit weniger Speicherplatz benötigt.

## Modellierung

### Es werden verschiede Modellideen getestet, mindestens aber:, Ein Modell zur Klassifizierung ohne Deep Learning, Ein Modell zur Klassifizierung mit Deep Learning

Es wurden verschiedene Modelle getestet. 

[Klassifierzung ohne Deep Learning](https://github.com/CDL1-Sensor/Sensor-Klassifikation-ohne-Deep-Learning/blob/main/ML-Modelle.ipynb)

[Klassifizierung mit Deep Learning](https://github.com/CDL1-Sensor/Sensor_Klassifikation-mit-Deep-Learning/blob/main/DL-Modelle.ipynb)

### Vergleich und Beurteilung der verschiedenen Modellansätze werden festgehalten

Der Vergleich von Modellen ist im jeweiligen Notebook ersichtlich. 

Der Vergleich von ML und DL modelle ist im [ReadMe](https://github.com/CDL1-Sensor/Sensor_Dokumentation/blob/master/README.md) unter dem Abschnitt "Vergleich Machine Learning und Deep Learning" ersichtlicht.

### Auch negative Ergebnisse werden dokumentiert

Negative Ergebenisse wurden im Notebook nicht entfernt. Siehe Im ML-Notebook unter dem Abschnitt "Weitere Versuche" und im DL den Folder "DL-Experimente". 
Auch die fehlgeschlagenen Weights and Bias Runs wurden nicht enfternt und sind dort immer noch ersichtlich. 

## Präsentation

### Es werden folgende Punkte in der Präsentation besprochen: Aufgabenstellung und Vorgehen, Modelle, Modellevaluation, Lessons learnt

...

### Die Präsentation ist nachvollziehbar und hat einen roten Faden. (Story-telling)

...
