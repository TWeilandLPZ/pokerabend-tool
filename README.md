# Pokerabend Preparing Tool

*by Tobi*

Ein kleines Browser-Tool zum Trainieren des Kartengefühls für Texas Hold'em. Wähle eine Starthand, teile Flop, Turn und River aus und sieh live, wie sich deine Gewinnwahrscheinlichkeit über die Straßen entwickelt.

Läuft komplett im Browser, ohne Server, ohne Installation, ohne Account.

## Nutzen

Einfach den Link öffnen — funktioniert auf dem Handy genauso wie am Rechner:

[**👉 Tool öffnen**](https://DEIN-USERNAME.github.io/pokerabend-tool/)

*(Link anpassen, sobald GitHub Pages eingerichtet ist — siehe unten.)*

## Was das Tool macht

* **Starthand wählen**: 13×13-Raster mit allen 169 Starthand-Kombinationen (Paare, suited, offsuit).
* **Echte Simulation statt Tabelle**: Die Gewinnchance wird per Monte-Carlo-Simulation mit einem vollständigen 7-Karten-Hand-Evaluator berechnet — nicht aus einer vorgefertigten Tabelle abgelesen.
* **Flop / Turn / River austeilen**: Karten werden nacheinander aufgedeckt, die Equity wird nach jedem Schritt neu berechnet — die bereits ausgeteilten Karten bleiben dabei fix.
* **Gegneranzahl \& Position einstellbar**: Equity gegen 1–8 zufällige Gegnerhände, plus eine grobe, positionsbasierte Handlungsempfehlung (UTG bis BB, jeweils mit Erklärung).
* **Pot-Odds-Rechner**: Optionales Feld für Pot-Größe und Einsatz, relevant für die Big-Blind-Verteidigung.
* **Handtipps**: Kurze, kategoriebasierte Tipps zur gewählten Starthand (Premium-Pärchen, suited Connector, Ass-x usw.).

## Einordnung — was das Tool nicht ist

* Die Simulation rechnet gegen **zufällige** Gegnerhände, nicht gegen realistische Ranges. Das ist reine Kartenwahrscheinlichkeit, keine Range-Equity wie bei einem GTO-Solver (z. B. PioSolver, GTO Wizard).
* Die Handlungsempfehlung ist eine einfache Faustregel-Heuristik nach Position, kein Solver-Ergebnis. Sie berücksichtigt weder Stack-Tiefe noch Tischdynamik noch echtes Postflop-Spiel.
* Gedacht zum **Trainieren zuhause**, nicht als Live-Hilfe am Tisch — Equity-Software während des Spiels ist an so gut wie jedem Tisch ohnehin nicht erlaubt.

## Für die Gruppe hosten (GitHub Pages)

Falls der Link oben noch nicht funktioniert oder das Tool an einem neuen Ort liegen soll:

1. Neues Repository auf GitHub anlegen (**Public**).
2. Die Datei `poker\_equity\_trainer.html` hochladen und dabei in **`index.html`** umbenennen.
3. Unter **Settings → Pages** als Quelle den `main`-Branch, Ordner `/ (root)` auswählen und speichern.
4. Nach ca. 1 Minute ist die Seite live unter `https://github.com/TWeilandLPZ/pokerabend-tool/settings/pages`.
5. Diesen Link in die Gruppe schicken.

## Update

Um eine neue Version zu veröffentlichen: einfach die `index.html` im Repository durch die aktualisierte Datei ersetzen (Upload → gleicher Dateiname → Commit). Der Link bleibt gleich, nur der Inhalt ändert sich.

## Technik (für Interessierte)

Eine einzige HTML-Datei, kein Framework, kein Build-Schritt. Die Handbewertung läuft vollständig client-seitig in JavaScript (Poker-Hand-Evaluator + Monte-Carlo-Simulation über alle 21 möglichen 5-aus-7-Kartenkombinationen). Es werden keine Daten irgendwohin gesendet — alles passiert lokal im Browser der Person, die die Seite öffnet.

