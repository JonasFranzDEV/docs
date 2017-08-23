---
date: "2017-08-23T16:00:00+02:00"
title: "Basteln mit Gitea"
slug: "hacking-on-gitea"
weight: 10
toc: false
draft: false
menu:
  sidebar:
    parent: "advanced"
    name: "Basteln mit Gitea"
    weight: 10
    identifier: "hacking-on-gitea"
---

# Basteln mit Gitea

Wir werden in dieser Anleitung nicht die Basis des Golang-Setups thematisieren. Wenn du nicht weißt, wie du die Golang-Umgebung aufsetzten kannst, schaue dir die [offizielle Anleitung](https://golang.org/doc/install) an.

Wenn du zu Gitea beitragen möchtest, solltest du einen Fork des Projektes anlegen und auf der `master`-Branch arbeiten. Da Gitea eine andere URL als die GitHub-Clone-URL verwendet, müssen wir Go ein wenig austricksen. Dafür starten wir mit dem Download von Gitea:

```
go get -d code.gitea.io/gitea
```

Nun ist es Zeit einen Fork der [Gitea-Repository](https://github.com/go-gitea/gitea) auf GitHub zu erstellen, dannach musst du in der Kommandozeile zum Gitea-Quellcode-Ordner navigieren:

```
cd $GOPATH/src/code.gitea.io/gitea
```
Um eine Pull-Request erstellen zu können, solltest du deine geforkte Repository als `remote` hinzufügen. Andernfalls kannst du nichts am Quellcode ändern, da du keine Schreibberechtigungen für das Gitea-Projekt hast:

```
git remote rename origin upstream
git remote add origin git@github.com:<USERNAME>/gitea.git
git fetch --all --prune
```
Nun hast du eine funktionierende Entwicklungsumgebung für Gitea. Schau dir die `Makefile` an, um einen Überblick der verfügbaren Tasks zu bekommen. 
Der `make test`-Task führt dabei automatisierte Tests aus, und der `make build`-Task baut eine ausführbare `gitea`-Binärdatei.
Du musst keine automatiserten Tests schreiben, aber wir würden uns freuen, welche zu sehen.

Das war's! Du bist nun bereit mit Gitea herumzubasteln. Teste deine Änderungen, Push diese in deine Repository und eröffne eine Pull-Request!
