# Sensor based Activity Recognition Dokumentation
Abgabetermin: 16. Juni 2023  
In diesem Repository erfolgt die Dokumentation der Challenge 

Diese Challenge wurde von: Lea Bütler, Manjavy Kirupa, Etienne Roulet und Si Ben Tran bearbeitet.
Dieses README dient als eine Zusammenfassung aller Arbeiten die im Rahmen dieser Challenge gemacht wurden. Die detailierten Dokumentationen befinden sich in den jeweiligen Notebooks oder README vom entsprechenden Repository und werden hier immer wieder weiter verlinkt. 

# Einleitung
In heutiger Zeit verwenden nahezu alle Personen ein Smartphone, welches mit Beschleunigungs- und Rotationssensoren ausgestattet ist. Ziel dieser Challenge ist es, Bewegungsprofile aus den Daten dieser Sensoren zu identifizieren und durch Verwendung von Machine-Learning-Modellen zu klassifizieren. In dieser Challenge werden sechs verschiedene Bewegungsprofile erfasst und die Sensordaten werden in einem geeigneten Format verarbeitet, um Machine-Learning- sowie Deep-Learning-Modelle zu erstellen. Bei der Verarbeitung der Daten ist es wichtig, das definierte Zeitfenster zu berücksichtigen und darauf zu achten, dass kein "Data Leakage" zwischen den Trainings- und Testdatensätzen stattfindet. Um eine hohe Accuracy Metrik für die Klassifikation zu erreichen, müssen die Modelle durch verschiedene Methoden, wie beispielsweise der Cross-Validation, optimiert werden. Dadurch kann das Ziel einer Accuracy von mehr als 0.9 erreicht werden. 

