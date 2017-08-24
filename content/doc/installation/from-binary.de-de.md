---
date: "2017-08-24T16:00:00+02:00"
title: "via Installationsdatei"
slug: "install-from-binary"
weight: 10
toc: true
draft: false
menu:
  sidebar:
    parent: "installation"
    name: "via Installationsdatei"
    weight: 20
    identifier: "install-from-binary"
---

# Installation via Installationsdatei

Alle Downloads unterstützen SQLite, MySQL und PostgreSQL. Alle benötigten Dateien sind dabei enthalten. Dies kann für alte Versionen anders sein! Die Installation via Installationsdatei ist einfach. Du musst nur, die zu deiner Platform passende, Installationsdatei von der [Download-Seite](https://dl.gitea.io/gitea) wählen, und die untere URL  mit dem entsprechenden Link der Installationsdatei ersetzten:

```
wget -O gitea https://dl.gitea.io/gitea/1.0.1/gitea-1.0.1-linux-amd64
chmod +x gitea
```

## Test

Nachdem du die oberen Schritte befolgt hast, befindet sich nun in deinem Installationsordner die `gitea`-Datei (auch bekannt als "Installationsdatei").
Als erstes solltest du Testen, ob Gitea auch funktioniert. Dazu kannst du den unteren Befehl ausführen, der Gitea starten lässt. Du kannst dann Gitea auf der Adresse des ausführenden Rechner aufrufen. Mit `Ctrl + C` kannst du Gitea in der Kommandozeile wieder beenden.

```
./gitea web
```

## Fehlerbehebung

### Alte glibc-Versionen

Alte Linux-Distrubutionen (wie Debian 7 oder CentOS 6), können Gitea manchmal nicht starten, da die Fehlermeldung ```./gitea: /lib/x86_64-linux-gnu/libc.so.6: version `GLIBC_2.14' not found (required by ./gitea)``` auftritt. Dies geschieht auf Grund der Unterstützung von SQLite. In Zukunft werden wir Versionen, die glibc nicht mehr benötigen zur Verfügung stellen. In der Zwischenzeit, lässt sich Gitea aus [dem Quellcode aus installieren.]({{< relref "from-source.de-de.md" >}}

### Gitea auf einen anderen Port laufen lassen

Wenn du die Fehlermeldung `702 runWeb()] [E] Failed to start server: listen tcp 0.0.0.0:3000: bind: address already in use` erhälst, musst du Gitea auf einen anderen freien Port starten.

Die ist möglich, indem du `./gitea web -p $PORT` verwendest.

## Fehlt irgendetwas?

Wenn dir irgendetwas auf dieser Seite fehlt, kannst du dich über unseren [Discord-Server](https://discord.gg/NsatcWJ) an uns wenden. Dort werden deine Fragen recht schnell beantwortet.
