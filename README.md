# Neuroprojekt 2017 'Heatmap' Hack

*English version below* 

## Über das Projekt

Der Code ermöglicht es auf https://www.soscisurvey.de, einem Tool für Onlineumfragen, eine Frage zu erstellen, in der auf einem Bild per Mausklick Punkte markiert werden können. Die Position der Punkte wird sowohl auf dem Bild dargestellt als auch in den Fragebogendaten gespeichert.

Dieser Code entstand im Rahmen der Veranstaltung Projekt Neuroergonomie im Sommersemester 2017 an der TU Berlin. Er ermöglichte es unserer Projektgruppe Probanden in einem Online Fragebogen die fünf von ihnen am häufigsten genutzten U-Bahn Stationen zu markieren. 

## Setup in einem Fragebogen

Die 'Heatmap' funktioniert aus dem Zusammenspiel dreier Komponenten:
 - Eine Frage des Type *Interne Variable* auf SoSciSurvey
 - Dem Bild, das angeklickt werden soll, hochgeladen auf SoSciSurvey
 - Dem Code in `map.html` der in eine `HTML-Code` Komponente in einer Frage kopiert wird

 ### In wenigen Schritten zur 'heatmap'
 1. Erstelle einen Fragebogen auf https://www.soscisurvey.de/
 2. Lade das Bild hoch, das du benutzen möchtest
 3. Erstelle eine Frage des Formats *Interne Variable* und füge sie deinem Frageboben hinzu
    * Diese Frage benötigt auf jeden Fall zwei Variablen für die Abmessungen des Bildes, um diese bei der Auswertung zu benutzen
    * Für jeden Punkt den du hinzufügen möchtest benötigst du je zwei weitere Variablen für die Koordinaten des Punktes
    * Merke dir ausserdem den Namen der Variable (z.B.: 'U501')
4. Füge die *Interne Variable* Frage zu deiner Fragebogenseite hinzu
5. Kopiere anschließend den gesamten Code aus `map.html` in eine `HTML-Code` Komponente auf deiner Seite.
6. Im letzten Schritt musst du noch eine wenige Anpassungen im Code vornehmen wie im nächsten Abschnitt beschrieben.

### Anpassen der 'heatmap'
Finde die jeweils dargestellten Abschnitte im Code und passe die Werte an.

Lege die Quelle des Bildes fest, dass verwendet werden soll. In diesem Beispiel ist es *test-map.png*. Der korrekte Wert für `src` findet sich auch unter *Bilder und Mediendateien* und der Option *HTML-Tag*.
```html
    <img id="bg-img" src="test-map.png">
```

Lege die Anzahl der Punkte fest die angeklickt werden sollen. In diesem Beispiel ist sie *5*.
```javascript
    const maxPoints = 5;
```

Lege den Namen der *Interne Variable* fest, um die Daten zu speichern. Hier ist er *U501*. Du findest ihn z.B. auf der Seite des Fragebogens.
```javascript
    StorageCtrl.initialize('U501', showError);
```

## Viel Erfolg bei deiner Umfrage!

---
*English version*

## About

This code makes it possible to add a 'heatmap' to a question on https://www.soscisurvey.de, a survey tool. It will enable the user to click on a picture to mark certain points. The points will be shown on the picture and their position stored in the survey's database.

This code was created during the project Projekt Neuroergonomie 2017 at the Technical University Berlin.

## Setup in your survey

The 'heatmap' needs three components to work:
 - A *Interne Variable*  question on SoSciSurvey
 - The picture you want to click on, uploaded to SoSciSurvey
 - The code in `map.html` embedded in a `HTML-Code` component on your site

 ### Steps to your own 'heatmap'
 1. Make a survey on https://www.soscisurvey.de/
 2. Upload your picture
 3. Make a *Interne Variable* question and add it to your questionnaire
    * The question needs two variables for storing the size of the image in ervey case
    * For every point you want to add you nee two add two more variables for storing the point's coordinates
    * Take a note of the variable name (e.g.: 'U501')
4. Add the *Interne Variable* question
5. Paste the code from `map.html` into a `HTML-Code` component
6. Customize the code as described below.

### Customization of the 'heatmap'
Finde the code described below and edit it accordingly.

Set the source of the image you want to use. In this example it's *test-map.png*. 
```html
    <img id="bg-img" src="test-map.png">
```

Set the number of points that should be allowed. In this example it's *5*.
```javascript
    const maxPoints = 5;
```

Set the name of the *Interne Variable* for saving the data. In this example it's *U501*.
```javascript
    StorageCtrl.initialize('U501', showError);
```

## Happy surveying!
