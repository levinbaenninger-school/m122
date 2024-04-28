# Verzweigungen

Verzweigungen sind ein wichtiger Bestandteil von jedem Skript.

## if-Verzweigung

`if`-Verzweigungen funktionieren exakt gleich, wie bei bekannten Programmiersprachen, wie C oder JavaScript, jedoch mit einer abgeänderten Syntax:

````Bash
if [ $x -eq 10 ]; then
    echo x ist 10
fi
````

Die Bedingung wird also in eckige Klammern `[]` gesetzt; die Bedingung wird mit einem Semikolon `;` beendet. Danach kommt das `then`-Keyword, welches den Beginn unserer Aktion zeigt. Zum Schluss kommt das `fi`-Keyword zum Zug, das Bash zeigt, dass die `if`-Verzweigung zu Ende ist.

### elif und else

````Bash
if [ $x -eq 10 ]; then
    echo x ist 10
elif [ $x -eq 20 ]; then
    echo x ist 20
else
    echo x ist weder 10 noch 20
fi
````

## case-Verzweigung

Natürlich gibt es auch die `case`-Verzweigung besser bekannt als `switch` in Bash:

````Bash
read -p $'Enter the name of a country:\n' country

echo -n "The official language of $country is "

case "$country" in
  Lithuania)
    echo -n "Lithuanian";;
    
  Romania | Moldova)
    echo -n "Romanian"  ;;

  Italy | "San Marino" | Switzerland | "Vatican City")
    echo -n "Italian"   ;;

  *)
    echo -n "unknown"  
esac
````
