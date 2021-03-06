# Projektseite zu "Maze Race"

von Rebecca Scholz und Frederik Peters                                                                                                                                             
Stormarnschule Ahrensburg                                                                                                                                                           
Klasse 12b                                                                                                                                                                         
Schuljahr 2020/2021


## Inhalt 

[1. Vorwort](#1)                                                                                                                                                                   
[2. Beschreibung](#2)                                                                                                                                                               
[3. Erläuterungen](#3)                                                                                                                                                           

[3.1 Das Labyrinth](#3.1)   
[3.2 Der Spieler](#3.2)  
[3.3 Die Coins](#3.3)                                                                                                                                                           
[3.4 Die Barrikaden](#3.4)                                                                                                                                                       
[3.5 Der Gegenspieler](#3.5)                                                                                                                                                     
[3.6 Das Ziel](#3.6)                                                                                                                                                             
[3.7 Die Complete Bühne](#3.7)

[4. Herausforderungen](#4)                                                                                                                                                         
[5. Schlusswort](#5)


## Vorwort<a name="1"></a>

Unser Spiel "Maze Race" ist im ersten Halbjahr des Informatikunterrichts der 12. Klasse entstanden. Wir sind ohne jegliche Programmiererfahrungen an das Projekt herangegangen. Für unser erstes Projekt haben wir uns dann dazu entschieden mit Snap! zu programmieren, da wir dort mit bereits existierenden Befehlen ein Projekt entwickeln konnten. Somit konnten wir uns so langsam mit der Programmierung vertraut machen und die ersten wichtigen Schritte in Erfahrung bringen.

Maze Race ist ein Spiel, in dem es das Ziel ist, ein Labyrinth erfolgreich zu durchqueren. Die Suche nach dem richtigen Weg durch die verschiedenen Labyrinthgänge wird dabei durch einen Gegner, sich bewegende Wände und verschiedene Aufgaben erschwert. Um hier zu gewinnnen, sollte man ein wenig Geschicklichkeit besitzen. Wer also Spaß an Geschicklichkeitspielen hat, der kann sich zum Zeitvertreib einen Weg durch unser Labyrinth bahnen.

Link zu unserem Projekt "Maze Race":

https://snap.berkeley.edu/project?user=frederikrebecca&project=Labyrinth

Auf unserer Projektseite werden wir im Folgenden zunächst unser Spiel beschreiben und dann die einzelnen Funktionen und Abläufe genauer erläutern.

## Beschreibung <a name="2"></a> <a name="a"></a>

Wenn man unser Spiel "Maze Race" öffnet, erscheint direkt das zu durchquerende Labyrinth und der Spieler befindet sich an der Startposition links oben im Labyrinth. Das Ziel wird durch das rote Kreuz rechts unten markiert. Man kann nun schon den roten Gegenspieler erkennen, der seinen Weg vor dem Ziel abläuft. Des Weiteren öffnen und schließen sich die Barrikaden, die auf dem Weg zum Ziel aufzufinden sind. Zusätzlich sieht man unten links den grünen Coin, der als erstes eingesammelt werden muss, damit sich der nächste Coin, der blaue, zeigt und ebenfalls eingesammelt werden muss. Hat man dies bewältigt, so zeigt sich der letzte lilane Coin, der, wenn er auch eingesammelt wurde, die Barrikade öffnet, die bislang noch den Weg zum Ziel blockierte. 

![Startposition](https://github.com/Frebecca/Projekt/blob/master/PB-start%20screen.PNG)

Wenn man das Ziel erreicht hat, erscheint der Schriftzug "Complete", welcher ebenfalls einem Labyrinth ähnelt. Der Spieler kann durch die einzelnen Buchstaben laufen, jedoch gibt es hier keine weitere Aufgabe, denn das Spiel ist mit dem Erreichen des Zieles beendet.

![Complete](https://github.com/Frebecca/Projekt/blob/master/PB-complete%20screen.PNG)


Maze Race wurde so programmiert, dass der Spieler, sobald er die Kanten des Labyrinths, die Barrikaden oder den Gegenspieler berührt, zurück an den Anfang des Labyrinths versetzt wird und von vorne beginnen muss. Die Steuerung des Spielers kann ganz einfach und unkompliziert mittels der vier Pfeiltasten erfolgen, die ihn dann je nach Pfeiltaste, nach rechts, links oben oder auch unten gehen lassen. Eine dauerhafte Betätigung einer Taste führt dazu, dass sich der Spieler in dieser Richtung wesentlich schneller bewegt.

## Erläuterungen <a name="3"></a>

### Das Labyrinth <a name="3.1"></a>
Zunächst haben wir unser Labyrinth programmiert. Hierzu haben wir das Labyrinth mit einer Sprite gezeichnet, welche zunächst mit einer vorher eingestellten Schriftgröße und Schriftfarbe senkrechte Linien und dann waagerechte Linien abfährt. Diese haben an gewissen Stellen Lücken, sodass sich dann im Endeffekt das typische Labyrinthmuster ergibt. Das Labyrinth erscheint schon zu Beginn des Spieles, weil es so programmiert wurde, dass es mit dem Klicken des Startbuttons bereits vollständig gezeichnet ist. Hierzu nutzen wir die Funktion "Warp".
Der Ablauf der Programmierung ist folgendermaßen:

Die Sprite startet an einem von uns festgelegten Punkt. Um nun eine Linie zu erzeugen, nutzen wir "Pen down" und die jeweils benötigte Anzahl unserer vorher festgtelegten Variable "Breite", welche durch die Schrittweite 25 definiert ist. Nun verwendet man den Befehl "Pen up", um zum nächsten Anstatzpunkt einer Linie zu kommen. Dabei haben wir den Überblick durch das Verwenden eines imaginären Koordinatensystems behalten. Diese Abfolg wiederholt sich für die senkrechten und waagerechten Linien bis unser gewünschtes Labyrinth fertig gezeichnet ist.

![Prorammierung des Labyrinths](https://github.com/Frebecca/Projekt/blob/master/PB-Labyrinth%20descr.PNG)

### Der Spieler <a name="3.2"></a>

#### Steuerung
Der Spieler wird durch einen kleinen schwarzen Strich dargestellt. Mit Hilfe der vier Pfeiltasten kann man den Spieler in alle vier Richtungen manövrieren. Die Bewegung wird durch den Befehl „When x arrow key pressed“, „Point in direction x“ und „Move 2 steps“ gesteuert. Dieser Ablauf gilt für alle vier Richtungen.

![Steuerung des Spielers](https://github.com/Frebecca/Projekt/blob/master/Spieler%20Steuerung.png)

#### Zurücksetzen des Spielers <a name="c"></a>

Sobald der Spieler die Kanten des Labyrinths, die Barrikaden oder den Gegenspieler berührt, wird er an den Start zurückgesetzt. Die Position des Startpunktes haben wir durch die Variable "go to x: X y: Y" definiert.

![Zurücksetzen des Spielers](https://github.com/Frebecca/Projekt/blob/master/Spieler%20Zs.png)

#### Berührung der Coins <a name="b"></a>

Zu den Aufgaben des Spielers gehört es, die drei Coins einzusammeln, damit sich die Barrikade zum Ziel öffnet. 

Der erste grüne Coin ist mit dem Beginn des Spiels bereits sichtbar und muss zuerst eingesammelt werden. Erreicht der Spieler diesen, so versteckt sich dieser auf Grund der Programmierung und der zweite Coin, ein blauer, erscheint an einer anderen Stelle und muss nun ebenfalls erreicht werden. Hier greift das selbe Schema wie beim ersten Coin: Wird der blaue Coin eingesammelt, so zeigt sich der letzte, lilafarbene Coin und der blaue Coin erlischt. Mit dem Einsammeln des letzten Coins öffnet sich die Barrikade und der Weg zum Ziel ist geöffnet.

Der Spieler sendet, sobald er den grünen, blauen bzw. lilafarbenen Coin berührt, eine Nachricht an diesen, sodass sich der berührte Coin dann versteckt und der folgende Coin erscheint. Soabld der Spieler den letzten Coin berührt, wird zusäztlich der Befehl an die Barrikade, bzw. das "Objekt" gesendet, sich abwechselnd zu öffnen und schließen.

![Nachricht von Spieler an Coins](https://github.com/Frebecca/Projekt/blob/master/Coins%20Spieler.png)

![Reaktion der Coins](https://github.com/Frebecca/Projekt/blob/master/Coins%20Coin.png)

#### Erreichen des Ziels <a name="d"></a>

Wenn der Spieler das Ziel „Labyrinth“ berührt, wird eine Nachricht an alle versendet, die den Befehl enthält, sich zu verstecken. Die Complete Bühne, die oben bereits gezeigt wurde [(siehe Bild)](#a), erscheint und der Spieler ändert seine Position, sodass er sich nun innerhalb des Schriftzuges befindet und bewegen kann.

![Spieler Steuerung, sobald Ziel erreicht ist](https://github.com/Frebecca/Projekt/blob/master/Spieler%20Ziel.png)

### Die Coins <a name="3.3"></a>

Die Programmierung der Coins lässt sich bei der Erläuterung des Spielers unter der [Berührung der Coins](#b) nachlesen.

### Die Barrikaden <a name="3.4"></a>

In unserem Spiel befinden sich insgesamt vier Barrikaden, von denen sich drei zum Spielbeginn bereits ständig öffnen und schließen und eine erst mit dem Einsammeln des letzten Coins bewegt.
Unsere Programmierung für jede einzelne Barrikade besteht aus der Festgelegten Position und dem Befehl, sich nach jeweils zwei Sekunden einen ganzen Schritt (Gangbreite) zu bewegen. Die Barrikade wechselt also im Zwei-Sekunden-Takt die Position, sodass sich ein Öffnen und Schließen ergibt.

![Barrikaden Steuerung](https://github.com/Frebecca/Projekt/blob/master/Barrikade%20Str.png)

Falls der Spieler eine Barrikade berührt, wird er an den Spielanfang [zurückgesetzt](#c).

### Der Gegenspieler <a name="3.5"></a>

Unser roter Gegenspieler ist schon zu Beginn des Spiels sichtbar und fährt die von uns festgelegte Strecke ab. Dabei versperrt er teilweise den Weg zum lilafarbenen Coin, sodass sich der Spieler im passenden Moment an dem Gegenspieler vorbei bewegen muss. Berührt der Spieler den Gegenspieler, so wird er an den Spielanfang [zurückgesetzt](#c). 

![Gegenspieler](https://github.com/Frebecca/Projekt/blob/master/Gegenspieler.png)

Die Programmierung des Gegenspielers basiert auf der Startposition und der sich dauerhaft wiederholenden abzulaufenden Strecke, wobei sich zwischen jedem einzelnen Schritt 0,7 Sekunden Pause befinden. 

![Steuerung des Gegenspielers](https://github.com/Frebecca/Projekt/blob/master/Str%20Gegenspieler.png)

### Das Ziel <a name="3.6"></a>

Das Ziel, welches durch das rote Kreuz markiert ist, haben wir gezeichnet. Sobald der Spieler dieses berührt, zeigt sich die [Complete Bühne](#a).

Die Steuerung des Spielers, sobald dieser das [Ziel berührt](#d), ist unter der Erläuterung des Spielers bei Berührung des Ziels nachzulesen.

![Ziel](https://github.com/Frebecca/Projekt/blob/master/Ziel.png)

### Die Complete Bühne <a name="3.7"></a>

Die Complete Bühne fungiert als Endbildschirm, sobald das Ziel erreicht wurde. Außerdem ist es ein weiteres Labyrinth, das vom Spieler durchlaufen werden kann – jedoch ohne weiteres Ziel. Diese Funktion ist ein extra Feature. 

Die Bühne ist so programmiert, dass eine Sprite zunächst den äußeren Umriss und dann das Innenleben zeichnet. 

![Schriftzug](https://github.com/Frebecca/Projekt/blob/master/C%20B.png)

![Programmierung der Complete Bühne](https://github.com/Frebecca/Projekt/blob/master/C%20B%202.png)

## Herausforderungen <a name="4"></a>

Wir standen vor zwei größeren Herausforderungen. Zum einen sind wir ohne jegliche Programmiererfahrungen in den Informatikunterricht gekommen und mussten uns zunächst einmal überlegen, was und womit wir unser Projekt programmieren möchten. Wir hatten zwei Ideen und haben uns zunächst mit der ersten Idee, einer Spirale, auseinandergesetzt. Jedoch wollten wir dann doch lieber unsere zweite Idee, ein Labyrinth, weiter verfolgen und haben somit nach einigen Stunden mit einem neuen Projekt angefangen.

Unsere zweite Herausforderung bestand darin, dass wir manchmal nicht direkt nachvollziehen konnten, warum gewisse Programmierungen nicht so funktionieren oder für uns unerklärliche Bewegungsabläufe geschehen. Dies betraf beispielsweise die Hitbox, das Zurücksetzen bei Berührungen und die Zeichnung des Labyrinths. Die Probleme haben uns teilweise ein paar Stunden lang beschäftigt, aber letztendlich konnten wir auch diese bewältigen und unser Projekt weiter entwickeln.

## Schlusswort <a name="5"></a>

Rückblickend können wir sagen, dass wir unser Projekt stets mit weiteren Features erweitern konnten und uns immer wieder neue Idee kamen, mit denen wir es erweitern konnten. Unser Spiel hat sich von der Programmierung beziehungsweise Zeichnung des Labyrinths über den Spieler, der zum Ziel gelangen und dabei herausfordernde Hindernisse umgehen und Aufgaben bewältigen muss, zum komplexeren Labyrinth entwickelt. Als extra Feature gibt es bei dem Erreichen des Ziels den Schriftzug "Complete", in welchem sich der Spieler wie in einem Labyrinth bewegen kann.

Wir sind sehr zufrieden mit dem, was wir in den paar Monaten Informatikunterricht mit keinerlei Programmiererfahrung erreichen konnten und freuen uns auf unser nächstes Projekt, bei dem wir weitere Techniken und Programmiersprachen lernen und anwenden können.
