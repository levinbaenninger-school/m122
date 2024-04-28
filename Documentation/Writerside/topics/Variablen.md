# Variablen

In Bash werden Variablen ohne Datentyp deklariert:

````Bash
number=10
string="Bash ist toll!"
````

Dabei hat Bash einen Grundsatz: Wenn wir eine Variable **schreiben** nutzen wir einfach den **Namen der Variablen** und wenn wir eine Variable **lesen**, müssen wir ein **`$`-Zeichen** voranstellen:

````Bash
number=10
echo "Meine Zahl lautet $number"
````

## Rechnen mit Variablen

Um mit Variablen zu Rechnen brauchen wir `$(())`:

````Bash
calculation=$((number + 10))
echo "Meine Zahl lautet $((number + 5))"
````

> **Wichtig:** Bash kann keine Kommarechnung ausführen!

{ style="warning" }