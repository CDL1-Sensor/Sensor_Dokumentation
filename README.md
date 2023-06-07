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
Nachdem eine [Datenpipeline](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/tree/master/data_ingestion) erstellt wurde, die uns die aufgenommenen Sensordaten in ein Polardataframe überführt hat, haben wir festgestellt, dass die unterschiedlichen Sensoren, unterschiedlich Startpunkte der Messungeen haben und uns somit viele NA Werte geliefert hat. 

Als Beispiel des Problems hier ein kleiner Beispielausschnitt vom DataFrame.   
![image](https://user-images.githubusercontent.com/66916399/236678276-1526ec57-97d4-4b03-9417-28a2c28ad8ed.png)

Um Daten nicht zu verlieren ersetzten wir die NA Werte mit 0. Zunächst haben wir die Daten getrimmt und aggregiert.
Diese Vorgehensweise dazu findet man detailiert mit Code hier in diesem [Data Wrangling Notebook](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/blob/master/data-wrangling.ipynb). 

Getrimmt wurden jeweils die ersten und letzen 5 Sekunden der Daten mit der Funktion trim_all_files. Dies wurde gemacht um irrelevanten Daten, wie die Wartezeit von 5 Sekunden bei der Aufnahme, nicht in der weiteren Verarbeitung einzubeziehen.

Die Aggregation erfolgte indem die Daten jeweils in 5 Sekunden Zeitfenster aggregiert wurden. Die Idee besteht darin, Messdaten zu nehmen und diese in gleichgrosse Zeitfenster zu unterteilen. In jedem Zeitfenster werden dann die Sensorwerte mithilfe von Aggregationsfunktionen wie dem Durchschnitt, Median, Minimum oder Maximum berechnet. Wobei es wichtig ist, dass die Frequenz der Sensorwerte in allen Datensätzen gleich bleibt, insbesondere beim Rolling Mean. Dies bedeutet, dass die Anzahl der Beobachtungen pro Sekunde konsistent sein sollte, um genaue Ergebnisse zu gewährleisten.

Um die Daten für das Machine Learning zu brauchen, wurden diese preprocessed. Dabei wurden die Daten hauptsächlich in Train und Validation Set gesplittet. Zunächst wurden mit undersampling oder oversampling die Test sowie Validierungsdaten anhand von Plots verglichen. 


# Explorative Datenanalyse

Gesammthaft wurden 303 Mesuungen gemacht.

Im [Notebook der explorativen Datenanalyse](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/blob/master/eda.ipynb) wurden vorallem Visualisierungen generiert und die Daten zu verstehen. Zu Beginn wurden die Anzahl Messungen pro Person und Bewegungsprofile geplottet. Danach wurden die Sensoren mit Boxplots dargestellt. Um mehr über einzelne User zu erfahren, haben wir Sensordaten zweier User verglichen. Zu guter letzt wurden auch alle Sensordaten anhand von Linienplots dargestellt. Dies jeweils für jeden Sensor einmal auf den unbearbeiteten Daten und einmal auf den getrimmten Daten.

Weitere Einsichten gewannen wir indem wir ein pandasprofiling als Inspiration auf unsere Daten gemacht haben. Hierfür wurde ein separates [Notebook EDA pandansprofiling inspiration](https://github.com/CDL1-Sensor/Sensor_Data-Wrangling-und-EDA/blob/master/eda-pandasprofiling-inspiration.ipynb) generiert. 

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


# Mobile App / Frontend Tensorflowjs:
- Repo : https://github.com/CDL1-Sensor/Mobile-Frontend
**Installation** siehe Readme.md
## Reactivity:
Es wird auf folgende Javascript Objects reactive reagiert.
``` js
watch(
  () => ({
    alpha: orientation.alpha,
    beta: orientation.beta,
    gamma: orientation.gamma,
    x: motion.acceleration?.x,
    y: motion.acceleration?.y,
    z: motion.acceleration?.z,
    gx: motion.accelerationIncludingGravity?.x,
    gy: motion.accelerationIncludingGravity?.y,
    gz: motion.accelerationIncludingGravity?.z,
    rx: motion.rotationRate?.alpha,
    ry: motion.rotationRate?.beta,
    rz: motion.rotationRate?.gamma,
  }),
 ```
## DataCreation:
Hier werden die Daten so transformiert, damit sie mit dem Deeplearning Model übereinstimmen, sprich mit Window und Stepsize erstellt (im Tensor).
``` js
const createData = () => {
  const window_size = 400;
  const step_size = 100;
  const X = measurments.value.map((value) => [
    value.alpha || 0,
    value.beta || 0,
    value.gamma || 0,
    value.x || 0,
    value.y || 0,
    value.z || 0,
    value.gx || 0,
    value.gy || 0,
    value.gz || 0,
    value.rx || 0,
    value.ry || 0,
    value.rz || 0,
  ]);

  // Create a sliding window of X with the specified window and step sizes
  const X_windows = [];
  for (let i = 0; i <= X.length - window_size; i += step_size) {
    const window = X.slice(i, i + window_size);
    X_windows.push(window);
  }
  // Reshape X_windows to 3D format (samples, timesteps, features)
  const samples = X_windows.length;
  const timesteps = X_windows[0].length;
  const features = X_windows[0][0].length;
  const reshapedX_windows = tf
    .tensor(X_windows)
    .reshape([samples, timesteps, features]);
  return reshapedX_windows;
};
```

## Prediction:
Hier wird nun das Model importiert und mittels den X_window Objects die acitivites predicted.
Und anschliessend wird ein Alert Fenster augegeben und predicted.
Im Res ist jeweils ein Tensor mit den jeweiligen Probablities der Acitivtäten.
Das label ist klartext die Activity die am meisten Vorgeschlagen wurde.

``` js
const predictData = async () => {
  const model = await importModel();
  debugger;
  const X_widow = createData();

  const res = await model.predict(X_widow);
  alert(res);
  // [laufen, rennen, sitzen, stehen, treppenlaufen, velofahren]
  const labels = [
    "laufen",
    "rennen",
    "sitzen",
    "stehen",
    "treppenlaufen",
    "velofahren",
  ];
  const index = res.argMax(1).dataSync()[0];
  const label = labels[index];
  alert(label);
  };
```


# Export von Deep Learning Modell für Json Model in Tensorflow JS:
Wir konvertieren unsere Models manuell, da die bin Files nicht mittels Json Model convertiert werden können.
- Wir benutzten den Command: **tensorflowjs_wizard**

:warning: Bitte folgende Anleitung folgen für Installation, muss zwingend Python 3.6 sein.

from: C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\saved_model\sensor_model.h5
to: C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\saved_model\jsModel

:warning: **Ersetzten sie**: 
C:\Users\super\OneDrive\Dokumente\GitHub\Mobile_Frontend\Sensor_Klassifikation-mit-Deep-Learning\
Mit ihrem Repository prefix:
<Repo>\saved_model\sensor_model.h5


https://www.npmjs.com/package/@tensorflow/tfjs-converter

used cli commands:
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


