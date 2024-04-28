# Parameter

Wir können beim Aufruf unseres Skripts noch Argumente mitgeben:

````Bash
./parameter.sh -a "Es sind" 5 Parameter vorhanden
````

Diese Argumente können wir in unserem Skript mit `$1`, `$2` bis `$n` ansprechen und nutzen. Zum Beispiel:

````Bash
if [ $# -eq 0 ]; then
	read -p $'Von welcher Zahl möchten Sie den Kubikwert errechnen?\n' basis
	echo "$basis hoch 3 = $((basis * basis * basis))"
elif [[ $# -eq 1 ]]; then
	echo "$1 hoch 3 = $(($1 * $1 * $1))"
else 
	echo "Sie haben zu viele Parameter eingeben! - Abbruch"
fi
````

Hier benutzen wir noch spezielle Parametervariablen:

- `$#` - Anzahl der mitgegebenen Argumente
- `$*` - Alle Argumente in einer Zeichenkette