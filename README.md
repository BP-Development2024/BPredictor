# BPredictor

BPredictor ist eine Anwendung für maschinelles Lernen, mit dem in erster Linie Modelle trainiert und Vorhersagen auf der Grundlage von Daten zu Gebäuden, Bauteilen und Baustoffen getroffen werden können. Es kann jedoch auch auf anderen Datensätzen mit kontinuierlichen und kategorialen In- und Regressionsergebnissen trainiert werden.

BPredictor is a machine learning tool primarily aimed at training models and making predictions based on building, building component and building material data. Can however also be trained on other datasets with continuous and categorial in- and regressive outputs.
English Version below!

Die Anwendung kann entweder in Google Colab oder als Jupyter-Notebook ausgeführt werden. Es werden Quellcode-Versionen (BPredictor_X_X_GoogleColab und BPredictor_X_X_JupyterNB) für beide Optionen zur Verfügung gestellt. Es ist darauf zu achten, je nach Entwicklungsumgebung die korrekte Version zu verwenden, da es sonst zu Problemen beim Datenimport und der Darstellung von Bedienelementen und weiteren Fehlern kommen kann. 

Es folgen einige allgemeine Bedienungshinweise für die Verwendung des BPredictor:

1. Allgemein: Die GUI-Elemente finden sich in Abschnitt 8 und 9 des Notebooks (auch in Google Colab). Dies sind die einzigen Abschnitte, die für User-Interaktion gedacht sind. In Abschnitt 8 findet das Training der ML-Modelle statt. In Abschnitt 9 können Vorhersagen auf Basis der trainierten Modelle gemacht werden. Zu Beginn müssen alle Codebausteine ausgeführt werden (Google Colab: Ctrl-F9; Jupyter-Notebook: Run -> Run all cells).
   
2. Trainingsdaten: Diese müssen im .csv-Format vorhanden sein. Es wird empfohlen, zum Import der Daten das Eingabefeld zur Eingabe des Dateispeicherorts zu verwenden, da diese Methode zuverlässiger ist. Innerhalb der Trainingsdaten ist besonders darauf zu achten, die Spalten klar zu benennen. Doppelungen der Spaltenbenennung, auch mit Einträgen innerhalb des Datensatzes, können zu Problemen führen. Ist z.B. eine Spalte lediglich mit 'E' benannt, kann dies zu Problemen bei der Verarbeitung führen, wenn Einträge in einer Spalte auch den Buchstaben "E" enthalten. Allgemein können Werte in den Trainingsdaten sowohl kontinuierlicher Art (Datentyp Float oder Integer mit mehr als 100 verschiedenen Werten) oder kategorialer Art (String-Bezeichnungen (übersichtlicher) oder Integer-Einträge mit < 100 unterschiedlichen Einträgen) sein. Der Spaltentrenner der .csv-Datei kann in der GUI spezifiziert werden. Standardeinstellung ist ",". Beim Export aus Tabellenkalkulationsprogrammen wie Excel wird häufig ";" verwendet.
  
3.  Speicherort von Modellen und Auswertung: Hierfür müssen in der GUI zwei Ordner eingetragen werden. Bei Google Colab muss es sich dabei um Google Drive Ordner handeln. Im Jupyter Notebook sollten lokale Ordner verwendet werden. Es ist zu empfehlen, für jedes Projekt, das eine neue Art von Trainingsdaten hat, neue Modell- und Auswertungsordner anzulegen, da diese sonst sehr voll und unübersichtlich werden. Zudem können inhomogen gefüllte Ordner zu Problemen bei der Verwendung und Auswertung von Modellen führen.

4.  Treffen von Vorhersagen auf Basis trainierter Modelle: Die GUI zum Treffen von Vorhersagen findet sich in Abschnitt 9. Es ist darauf zu achten, den korrekten Modellordner (nicht die models.csv Datei selbst) anzugeben. Bei der Auswahl des zu verwendenden Modells durch ein Dropdown-Menü sind die neuesten Modelle unten zu finden.

