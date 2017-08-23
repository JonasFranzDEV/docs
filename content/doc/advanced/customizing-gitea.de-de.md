---
date: "2017-08-23T16:00:00+02:00"
title: "Gitea anpassen"
slug: "customizing-gitea"
weight: 9
toc: false
draft: false
menu:
  sidebar:
    parent: "advanced"
    name: "Gitea anpassen"
    weight: 9
    identifier: "customizing-gitea"
---

# Gitea anpassen

Gitea lässt sich primär über den `custom`-Ordner anpassen. Dies ist der zentrale Ort, um Eigenschaften zu ändern.

Wenn du Gitea über die ausführbare Datei installiert hast, findest du den `custom`-Ordner im Ordner der ausführbaren Datei.

Gitea erstellt diesen Ordner für dich und fügt zu Beginn den `conf`-Ordner hinzu, indem die während der Installation erstellte Konfiguration platziert wird. ([Beispielhafte vollständige Konfigurationsdatei](https://docs.gitea.io/en-us/config-cheat-sheet/))

Wenn du den `custom`-Ordner nicht finden kannst, überprüfe bitte die `GITEA_CUSTOM`-Umgebungsvariable, die dazu genutzt werden kann, um den Pfad des Ordners zu verändern.

**Beachte**, dass Gitea neugestartet werden muss, bevor die Änderungen übernommen werden.

## /robots.txt anpassen

Um Gitea deine eigene `/robots.txt` verwenden zu lassen (Standartmäßig wird Status 404 zurückgegeben), erstelle einfach eine `/robots.txt`-Datei in dem `custom`-Ordner.

## Eigene Dateien im Webserver bereitstellen

Um Gitea eigene, öffentliche Dateien bereitstellen zu lassen (wie Seiten oder Bilder), benutze den Ordner `custom/public/` als Webroot. Verknüpfungen werden gefolgt.

Zum Beispiel wird die Datei `image.png` im Ordner `custom/public` unter `http://your-gitea-url/image.png` bereitgestellt.

## Standart-Profilbild ändern

Platziere eine PNG-Bild unter folgendem Pfad: `custom/public/img/avatar_default.png`

## Gitea-Seiten anpassen

Der `custom/templates`-Ordner erlaubt es dir jede einzelne Gitea-Seite zu ändern.

Du musst dich mit Templates auskennen, um Änderungen durchzuführen. Alle Templates können im `templates`-Ordner des Gitea-Quellcodes gefunden werden.

Wenn du die passende .tmpl-Datei gefunden hast, kannst du diese in den `custom/templates`-Ordner kopieren. __Übernehme__ die Unterordner aus dem Quellcode.

Du kannst nun die Templates, die du kopiert hast nach deinen Wünschen anpassen. Sei aber Vorsichtig, dass du nichts kaputt machst!

Alle Textstellen, die durch `{{` und `}}` ummantelt werden, beinhalten Gitea-Syntax, welchen du nicht ändern solltest, außer du weißt, was du tust.

## gitignores, Labels, Lizenzen, Übersetzungen und Readmes anpassen

Platziere die Datei in dem jeweiligen Unterordner unter `custom/options`.
