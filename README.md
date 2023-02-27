# Planung Konzeption
Abgabetermin: 16. März 2023   
Dieses Dokument dient als Planunung und Konzeption unserer cdl1/4Da Sensor based Activity Recognition Challenge.  
Dabei beantworten wir die vorgegebenen Leitfragen im [Spaces](https://spaces.technik.fhnw.ch/spaces/sensor-based-activity-recognition).

## Ziel: welche Bewegungsprofile erkannt werden sollen und mit welcher erhofften Genauigkeit  

Um eine umfassende Datenerfassung der Bewegungsprofile zu gewährleisten, beabsichtigen wir, insgesamt sechs Bewegungsprofile zu erheben. Die Datensammlung wird gruppenübergreifend mithilfe der SensorLogger-App erfolgen.

Nachfolgend werden die sechs Bewegsungsprofilen aufgelistet. 

- Laufen
- Rennen
- Treppenlaufen
- Velofahren
- Stehen
- Sitzen

Unser Ziel ist es, für jedes der sechs Bewegungsprofile eine Klassifizierung mit dem bestmöglichen Modell zu erreichen und dabei eine hohe Genauigkeit anzustreben, die im Bereich von gut bis sehr gut liegen sollte.

Im Folgenden präsentieren wir eine Tabelle mit verschiedenen Metriken, anhand derer wir als Gruppe die Ergebnisse als "sehr gut", "gut", "genügend" oder "ungenügend" bewerten können.

| Gruppenbeurteilung / Metrik | Accuracy | Precision | Recall | F1-Score |
|-----------------------------|----------|-----------|--------|----------|
| Sehr gut                    | 0.9      | 0.9       | 0.9    | 0.9      |
| Gut                         | 0.7      | 0.7       | 0.7    | 0.7      |
| Genügend                    | 0.5      | 0.5       | 0.5    | 0.5      |
| Ungenügend                  | 0.2      | 0.2       | 0.2    | 0.2      |

Das Dömänenwissen über die Metriken behandeln wir [hier](https://github.com/CDL1-Sensor/Sensor_Domaenverstaendnis) im Abschnitt Klassifikationsmetriken.

Ein weiterer Aspekt ist, dass die Klassifizierung der Bewegungsprofile sowohl für Android- als auch für Apple-Geräte funktionieren sollte, die mit dem Sensorlogger die Messungen durchführen.

## Scope: Was genau im Projekt erreicht werden soll / was nicht

Unser Ziel ist es, eine umfassende Analyse des Tagesablaufs oder Tagesabschnitt durchzuführen, indem wir ein Programm zur Aufzeichnung der Bewegungsprofilen (Zb. SensorLogger) verwenden und die aufgenommenen Daten anschliessend im **nachinein** in der eigenen programmierten Applikation auswerten.   
Damit können wir feststellen, wann welches Bewegungsprofil zur welcher Zeit aufgetreten ist.   
Hierzu werden anschliessend zu den sechs Bewegungsprofilen eine Statistik der aufgenommenen Person durchgeführt.   

Ein wichtiger Use-Case besteht darin, den Tagesablauf der Person genauer zu analysieren und festzustellen, ob sich diese ausreichend bewegt. Hierbei können wir durch die Auswertung der Bewegungsprofile wertvolle Erkenntnisse gewinnen. 

Dabei sind folgende Punkte noch offen die wir im Laufe der Bearbeitung der Challenge klären müssen.
- Wie speichern wir die aufgenommenen Tagesabläufe?
- Welches Modell verwenden wir für unsere Applikation? 

Was nicht in unserer Challenge erreicht werden sollte ist die Klassifikation von Bewegungsprofilen in Echtzeit mittels einer selbst programmierten App. 

## Planung: Was es für Milestones gibt und wann diese etwa erreicht sein sollen 

Unsere Milestone stellen wir in einer Tabelle Deadlines übersichtlich dar. 

| Milestone | Was?                                              | Deadline   |
|-----------|---------------------------------------------------|------------|
| 1         | Planung und Konzeption                            | 16.03.2023 |
| 2         | Datenbeschaffung beenden (in Absprache)           | 07.03.2023 |
| 3         | Data Wrangling und EDA abschließen                | 30.04.2023 |
| 4         | Implementierung von ML Modellen                   | 16.06.2023 |
| 5         | Webapp Integration                                | 16.06.2023 |
| 6         | Dokumentation parallel zu allen Milestones machen | 16.06.2023 |
| Deadline  | Abgabe                                            | 16.06.2023 |

## Konzept: Wie das Vorgehen für die Datensicherung und Beschriftung, die Datenverarbeitung, sowie die Modellierung ist

Die Datensammlung geschieht Gruppen übergreifend, um möglichst viele Bewegungsprofile sammeln zu können. 
Die Datensicherung geschieht durch den Export an Etienne Roulet's OneDrive. 
Die Beschriftung der Daten wird sichergestellt, indem für jedes Bewegungsprofil von jeder Person eine Orderstruktur erstellt wurde.
Die Rohdaten werden dabei in einem json Format von Sensorlogger exportiert, dabei wird der Dateiname nummeriert und Gerätetyp beschriftet.

Die Ordnerstruktur sieht wie folgt aus.

├── Messungen  
│   ├── Aktivitätstyp  
│   │   ├── Vorname_Nachname  
│   │   │  ├── XX_DeviceTyp.json  

Bei der Datenverabeitung entscheiden wir aufgrund vom Domänenwissen, ([hier](https://github.com/CDL1-Sensor/Sensor_Domaenverstaendnis)), welche Sensoren im Grunde genommen für unsere Klassifikationsaufgabe in Frage kommen. 
Anschliessend erfolgt das einlesen von den json Datei in ein geeignetes DataFrame (Pandas oder Polars) 
Nachdem wir die Bewegungsprofilen sowie Labeling in ein passendes DataFrame überführen konnten erfolgt die Explorative Datenanalyse und Data Wrangling.
Dabei werden diverse Bewegungsprofile mit dem entsprechenden Sensor gegenüber der Zeit geplottet (Matplotlib oder Seaborn). 
Ein Data Wrangling part könnte sein, das Schneiden von Messungen der ersten 10 Sekunden und der letzten 10 Sekunden. 
Nach dem die Daten aufbereitet und exploriert wurde, erfolgt die Trennung der Daten in Trainingsdaten und Validierung-/Testdaten. 
Anschliessend die Auswahl an Machine Learning sowie Deep Learning Modellen und trainieren der Modelle. 
Um zu schauen, wie gut unsere Modelle performen nutzen wir die Validierung-/Testdaten und werten aus und vergleichen Unterschiedliche Modelle
untereinander. Als aller letzter Schritt werden die Daten in der Applikation integriert und getestet.  

Zum jetzigen Zeitpunkt stellen sich nun die folgenden Fragen:
- Welche Modelle kommen in Frage ohne DL? (Clustering Algorithmen, Decision Trees)
- Welche Modelle kommen mit DL in Frage? (CNN, RNN)

## Output: In welcher Form die Erkenntnisse präsentiert werden sollen 

Die gewonnen Erkentnissen werden in Form von einem Pitch präsentiert. Dabei wird unsere erstellte Frontend Applikation präsentiert und gezeigt, wie diese funktioniert und genutzt werden kann. 



