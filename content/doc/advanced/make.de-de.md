---
date: "2017-08-23T16:00:00+02:00"
title: "Make"
slug: "make"
weight: 10
toc: true
draft: false
menu:
  sidebar:
    parent: "advanced"
    name: "Make"
    weight: 30
    identifier: "make"
---

# Make

Gitea nutzt Make für automatisierte Aufgaben und schnellere Entwicklung. Diese Anleitung erklärt, wie man Make installiert.

### Unter Linux

Du kannst Make über deine Paketverwaltung installieren.

Unter Ubuntu/Debian:

```bash
sudo apt-get install build-essential
```

Unter Fedora/RHEL/CentOS:

```bash
sudo yum install make
```

### Unter  Windows

Wenn du Windos benutzt, kann du einer dieser Make-Varianten herunterladen:

- [Single binary build](http://www.equation.com/servlet/equation.cmd?fa=make). Kopiere es irgendwo hin und füge es zum `PATH` hinzu.
  - [32-bits Version](ftp://ftp.equation.com/make/32/make.exe)
  - [64-bits Version](ftp://ftp.equation.com/make/64/make.exe)
- [MinGW](http://www.mingw.org/) enhält make. Die Datei heißt `mingw32-make.exe` anstatt `make.exe`. Füge den `bin`-Ordner zum `PATH` hinzu.
- [Chocolatey package](https://chocolatey.org/packages/make). Führe `choco install make` aus.