5.  Hilfe zum Troubleshooting

    5.1 Probleme beim Training
      - Datei wird nicht gefunden / Beim Klicken von "Datenimport starten" geschieht nichts: In Google Colab: Pfad-Feld statt Upload-button benutzen (Upload kann bei größeren Dateien fehlschlagen); Berechtigung zum Zugriff auf Google drive sicherstellen; sichergehen, dass der Pfad auf Google Drive verweist und nicht auf eine lokale Datei (z.B. aus der linken Tool-Leiste kopieren). 
      - Merkwürdige / Zu wenige In- und Outputparameter zur Auswahl: Spaltentrennzeichen überprüfen
      - Es werden zu viele oder unerwartete aussehende Beispiele für Outputs nach dem Datenimport gezeigt: Benennung der Spalten in den Trainingsdaten überprüfen. Zu kurze Benennungen, z.B. nur einer oder wenige Buchstaben / Zahlen, können zu Dopplungen mit den Werten in der Tabelle führen und die Zuordnung der Spalten stören. Weiterhin prüfen, ob ein kategorialer Wert als Output gewählt wurde. BPredictor ist nur zur Vorhersage kontinuierlicher Outputs geeignet (Kategoriale Inputs hingegen können verarbeitet werden).
      - Errormeldung zu Auswertungs- oder Modellpfad: Sichergehen, dass die angegebenen Ordner tatsächlich auf Google Drive (für Google Colab) oder lokal auf dem Rechner (Jupyter Notebook) existieren.
  
    5.2 Probleme beim Treffen von Vorhersagen
      - Modellordner wird nicht gefunden: Überprüfen, ob der Ordner auf Google Drive (Google Colab) oder lokal (Jupyter Notebook) vorhanden ist. Zugriffsrecht auf Google Drive prüfen. Dateipfad auf Korrektheit prüfen, z.B. Anführungszeichen entfernen.
      - Oberstes Modell in Modellliste lässt sich nicht auswählen: Zuerst ein anderes Modell auswählen, und dann das oberste.
      - Welches Modell soll ich wählen? Neuere Modelle befinden sich unten in der Liste. Auf Modellart (NN, RF, DT, SVM, LR) achten. Jedes Modell ist zudem mit einem Timestamp gespeichert, der im Modellnamen bei der Auswahl zu sehen sein sollte, im Format: folderpath/xx_model_YYYYMMDD_HHMMSS. Der Wert nach dem Modellname ist der R²-Wert (Bestimmtheitsmaß). Es wird empfohlen, nur Modelle zu einer Art von Trainingsdaten in einem Ordner abzuspeichern, um Übersichtlichkeit zu gewährleisten.

English Version:

The application can be run either in Google Colab or as a Jupyter notebook. Source code versions (BPredictor_X_X_GoogleColab and BPredictor_X_X_JupyterNB) are provided for both options. Care should be taken to use the correct version depending on the development environment, as otherwise there may be problems with data import and the display of control elements and other errors. 

The following are some general operating instructions for using the BPredictor:

1. general: the GUI elements can be found in section 8 and 9 of the notebook (also in Google Colab). These are the only sections intended for user interaction. Section 8 is where the training of the ML models takes place. In section 9, predictions can be made on the basis of the trained models. At the beginning, all code blocks must be executed (Google Colab: Ctrl-F9; Jupyter notebook: Run -> Run all cells).

2. Training data: This must be available in .csv format. It is recommended to use the input field for entering the file location to import the data, as this method is more reliable. Within the training data, particular care must be taken to name the columns clearly. Duplication of column names, even with entries within the data set, can lead to problems. If, for example, a column is only named ‘E’, this can lead to problems during processing if entries in a column also contain the letter ‘E’. In general, values in the training data can be continuous (data type float or integer with more than 100 different values) or categorical (string names (clearer) or integer entries with < 100 different entries). The column separator of the .csv file can be specified in the GUI. The default setting is ‘,’. When exporting from spreadsheet programmes such as Excel, ‘;’ is often used.

3. storage location of models and evaluation: Two folders must be entered in the GUI for this purpose. For Google Colab, these must be Google Drive folders. Local folders should be used in the Jupyter Notebook. It is recommended to create new model and evaluation folders for each project that has a new type of training data, otherwise they will become very full and confusing. In addition, inhomogeneously filled folders can lead to problems when using and analysing models.

4. making predictions based on trained models: The GUI for making predictions can be found in section 9. care must be taken to specify the correct model folder (not the models.csv file itself). When selecting the model to be used from a drop-down menu, the latest models can be found below.

5 Troubleshooting help
 
  5.1 Problems during training
      - File is not found / Nothing happens when clicking on ‘Start data import’: In Google Colab: Use the field to enter the path instead of the “Upload-Button” (may not be able to handle big file sizes); ensure authorisation to access Google drive; make sure that the path refers to Google Drive and not to a local file (e.g. copy from the left toolbar).
      - Strange / Too few input and output parameters to choose from: Check column separators
      - Too many or unexpected looking examples of outputs are shown after the data import: Check the naming of the columns in the training data. Names that are too short, e.g. only one or a few letters/numbers, can lead to duplications with the values in the table and disrupt the assignment of the columns. Also check whether a categorical value has been selected as the output. BPredictor is only suitable for predicting continuous outputs (categorical inputs, on the other hand, can be processed).
      - Error message for evaluation or model path: Make sure that the specified folders actually exist on Google Drive (for Google Colab) or locally on the computer (Jupyter Notebook).
      
  5.2 Problems when making predictions
      - Model folder is not found: Check whether the folder is available on Google Drive (Google Colab) or locally (Jupyter Notebook). Check access rights to Google Drive. Check file path for correctness, e.g. remove inverted commas.
      - Top model in model list cannot be selected: First select another model and then the top model.
      - Which model should I choose? Newer models are at the bottom of the list. Pay attention to the model type (NN, RF, DT, SVM, LR). Each model is also saved with a timestamp, which should be visible in the model name when selecting, in the format: folderpath/xx_model_YYYYMMDD_HHMMSS. The value after the model name is the R² value (coefficient of determination). It is recommended that you only save models for one type of training data in one folder to ensure clarit
