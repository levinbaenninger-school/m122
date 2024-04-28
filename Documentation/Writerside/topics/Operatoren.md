# Vergleichsoperatoren

Vergleichsoperatoren sind ein wichtiger Bestandteil für Verzweigungen und Loops.

## Operatoren für Zahlen

| Ausdruck              | Bedeutung             |
|-----------------------|-----------------------|
| `"$num1" -eq "$num2"` | equals                |
| `"$num1" -ne "$num2"` | not equals            |
| `"$num1" -lt "$num2"` | less than             |
| `"$num1" -gt "$num2"` | greater than          |
| `"$num1" -le "$num2"` | less than or equal    |
| `"$num1" -ge "$num2"` | greater than or equal |

## Operatoren für Strings

| Ausdruck             | Wahr, wenn ...                 |
|----------------------|--------------------------------|
| `"$str1" = "$str2"`  | `str1` gleich `str2` ist       |
| `"$str1" != "$str2"` | `str1` nicht gleich `str2` ist |
| `-z "$str"`          | `str` leer ist                 |
| `-n "$str"`          | `str` nicht leer ist           |

## Operatoren für Dateien

| Operator     | Bedeutung                                     |
|--------------|-----------------------------------------------|
| `-d "$file"` | Datei existiert und ist ein Verzeichnis       |
| `-f "$file"` | Datei existiert und ist eine reguläre Datei   |
| `-h "$file"` | Datei existiert und ist ein symbolischer Link |
| `-L "$file"` | Datei existiert und ist ein symbolischer Link |
| `-e "$file"` | Datei existiert                               |
| `-s "$file"` | Datei existiert und ist nicht leer            |

## Operatoren für Rechte

| Operator     | Bedeutung                                                                   |
|--------------|-----------------------------------------------------------------------------|
| `-r "$file"` | Datei existiert und ist lesbar                                              |
| `-w "$file"` | Datei existiert und ist beschreibbar                                        |
| `-x "$file"` | Datei existiert und ist ausführbar                                          |
| `-O "$file"` | Datei existiert und Benutzer des Skriptes ist Owner der Datei               |
| `-G "$file"` | Datei existiert und der Benutzer des Skripts hat dieselbe GID wie die Datei |

## Beispiel

````Bash
!/bin/bash

file="$1"

# Überprüfe, ob ein Parameter angegeben wurde
if [ $# -lt 1 ]; then
    echo "Bitte geben Sie den Namen einer Datei als Parameter ein."
    exit 1
fi

# Überprüfe, ob die Datei existiert
if [ ! -e "$file" ]; then
    echo "Die angegebene Datei existiert nicht!"
    exit 1
fi

# Überprüfe, ob es sich um eine reguläre Datei handelt
if [ -f "$file" ]; then
    cp "$file" /tmp
    echo "Datei wurde nach /tmp kopiert. Inhalt von /tmp:"
    ls /tmp
elif [ -d "$file" ]; then
    echo "Die angegebene Datei ist ein Verzeichnis."
fi
````



