Intro Versionierung mit Git/GitHub für non-developer
==============================

Einführung in die Versionierung von textbasierten Files mittels Git und GitHub auf der Semantic Media Wiki Conference am 1. Oktober 2014 in Wien.

Zu Beginn gab es eine kleine Einführung in Software-Versionierung, Git und Github, bevor dann praktisch mit Git und GitHub Daten und Textfiles (Dokumentation) verwaltet wurde.

## EINFÜHRUNG
Ordner erstellen.
```shell
mkdir presentation
cd presentation
```

### REPO ERSTELLEN
Git Repository erstellen.
```shell
git init
git status
```
.git Ordner ansehen
Datei erstellen
```shell
touch profil.txt
git status
```

### DATEIEN HINZUFÜGEN
Datei stagen für commit.
```shell
git add profil.txt
git status
```
Datei unstagen.
```shell
git reset
git status
```
Datei aus Repository entfernen.
```shell
git rm --cached profil.txt
git add profil.txt
git status
```

### DATEIEN COMMITEN
Ein Commit ist das Erstellen eines statischen Punktes im Repository. Dieser kann immer wieder hergestellt und abgerufen werden.
```shell
git commit -m"create profil.txt"
git status
git log 
```

### DATEI LÖSCHEN
Datei aus Repository und Filesystem löschen.
```shell
git rm profil.txt
git status
```

### HISTORY ABWANDERN
Zwischen Commits hin und herspringen.
```shell
git checkout <COMMITHASH>
git checkout master
```

### DIFF ANSEHEN
Neue Datei erstellen und hinzufügen.
```shell
touch data.csv
git add data.csv
git commit -m"create data.csv"
```
Neue Zeilen zu Datei hinzufügen.
EDIT csv
```shell
git add data.csv
git commit -m"edit data.csv"
git status
```
EDIT csv
Änderungen in Files ansehen.
```shell
git diff --unstaged data.csv
git commit -m"update data.csv"
git status
git log
git lol
```

### ÄNDERUNGEN RÜCKGÄNGIG MACHEN
EDIT csv
Zustand der File vom HEAD wiederherstellen, also alle Änderungen verwerfen.
```shell
git reset HEAD data.csv
git checkout -- data.csv
git status
```

### BRANCHEN
Branches ansehen.
```shell
git branch -v
devel Branch erstellen.
git branch devel
git branch -v
git status
```
COPY geojson
```shell
git status
```
GeoJSON File hinzufügen.
```shell
git add map.geojson
git commit -m"add map.geojson"
```
Branch wechseln -> master
```shell
git checkout master
git status
```
### MERGEN
EDIT csv
Änderungen hinzufügen
```shell
git add data.csv
git commit -m"add banker to data.csv"
git status
```
master-Branch mit devel-Branch mergen.
```shell
git merge devel
git checkout devel
git lol
```

### REPO AUF GITHUB ERSTELLEN
Remote-Connections ansehen.
```shell
git remote -v
```
REPO erstellen
Remote erstellen.
```shell
git remote add origin XXXX
git remote -v
git status
```

### REPO UPLOAD
Lokales Repository auf GitHub laden.
```shell
git pull origin master
```

### REPO DOWNLOAD
GitHub-Repository auf Rechner runter ziehen.
```shell
git clone <REPOURL>
```

### REPO UPDATE
Lokales Repository mit dem ursprünglichen GitHub Repository aktualisieren (abgleichen).
```shell
git fetch 
```

### Weiteres
Hilfe:
```shell
git help
```

## Quellen
- [git](http://git-scm.com/)
- [GitHub](https://github.com)
- [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown)
- [Buch: Pro Git](http://git-scm.com/book/de)

## FAQ
### Wie oft soll man commiten?
**Nach jeder relevanten Änderung bzw. wenn ein Block abgeschlossen ist.**
### Was schreibt man in die Commit-Message?
**Möglichst genau, was gemacht wurde, ohne einen Roman zu verfassen. Es geht darum, im nachhinein noch nachvollziehen zu können, was sich durch den Commit verändert hat. Sprachlich wird Englisch und Präsenz empfohlen.**



