# Skripte

Jedes Skript braucht am Anfang die sogenannte **Shebang-Zeile**. Diese Zeile bestimmt den Interpreter. Um den Pfad des Bash-Interpreters herauszufinden, machen wir Folgendes:

````Bash
echo $SHELL
````

Mit diesem Befehl bekommen wir den Pfad von Bash und können diesen nun in unserem Skript einbinden:

````Bash
#!/bin/bash
# Shebang-Zeile
# Autor: Levin Bänninger
# Datum: 19.3.2024
# Aufgabe: Erstes Skript

...
````

Wie wir sehen lautet die Shebang-Zeile `#!/bin/bash`. Ausserdem sehen wir, dass wir Kommentare mit einem `#` erstellen können.

## Ausgabe

Um bspw. Text im Terminal auszugeben nutzen wir den Befehl `echo`:

````Bash
echo Ich bin ein Skript!
echo Hallo, mein Name ist: $(whoami)
````

Soll das Resultat eines Kommandos ausgegeben werden, so benötigt man zusätzlich `$()`.

### Optionen

Wenn Escape-Sequenzen verarbeitet werden sollen, dann kann man den Schalter `-e` nutzen.

## Eingabe

Mit dem Befehl `read` können wir Nutzereingaben in einer Variable speichern:

````Bash
read -p $'Bitte eine Zahl eingeben: \n' number
echo $number
````

Hierbei wird der Text `Bitte eine Zahl eingeben: ` mit einem Zeilenumbruch dargestellt. Falls wir keinen Zeilenumbruch benötigen, reicht es die Aufforderung in `""` zu schreiben.

Die Eingabe wir in der Variablen `number` gespeichert, diese muss vorher nicht zwingend erstellt worden sein.