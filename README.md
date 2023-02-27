# Planung Konzeption
Abgabetermin: 16. März 2023  
Dieses Dokument dient als Planunung und Konzeption unserer cdl1/4Da Sensor based Activity Recognition Challenge.

## Ziel: welche Bewegungsprofile erkannt werden sollen und mit welcher erhofften Genauigkeit (
Bewegungsprofile
- 6 Bewegungsprofile auflisten 

Genauigkeit
- Sowohl fuer schlechte und gute Handys erkennen 
- Sowohl Android und Iphone koenne zu klassifizieren

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


