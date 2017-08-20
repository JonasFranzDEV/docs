---
date: "2017-08-23T16:00:00+02:00"
title: "Dokumentation"
slug: "documentation"
weight: 10
toc: true
draft: false
---

# Was ist Gitea?

Gitea ist einfacher, selbstgehosteter Git-Service. Ähnlich wie GitHub, Bitbucket oder GitLab. Gitea ist eine Absplatung ("Fork") des [Gogs](http://gogs.io)-Projektes. 
Gründe für die Abspaltung können Sie in diesem [diesem](https://blog.gitea.io/2016/12/welcome-to-gitea/) Blog-Eintrag finden.

## Ziel

Das Ziel dieses Projektes ist es, einen einfachen, schnellen und schmerzfreien Weg zu einem selbstgehosteten Git-Service zu erschaffen. Go bietet dabei die Möglichkeit, Gitea auf allen Platformen, die Go unterstützen, einzusetzen wie Linux, macOS und Windows, sogar auch Architekturen wie ARM oder PowerPC.

## Features

- Benutzer-Übersichtsseite
    - Kontext-Wechsler (aus Sicht des Nutzers oder der Organisation)
    - Aktivitätsliste
        - Commits
        - Issues
        - Pull-Requests
        - Erstellung von Repository
    - Durchsuchbare Repository-Liste
    - Liste der Organisationen
    - Liste der Mirror-Repositories
- Issues-Übersicht
    - Kontext-Wechsler (aus Sicht des Nutzers oder der Organisation)
    - Filtern nach
        - Offen
        - Geschlossen
        - Eigene Repositories
        - Dir zugewiesen
        - Deine issues
        - Repository
    - Sortierbar nach
        - Älteste
        - Zuletzt aktualisiert
        - Anzahl der Kommentare
- Pull-Request Übersicht
    - Siehe Issues-Übersicht
- Repository-Typen
    - Mirror
    - Normal
    - Migriert
- Benachrichtigungen (E-Mail und Web)
    - Gelsenen
    - Ungelsen
    - Angepinnt
- Erkunden
    - Benutzer
    - Repositories
    - Organisationen
    - Suche
- Benutzerdefinierte templates
- Überschreibbare Web-Dateien (Logo, CSS, etc.)
- CSRF- und XSS-Schutz
- HTTPS-Unterstützung
- Beschränkbare Upload-Dateigrößen und -typen
- Logging
- Konfiguration
    - Datenbanken
        - MySQL
        - PostgreSQL
        - SQLite3
        - MSSQL
        - [TiDB](https://github.com/pingcap/tidb) (experimentel)
    - Konfigurations-Datei
        - Siehe [hier](https://github.com/go-gitea/gitea/blob/master/conf/app.ini)
    - Administrations-Bereich
        - Statistiken
        - Aktionen
            - Löschung inaktiver Benutzer
            - Löschung zwischengespeicherter Repository-Archive
            - Löschung von Repositories, deren Datei gelöscht worden sind
            - Aufräumen der Repositories (garbage collection)
            - Regenerierung der SSH-Schlüssel
            - Resynchronisierung der hooks
            - Fehlende Repositories erneut erstellen
        - Server-Status
            - Laufzeit
            - Arbeitsspeicher
            - Anzahl der goroutines
            - ...
        - Benutzerverwaltung
            - Suche
            - Sortieren
            - Letzte Anmeldung
            - Authentifizierungsquellen
            - Maximale Anzahl der Repositories
            - Benutzerkonten deaktivieren
            - Berechtigungen verwalten
        - Organisationsverwaltung
            - Mitglieder
            - Teams
            - Logo / Avatar
            - Hooks
        - Repositoryverwaltung
            - Alle Repository-Informationen sehen und verwalten
        - Authentifizierungsquellen
            - OAuth (z.B. GitHub, Google+, Facebook)
            - PAM
            - LDAP
            - SMTP
        - Anzeigen der Konfigurationsdatei
        - System-Mitteilungen
            - Wenn etwas Unerwartetes geschieht
        - Überwachung
            - Aktueller Prozess
            - Cron jobs
                - Mirrors aktualisieren
                - Repository-Status-Check
                - Repository-Statistik-Check
                - Aufräumen der alten Archiven
    - Umgebungsvariablen
    - Command-Line-Optionen
- Mehrsprachig ([21 Sprachen](https://github.com/go-gitea/gitea/tree/master/options/locale))
- E-Mail
    - Benachrichtigungen
    - Registrierungs-Bestätigung
    - Passwort-Reset
- Reverse-Proxy-Unterstützung
    - Inklusive subpaths
- Benutzer
    - Profil
        - Name
        - Benutzername
        - E-Mail
        - Webseite
        - Beitritsdatum
        - Followers und following
        - Organisationen
        - Repositories
        - Aktivität
        - Geteilte Repositories
    - Einstellungen
        - Siehe Profil
        - E-Mail-Adresse verstecken
        - Avatar
            - Gravatar
            - Libravatar
            - Benutzerdefiniert
        - Passwort
        - Mehrere E-Mail-Adressen
        - SSH-Schlüssel
        - Verbundene Anwendungen
        - Zwei-Faktor-Authentifizierung
        - Verlinkte OAuth2-Quellen
        - Account löschen
- Repositories
    - Klonen via SSH/HTTP/HTTPS
    - Git LFS
    - Watch, Star, Fork
    - Sehe watchers, stars, and forks
    - Code
        - Branch-Übersicht
        - Datei hochladen oder aktualisieren in der Web-Oberfläche
        - Clone-URLs
        - Download
            - ZIP
            - TAR.GZ
        - Web-basierter Editor
            - Markdown-Editor
            - Text-Editor
                - Syntax-Highlighting
            - Diff-Vorschau
            - Vorschau
            - Auswahl des Commit-Ziels
        - Datei-Historie anschauen
        - Datei löschen
        - Nur Dateiinhalt anzeigen
    - Issues
        - Issue-Templates
        - Meilesteine
        - Labels
        - Issues zuweisen
        - Filter
            - Offen
            - Geschlossen
            - Zugewiesene Person
            - Selbst erstellt
            - Erwähnt Dich
        - Sortieren
            - Ältestes
            - Zuletzt aktualisiertes
            - Anzahl der Kommentare
        - Suche
        - Kommentare
        - Anhänge
    - Pull-Requests
        - Siehe Issues
    - Commits
        - Commit-Graph
        - Commits an Hand der Branch
        - Suche
        - Suche in allen Branches
        - Diff anzeigen
        - SHA anzeigen
        - Autor anzeigen
        - Dateien im Commit durchsuchen
    - Releases
        - Anhänge
        - Titel
        - Inhalt
        - Löschen
        - Als "Pre-Release" makieren
        - Branch auswählen
    - Wiki
        - Importieren
        - Markdown-Editor
    - Einstellungen
        - Optionen
            - Name
            - Beschreibung
            - Privat/Öffentlich
            - Webseite
            - Wiki
                - Aktivieren / Deaktivieren
                - Intern / Extern
            - Issues
                - Aktivieren / Deaktivieren
                - Intern / Extern
            - Pull-Requests aktivieren / deaktiveren
            - Besitzer der Repository ändern
            - Wiki löschen
            - Repository löschen
        - Zusammenarbeit
            - Lesen/Schreiben/Administrator
        - Branches
            - Standart-Branch
            - Branch-Protection
        - Webhooks
        - Git-Hooks
        - Deploy-Schlüssel

## Systemanforderungen

- Ein günstiger Raspberry Pi hat genug Leistung für die essentiellen Funktionen
- Zwei CPU-Kerne und 1GB RAM sind die Mindestanforderungen für den Einsatz im Team.
- Gitea sollte mit einem nicht-root Nutzer auf UNIX-Systemen laufen. Das Ausführen als Root-Benutzer wird **nicht** unterstützt. (**HINWEIS**: Im Fall, dass du Gitea mit deinem eigenen Benutzer läuft und der eingebaute SSH-Server deaktiviert ist, modifiziert Gitea die  `~/.ssh/authorized_keys`-Datei, was bewirkt, dass du dich **nicht** mehr mit deinem SSH-Schlüssel **anmelden** kannst!)

## Browser-Unterstützung

- Siehe [Semantic UI](https://github.com/Semantic-Org/Semantic-UI#browser-support) for specific versions of supported browsers.
- Die offiziel Unterstützte Mindestsauflösung ist **1024*768**, die Benutzeroberfläche kann aber auch bei kleineren Auflösungen nutzbar sein, dafür gibtes aber keine Garantie!

## Komponenten

* Web-Framework: [Macaron](http://go-macaron.com/)
* ORM: [XORM](https://github.com/go-xorm/xorm)
* Komponeten der Benutzeroberfläche:
  * [Semantic UI](http://semantic-ui.com/)
  * [GitHub Octicons](https://octicons.github.com/)
  * [Font Awesome](http://fontawesome.io/)
  * [DropzoneJS](http://www.dropzonejs.com/)
  * [Highlight](https://highlightjs.org/)
  * [Clipboard](https://zenorocha.github.io/clipboard.js/)
  * [Emojify](https://github.com/Ranks/emojify.js)
  * [CodeMirror](https://codemirror.net/)
  * [jQuery Date Time Picker](https://github.com/xdan/datetimepicker)
  * [jQuery MiniColors](https://github.com/claviska/jquery-minicolors)
* Datenbank-Treiber:
  * [github.com/go-sql-driver/mysql](https://github.com/go-sql-driver/mysql)
  * [github.com/lib/pq](https://github.com/lib/pq)
  * [github.com/mattn/go-sqlite3](https://github.com/mattn/go-sqlite3)
  * [github.com/pingcap/tidb](https://github.com/pingcap/tidb)
  * [github.com/denisenkom/go-mssqldb](https://github.com/denisenkom/go-mssqldb)

## Unterstützte Software und Dienste

- [Drone](https://github.com/drone/drone) (CI)
