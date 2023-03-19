# Sensor based Activity Recognition Dokumentation
Abgabetermin: 16. Juni 2023  
In diesem Repository erfolgt die Dokumentation der Challenge 

Diese Challenge wurde von: Lea Bütler, Manjavy Kirupa, Etienne Roulet und Si Ben Tran bearbeitet.

# Einleitung
 
In heutiger Zeit verwenden nahezu alle Personen ein Smartphone, welches mit Beschleunigungs- und Rotationssensoren ausgestattet ist. Ziel dieser Challenge ist es, Bewegungsprofile aus den Daten dieser Sensoren zu identifizieren und durch Verwendung von Machine-Learning-Modellen zu klassifizieren. In dieser Challenge werden sechs verschiedene Bewegungsprofile erfasst und die Sensordaten werden in einem geeigneten Format verarbeitet, um Machine-Learning- sowie Deep-Learning-Modelle zu erstellen. Bei der Verarbeitung der Daten ist es wichtig, das definierte Zeitfenster zu berücksichtigen und darauf zu achten, dass kein "Data Leakage" zwischen den Trainings- und Testdatensätzen stattfindet. Um eine hohe Accuracy Metrik für die Klassifikation zu erreichen, müssen die Modelle durch verschiedene Methoden, wie beispielsweise der Cross-Validation, optimiert werden. Dadurch kann das Ziel einer Accuracz von mehr als 0.9 erreicht werden.

# Datenerfassung

Die Datenerfassung wurde im Plenum, gruppenübergreifend am 23.02.2023 besprochen. Dabei wurden sechs Bewegungsprofile sowie ein gemeinsames [Konzept](https://github.com/CDL1-Sensor/Sensor_Dokumentation/tree/master/Datenerhebung) zur Datenaufnahme definiert. 

Nachfolgend werden die sechs Bewegsungsprofilen aufgelistet. 

- Laufen
- Rennen
- Treppenlaufen
- Velofahren
- Stehen
- Sitzen

Damit wir die Bewegungsprofile aufnehmen können, nutzen wir die App [Sensor Logger](https://play.google.com/store/apps/details?id=com.kelvin.sensorapp&hl=de_CH&gl=US) 
Bei einer Erfassung eines Bewegungsprofiles wird die Messung im App gestartet und das Handy in die rechte Hosentasche gesteckt, anschliessend wartet man ca. 5 Sekunden und beginnt anschliessend mit der eigentlichen Bewegung. Nach Beendigung der Messung wartet man wieder 5 Sekunden ruhig und nimmt anschliessend das Handy wieder in die Hand und beenedet die Messung. Die Messung wird anschliessend als json File nach Etiennes One Drive File "Messung" exportiert. Die Daten wurden im json Format abgespeichert, damit im späteren Verlauf der Challenge das Einlesen der Daten einfacher gestaltet werden kann. Die Messungen fanden im Zeitraum von 23.02.2023 bis 16.03.2023 statt. Alle Messungen die nach dem 16.03.2023 statt gefunden haben wurden in unserer Challenge nicht berücksichtigt. 

Bemerkungen zu den Bewegungsprofilen
- Beim Treppenlaufen unterscheiden wir nicht, ob wir hinauf oder hinunter laufen
- Mit Rennen ist kein Vollsprint gemeint, sondern joggen in unterschiedliche Geschwindigkeiten
- In unserer Gruppe wurden nur .json Dateien berücksichtigt

# Datenverarbeitung 

Nachdem eine Datenpipeline erstellt wurde, die uns die aufgenommenen Sensordaten in ein Polardataframe überführt hat, haben wir festgestellt, dass die unterschiedlichen Sensoren, unterschiedlich Startpunkte der Messungeen haben und uns somit viele NA Werte geliefert hat. 

Als Beispiel des Problems hier ein kleiner Beispielausschnitt vom DataFrame

**DataFrame** Tabelle zeigen


Das Problem wurde gelöst, indem wir.... 
Die Lösung dazu findet man hier in diesem Data Wrangling Notebook. 


# Explorative Datenanalyse

Gesammthaft wurden XX Aufnahmen gemacht.



Wichtig zu erwähnen ist, dass die Marke vom Handy durchaus einen Einfluss auf die Datenqualität aufweist. 
Smartphones die tendenziell moderner und teuer sind, sind entsprechend besser ausgerüstet. 

Da bei der Modellierung wir alle Smartphone Modelle berücksichgt haben, sollte dies zu keinen Problemen bei den Validierungsdaten oder Testdaten führen. 



# Machine Learning Modelle

- Decision Tree
- Random Forest
- KNN 
- Kluster Algorithmen (K-Means, Dbscan)
- Neuronale Netze


# Deep Learning Modelle

- CNN mit aggregierten Daten
- CNN mit Sensorblider Daten

---



- Führt die Datensammlung so aus, dass die Datenqualität stimmt
- Prüft die Qualität der Daten


