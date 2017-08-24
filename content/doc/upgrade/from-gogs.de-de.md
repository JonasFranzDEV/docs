---
date: "2017-08-24T16:00:00+02:00"
title: "Von Gogs zu Gitea wechseln"
slug: "upgrade-from-gogs"
weight: 10
toc: true
draft: false
menu:
  sidebar:
    parent: "upgrade"
    name: "Von Gogs zu Gitea wechseln"
    weight: 10
    identifier: "upgrade-from-gogs"
---

# Von Gogs zu Gitea wechseln

Gogs bis zur Version 0.9.146 (DB-Schema Version 15) kann ohne Probleme zu Gitea gewechselt werden.

Du musst zum wechseln die unteren Schritte durchführen. Bitte führe die Schritte mit dem Gitea-Benutzer aus, wenn du UNIX benutzt.

* Erstelle ein Gogs-Backup mit `gogs dump`. Dies erstellt die `gogs-dump-[timestamp].zip`-Datei, die alle benötigten Daten von Gogs enthält.
* Lade dir die Datei, die zu deinem Betriebsystem passt von der [Download-Seite](https://dl.gitea.io/gitea) runter.
* Verschiebe die Installationsdatei in den gewünschten Installationsordner.
* Kopiere `gogs/custom/conf/app.ini` in deinen Installationsordner unter `gitea/custom/conf/app.ini`.
* Wenn du angepasste Templates etc. im `gogs/custom/` hast, kopiere diese in den entsprechenden `gitea/custom/`-Ordner. 
* Falls weitere Ordner mit benutzerdefinierten Inhalt existieren wie `gitignore, label, license, locale, readme`, kopiere diese ebenfalls in den `gitea/custom/options`-Ordner.
* Kopiere `gogs/data/` zu `gitea/data/`. Dieser Ordner beinhaltet die Profilbilder und Anhänge.
* Überprüfe, ob Gitea startet mit `gitea web`.
* Führe im "Administration[s]"-Bereich die Aktion Datei `'.ssh/Authorized_keys' neuschreiben (für Gitea SSH-Schlüssel)` aus.

### Weitere Gogs-bezogene Änderungen
* Benenne `gogs-repositories/` zu `gitea-repositories/` um
* Benenne `gogs-data/` zu `gitea-data/` um
* Ändere in deiner `gitea/custom/conf/app.ini`-Datei:

ALTE VERSION:
```
[database]
PATH = /home/:USER/gogs/data/:DATABASE.db
[attachment]
PATH = /home/:USER/gogs-data/attachments
[picture]
AVATAR_UPLOAD_PATH = /home/:USER/gogs-data/avatars
[log]
ROOT_PATH = /home/:USER/gogs/log
```

NEUE VERSION:
```
[database]
PATH = /home/:USER/gitea/data/:DATABASE.db
[attachment]
PATH = /home/:USER/gitea-data/attachments
[picture]
AVATAR_UPLOAD_PATH = /home/:USER/gitea-data/avatars
[log]
ROOT_PATH = /home/:USER/gitea/log
```

* Überprüfe, ob Gitea startet mit `gitea web`

### Fehlerbehebung

* Wenn Fehler bezüglich angepasster Templates (`gitea/custom/templates`) auftreten, versuche die einzelnen Templates nacheinander zu entfernen, um zu sehen welches den Fehler auslöst. Es kann sein,
dass diese nicht zu Gitea kompatibel sind.

### Autostart für Gitea einrichten (UNIX)

Aktualisiere die einzelnen Datei aus  [gitea/contrib](https://github.com/go-gitea/gitea/tree/master/contrib) mit den richtigen Umgebungsvariabeln.

Für systemd-Systeme (z.B. Debian 8):

* Übertrage das aktualiserte Script in `/etc/systemd/system/gitea.service`
* Füge den Service zum Autostart hinzu via `sudo systemctl enable gitea`
* Deaktiviere den Gogs-Autostart-Service via: `sudo systemctl disable gogs`

Für SysVinit-Systeme (z.B. Debian 7):

* Übertrage das neue Gitea-Skript in `/etc/init.d/gitea`
* Füge den Service zum Autostart hinzu via `sudo rc-update add gitea`
* Deaktiviere den Gogs-Autostart-Service via: `sudo rc-update del gogs`
