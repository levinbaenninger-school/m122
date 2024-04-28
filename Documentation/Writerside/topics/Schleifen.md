# Schleifen

In Bash gibt es sowohl die `for`-Schleife, als auch die `while`-Schleife.

## for-Schleife

Die Syntax ist fast genau gleich, wie bei allen C-ähnlichen Sprachen:

````Bash
for((i=5; i>0; i--))
do
   echo $i
   sleep 1   # Eine Sekunde anhalten
done
````

### Arrays

Wir können natürlich auch durch Arrays loopen; das geht in Bash mit `for ... in ...`:

````Bash
for file in "$@"
do
    if [ -f "$file" ]; then
        echo "$file: regular file"
    elif [ -d "$file" ]; then
        echo "$file: directory"
    else
        echo "$file: does not exist"
    fi
done
````

## while-Schleife

Die `while`-Schleife ist vor allem dann nützlich, wenn wir mögliche falsche Nutzereingaben abfangen müssen:

````Bash
action=0

while [ "$action" -ne 5 ]
do
	echo $'\n+---------Menu----------+'
	echo "| -1- Backup Scripts    |"
	echo "| -2- Ping Google       |"
	echo "| -3- Print Diskusage   |"
	echo "| -4- Clear /tmp Folder |"
	echo "| -5- Quit              |"
	echo "+-----------------------+"

	read -p $'\nPlease make a choice: ' action

	case "$action" in
		1) tar cfvz scripts_$(date +%d.%m.%y_%H.%M.%S).tar.gz *.sh ;;
		2) ping google.ch -c 4 ;;
		3) du -sh /* 2> /dev/null | sort -hr ;;
		4) rm -ri /tmp/* ;;
		5) exit 0 ;;
		*) echo "Invalid choice"
	esac
done
````

{ ignore-vars="true" }

Wie wir sehen ist die Syntax der `while`-Schleife anders, als die der `for`-Schleife.