# Datenerfassung
Die Datenerfassung wurde im Plenum, gruppenübergreifend am 23.02.2023 besprochen. Dabei wurden sechs Bewegungsprofile sowie ein gemeinsames [Konzept zur Datenaufnahme](https://github.com/CDL1-Sensor/Sensor_Dokumentation/tree/master/Datenerhebung) zur Datenaufnahme definiert. 

Nachfolgend werden die sechs Bewegsungsprofilen aufgelistet. 

- Laufen
- Rennen
- Treppenlaufen
- Velofahren
- Stehen
- Sitzen

Damit wir die Bewegungsprofile aufnehmen können, nutzen wir die App [Sensor Logger](https://play.google.com/store/apps/details?id=com.kelvin.sensorapp&hl=de_CH&gl=US) Bei einer Erfassung eines Bewegungsprofiles wird die Messung im App gestartet und das Handy in die rechte Hosentasche gesteckt, anschliessend wartet man ca. 5 Sekunden und beginnt anschliessend mit der eigentlichen Bewegung. Nach Beendigung der Messung wartet man wieder 5 Sekunden ruhig und nimmt anschliessend das Handy wieder in die Hand und beenedet die Messung. Die Messung wird anschliessend als json File nach Etiennes One Drive File "Messung" exportiert. Die Daten wurden im json Format abgespeichert, damit im späteren Verlauf der Challenge das Einlesen der Daten einfacher gestaltet werden kann. Die Messungen fanden im Zeitraum von 23.02.2023 bis 16.03.2023 statt. Alle Messungen die nach dem 16.03.2023 statt gefunden haben wurden in unserer Challenge nicht berücksichtigt. 

Bemerkungen zu den Bewegungsprofilen
- Beim Treppenlaufen unterscheiden wir nicht, ob wir hinauf oder hinunter laufen
- Mit Rennen ist kein Vollsprint gemeint, sondern joggen in unterschiedliche Geschwindigkeiten
- In unserer Gruppe wurden nur .json Dateien berücksichtigt

# Datenverarbeitung 
Nachdem eine [Datenpipeline](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/tree/master/data_ingestion) Datenpipeline erstellt wurde, die uns die aufgenommenen Sensordaten in ein Polardataframe überführt hat, haben wir festgestellt, dass die unterschiedlichen Sensoren, unterschiedlich Startpunkte der Messungeen haben und uns somit viele NA Werte geliefert hat. 

Als Beispiel des Problems hier ein kleiner Beispielausschnitt vom DataFrame.   
![image](https://user-images.githubusercontent.com/66916399/236678276-1526ec57-97d4-4b03-9417-28a2c28ad8ed.png)



Das Problem wurde gelöst, indem wir
Die Lösung dazu findet man hier in diesem Data Wrangling Notebook. 


# Explorative Datenanalyse

Gesammthaft wurden XX Aufnahmen gemacht.



Wichtig zu erwähnen ist, dass die Marke vom Handy durchaus einen Einfluss auf die Datenqualität aufweist. 
Smartphones die tendenziell moderner und teuer sind, sind entsprechend besser ausgerüstet. 

Da bei der Modellierung wir alle Smartphone Modelle berücksichgt haben, sollte dies zu keinen Problemen bei den Validierungsdaten oder Testdaten führen. 



# Machine Learning Modelle

## Logistische Regression - Baseline Modell

Als Baseline Modell haben wir eine Logsitische Regression genommen, die mehrere Klassen vorhersagen kann. 
In Sklearn wird die multiclass Logistische Regression durch das One-vs-Rest-Schema (auch als One-vs-All-Schema bezeichnet) implementiert. Das bedeutet, dass die Logistische Regression für jede Klasse eine separate binäre Klassifikation durchführt, indem sie die eine Klasse gegen alle anderen Klassen klassifiziert. Das Ergebnis dieser binären Klassifikationen wird dann kombiniert, um die endgültige multiklassifizierte Vorhersage zu erzeugen.
Beim Baseline Modell wurden die Rohdaten, sprich unverarbeitet eingelesen und der Datensatz aufgrund der niedrigsten Anzahl vorhandenem Bewegungsprofil gleichmässig gesampelt. Der Grund für diese Verarbeitung ist, dass wir als Optimierungsmetrik die Accuracy haben. Anschliessend wurden die Daten in Trainings und Validierungsdaten aufgesplittet in einem Verhältnis von 80:20. Anschliessend wurde das Logistische Modell trainiert und mittels den Validierungsdaten evaluiert, sprich die Accaurcy sowie die Confusion Matrix berechnet und geplottet. 

(Plots und Bilder vom Notebook hinzufuegen)


- Decision Tree
- Random Forest


- KNN 
- Kluster Algorithmen (K-Means, Dbscan)
- Neuronale Netze


# Deep Learning Modelle

- CNN mit aggregierten Daten
- CNN mit Sensorblider Daten

---


# Export von Deep Learning Modell für Json Model in Tensorflow JS:
Wir konvertieren unsere Models manuell, da die bin Files nicht mittels Json Model convertiert werden können.
- Wir benutzten den Command: tensorflowjs_wizard

Bitte folgende Anleitung folgen für Installation, muss zwingend Python 3.6 sein.

from: C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\saved_model\sensor_model.h5
to: C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\saved_model\jsModel

Ersetzten sie 
C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\
Mit ihrem Repository prefix:
<Repo>\saved_model\sensor_model.h5

https://www.npmjs.com/package/@tensorflow/tfjs-converter

example:
tensorflowjs_wizard

Welcome to TensorFlow.js Converter.
- ? Please provide the path of model file or the directory that contains model files.
If you are converting TFHub module please provide the URL.  C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\saved_ 
model\sensor_model.h5
- ? What is your input model format? (auto-detected format is marked with *)  Keras (HDF5) *
- ? What is your output format?  TensoFlow.js Layers Model
- ? Do you want to compress the model? (this will decrease the model precision.)  No compression (Higher accuracy)
- ? Please enter shard size (in bytes) of the weight files?  4194304
- ? Do you want to split weights by layers?  Yes
- ? Do you want to provide metadata?
- Provide your own metadata in the form: <br>
metadata_key:path/metadata.json <br>
Separate multiple metadata by comma. <br>
- ? Which directory do you want to save the converted model in?  C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\sav 
ed_model\jsModel
- ? The output already directory exists, do you want to overwrite it?  Yes
converter command generated: <br>
tensorflowjs_converter --input_format=keras --metadata= --output_format=tfjs_layers_model --split_weights_by_layer --weight_shard_size_bytes=4194304 C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\saved_model\sensor_model.h5 C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\saved_model\jsModel





File(s) generated by conversion:
Filename                           Size(bytes)
group1-shard1of1.bin                1024
group10-shard1of1.bin               20200
group11-shard1of1.bin               1224
group2-shard1of1.bin                512
group3-shard1of1.bin                3200
group4-shard1of1.bin                1600
group5-shard1of1.bin                800
group6-shard1of1.bin                6400
group7-shard1of1.bin                16512
group8-shard1of1.bin                2560800
group9-shard1of1.bin                80400
model.json                          10727
Total size:                         2703399
<br><br>

- Führt die Datensammlung so aus, dass die Datenqualität stimmt
- Prüft die Qualität der Daten


