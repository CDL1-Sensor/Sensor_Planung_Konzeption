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

Das Dömänenwissen über die Metriken behandeln wir [hier](LINK):

Ein weiterer Aspekt ist, dass die Klassifizierung der Bewegungsprofile sowohl für Android- als auch für Apple-Geräte funktionieren sollte, die mit dem Sensorlogger die Messungen durchführen.

## Scope: Was genau im Projekt erreicht werden soll / was nicht
Was wollen wir erreichen?
- Tag aufzeichnen in einem Programm und Daten analysieren, wann man um welche Zeit welches Bewegungsprofil hatte
- Statstik vom Tag aufgrund von 6 Bewegungsprofilen
- Use Case - Tagesabblauf analysieren und schauen, ob die Person sich bewegt.
- Webapp 

Was nicht?
- Echtzeit Messungen und Klassifikationen

Frage: 
- Wie speichern wir die Daten?
- Welches Modell verwenden wir in der Webapp? 

## Planung: Was es für Milestones gibt und wann diese etwa erreicht sein sollen 
Milestones 1: Planung und Konzeption bis 16.03.2023
Milestone 2: Datenbeschaffung beenden bis 07.03.2023 (in Absprache mit anderen Teams)
Milestone 3: Data Wrangling und EDA abschliessen bis 30.04.2023 
Milestone 4: Implementierung von ML Modellen bis 16.06.2023 
Milestone 5: Webapp Integration bis 16.06.2023

Milestone 6: Dokumentation parallel zu allen Milestones machen bis 16.06.2023

Deadline fuer alle Abgaben: **16.06.2023** 

## Konzept: Wie das Vorgehen für die Datensicherung und Beschriftung, die Datenverarbeitung, sowie die Modellierung ist

Datensicherung und Beschriftung 
(Beschriftung = Aktivitaetyp, Personennamen, Devicetyp -> bsp: Nummerierung Treppenlaufen, Lea, Huawei)
Dateisicherung -> 01_Huaweii.json
Kurze Messungen unter 5 Minuten. 

Datensicherung auf OneDrive Etienne -> Gruppenuebergreifend hochladen 

Datenverarbeitung: Auswahl von Sensoren -> Einlesen von Bewegungsprofilen -> DataFrames (Pandas, polars) -> Plots fuer jedes Bewegungsprofil pro Person und Aktivitaet anschauen -> gegebenfalls vordere Zeit und hintere Zeit weg schneiden -> Daten in passendes Format konvertieren fuer ML (Tensor) -> 
Modelierung: Modelle erstellen -> Modell trainieren -> Modelle Auswerten -> Modelle deployen 

Modelle die in Frage kommen ohne DL: Clustering Algorithmen 
Modelle die in Frage kommen ohne DL: CNN/RNN?
---> ChatGPT konsultieren - machen uns noch Gedanken 

Auswertung von Modellen: 
Accuracy, Recall, Precision, F1-Score, (ROC)

## Output: In welcher Form die Erkenntnisse präsentiert werden sollen 
- Frontend Applikation -> Zeigen wie das funktioniert und genutzt wird. Praesentation der Ergebniss 
- Pitch 


