---
title: "Einstellungen"
description: ""
url: "system/einstellungen"
weight: 10
---

Die Systemeinstellungen verabschieden sich langsam aber sicher aus dem Backend. Grundlegende Systemeinstellungen
beeinflussen Contao als Applikation und somit besteht auch die Chance, dass durch eine falsche Einstellung das System
in einen funktionsuntüchtigen Zustand gebracht wird. Sollte dies geschehen, hast du keine Möglichkeit mehr,
die Einstellungen rückgängig zu machen und das System wiederherzustellen, da du dich nicht mehr einloggen kannst.
Aus diesem Grund werden die meisten Einstellungen außerhalb von Contao über die `config.yml` vorgenommen bzw. können 
zukünftig über den Contao Manager vorgenommen werden.

## Einstellungen

### Globale Einstellungen

**E-Mail-Adresse des Systemadministrators:** An diese Adresse werden z. B. Benachrichtigungen über gesperrte Konten 
oder neu registrierte Benutzer geschickt. Du kannst auch folgende Notation verwenden, um einen Namen zur E-Mail-Adresse 
hinzuzufügen:

```text
Kevin Jones [kevin.jones@example.com]
```

### Datum und Zeit

**Datums- und Zeitformat:** Alle Datums- und Zeitformate müssen wie in der 
[PHP-Funktion date](https://www.php.net/manual/de/function.date.php) eingegeben werden. Contao verarbeitet im Backend 
ausschließlich numerische Formate, also die Buchstaben j, d, m, n, y, Y, g, G, h, H, i und s.

Hier sind einige Beispiele gültiger Datums- und Zeitangaben:

| Angaben  | Erklärung                                                     |
|:---------|:--------------------------------------------------------------|
| Y-m-d    | JJJJ-MM-TT, international ISO-8601, z. B. `2005-01-28`        |
| m/d/Y    | MM/TT/JJJJ, Englisches Format, z. B. `01/28/2005`             |
| d.m.Y    | TT.MM.JJJJ, Deutsches Format, z. B. `28.01.2005`              |
| y-n-j    | JJ-M-T, ohne führende Nullen, z. B. `05-1-28`                 |
| Ymd      | JJJJMMTT, Zeitstempel, z. B. `20050128`                       |
| H:i:s    | 24 Stunden, Minuten und Sekunden, z. B. `20:36:59`            |
| g:i      | 12 Stunden ohne führende Nullen sowie Minuten, z. B. `8:36`   |

**Zeitzone:** Die Zeitzone solltest du unbedingt vor dem Erstellen deiner Webseite einstellen, da Contao alle 
Zeitangaben als [Unix-Zeitstempel](https://www.php.net/time) speichert und PHP diese Zeitstempel bei einer Änderung der 
Zeitzone nicht automatisch anpasst.


### Backend-Einstellungen

**Elemente nicht verkürzen:** Im »Parent View« stellt Contao die Elemente aus Gründen der Übersichtlichkeit verkürzt 
dar, wobei einzelne Elemente über ein Navigationsicon bei Bedarf ausgeklappt werden können. Wähle diese Option, um das 
Feature komplett zu deaktivieren.

**Elemente pro Seite:** Im Abschnitt [Datensätze auflisten](../../administrationsbereich/datensaetze-auflisten/#datensaetze-sortieren-und-filtern) 
hast du gelernt, dass Contao die Anzahl der Datensätze pro Seite standardmäßig auf 30 begrenzt. Diesen Wert kannst du 
hier beliebig anpassen. Höhere Werte bedeuten jedoch eine längere Ladezeit.

**Maximum Datensätze pro Seite:** Um zu verhindern, dass ein unbedarfter Benutzer sich 5000 Datensätze auf einmal 
anzeigen lässt und damit das PHP Memory Limit überschreitet, kannst du festlegen, wie viele Datensätze maximal pro Seite 
angezeigt werden dürfen.


### Frontend-Einstellungen

**Ordner-URLs verwenden:** Hier kannst du Ordnerstrukturen in Seitenaliasen aktivieren (z. B. 
`docs/install/download.html` anstatt `docs-install-download.html`).

**Leere URLs nicht umleiten:** Bei einer leeren URL die Webseite anzeigen anstatt auf den Startpunkt der Sprache 
weiterzuleiten _(nicht empfohlen)_.


### Sicherheitseinstellungen

**Anfrage-Tokens deaktivieren:** Hier kannst du aktivieren, dass die Anfrage-Token beim Absenden eines Formulars nicht 
geprüft werden _(unsicher!)_.

**Erlaubte HTML-Tags:** Standardmäßig erlaubt Contao keine HTML-Tags in Formularen und entfernt diese beim Speichern 
automatisch. Für Eingabefelder, bei denen die Nutzung von HTML erwünscht ist, kannst du hier eine Liste erlaubter 
HTML-Tags festlegen.


### Dateien und Bilder

**Erlaubte Download-Dateitypen:** Hier kannst du festlegen, welche Dateitypen von deinem Server heruntergeladen werden 
dürfen (Download).

**Maximale GD-Bildbreite**: Hier kannst du festlegen, wie breit Bilder und andere Medien im Frontend maximal sein 
dürfen. Bei einer Überschreitung dieses Werts wird das entsprechende Objekt automatisch verkleinert.

**Maximale GD-Bildhöhe**: Hier kannst du festlegen, wie hoch Bilder und andere Medien im Frontend maximal sein 
dürfen. Bei einer Überschreitung dieses Werts wird das entsprechende Objekt automatisch verkleinert.


### Datei-Uploads

**Erlaubte Upload-Dateitypen:** Hier kannst du festlegen, welche Dateitypen auf deinen Server übertragen werden dürfen 
(Upload).

**Maximale Upload-Dateigröße:** Hier kannst du festlegen, wie groß eine mit der Dateiverwaltung auf deinen Server 
übertragene Datei maximal sein darf. Die Eingabe erfolgt in Bytes (1 MB = 1024 KB = 1.024.000 Bytes). Größere Dateien 
werden abgelehnt.

**Maximale Bildbreite:** Beim Upload von Bildern prüft die Dateiverwaltung automatisch deren Breite und vergleicht diese 
Werte mit deiner hier festgelegten Vorgabe. Überschreitet ein Bild die maximale Breite, wird es automatisch 
verkleinert.

**Maximale Bildhöhe:** Beim Upload von Bildern prüft die Dateiverwaltung automatisch deren Höhe und vergleicht diese Werte 
mit deiner hier festgelegten Vorgabe. Überschreitet ein Bild die maximale Höhe, wird es automatisch verkleinert.


### Cronjob-Einstellungen

**Den Command-Scheduler deaktivieren:** Hier kannst du den Periodic Command Scheduler deaktivieren und die 
`_contao/cron`-Route mittels eines echten Cronjobs (den du selbst einrichten musst) ausführen.


### Website-Suche

**Suche aktivieren:** Wenn du diese Option auswählst, indiziert Contao die fertigen Seiten deiner Webseite und erstellt 
daraus einen Suchindex. Mit dem Frontend-Modul 
»[Suchmaschine](../../modulverwaltung/website-suche/#konfiguration-des-suchmoduls)« kannst du diesen Index dann 
durchsuchen.

**Geschützte Seiten indizieren:** Wähle diese Option, um auch geschützte Seiten für die Suche zu indizieren. Nutze 
dieses Feature mit Bedacht, und achte darauf, personalisierte Seiten grundsätzlich von der Suche auszuschließen.


### Standard-Zugriffsrechte

**Standardbesitzer:** Hier kannst du vorgeben, welchem Benutzer standardmäßig die Seiten gehören, für die keine 
Zugriffsrechte definiert wurden. Weitere Informationen dazu findest du im Abschnitt 
[Zugriffsrechte](../../seitenstruktur/seiten-konfigurieren/#zugriffsrechte).

**Standardgruppe:** Hier kannst du festlegen, welcher Gruppe standardmäßig die Seiten gehören, für die keine 
Zugriffsrechte definiert wurden. Weitere Informationen dazu findest du im Abschnitt 
[Zugriffsrechte](../../seitenstruktur/seiten-konfigurieren/#zugriffsrechte).

**Standardzugriffsrechte:** Hier kannst du festlegen, welche Zugriffsrechte standardmäßig für die Seiten gelten, für 
die keine speziellen Zugriffsrechte definiert wurden. Weitere Informationen dazu findest du im Abschnitt 
[Zugriffsrechte](../../seitenstruktur/seiten-konfigurieren/#zugriffsrechte).



## parameters.yml

In der Contao Managed Edition werden die Parameter (z. B. Datenbankdaten) in der `parameters.yml` abgelegt. 
Auf diese Daten greift auch das Contao-Installtool zurück. Diese Datei wird normalerweise von der Versionierung 
ausgenommen und kann auch zusätzliche Einträge wie z. B. das Install-Passwort oder die Angaben für den E-Mail-Versand 
über SMTP enthalten.

Die Datei `parameters.yml` findest du im Ordner `app/config/` und wird bei der Installation von Contao automatisch 
angelegt.

{{% notice note %}}
Ab der Version 4.8 von Contao befindet sich die Datei im Ordner `config`.
{{% /notice %}}

Die `parameters.yml` nach der Installation von Contao:

```yaml
# This file has been auto-generated during installation
parameters:
    database_host: …
    database_port: …
    database_user: …
    database_password: …
    database_name: …
    secret: …
```


### SMTP-Versand

Um den SMTP-Versand einzurichten, brauchst du folgende Angaben von deinem Hoster:

- Den **Hostnamen** des SMTP-Servers.
- Den **Benutzernamen** für den SMTP-Server.
- Das **Passwort** für den SMTP-Server.
- Die **Portnummer** des SMTP-Servers (587 / 465).
- Die **Verschlüsselungsmethode** für den SMTP-Server (tls / ssl).

Diese fügst du dann unterhalb der bereits bestehenden Daten in die `parameters.yml` ein:

```yaml
# This file has been auto-generated during installation
parameters:
    …
    mailer_transport: smtp
    mailer_host: host.example.com
    mailer_user: mail@example.com
    mailer_password: 'mein-passwort'
    mailer_port: 465
    mailer_encryption: ssl
```


## config.yml

Die normale Bundle Config gehört in die `config.yml` und befindet sich im Ordner `app/config/`. 
Falls die Datei noch nicht vorhanden ist, muss diese angelegt werden. Contao lädt automatisch die `config_prod.yml` 
bzw. `config_dev.yml` und falls nicht vorhanden die `config.yml`.

Damit kannst du unterschiedliche Konfigurationen für deine Test- bzw. Produktionsumgebung (dev/prod) realisieren (z. B. 
mehr Logging im Debug Modus). Außerdem committest du die `config.yml` im Gegensatz zur `parameters.yml` in dein 
[Repository](https://de.wikipedia.org/wiki/Repository).

{{% notice note %}}
Ab der Version 4.8 von Contao befindet sich die Datei im Ordner `config`.
{{% /notice %}}

Über die Kommandozeile kommst du an die Standard-Konfiguration für Contao:

```bash
vendor/bin/contao-console config:dump-reference contao
```

```yaml
# Default configuration for extension with alias: "contao"
contao:
    web_dir:              /contao/web
    prepend_locale:       false
    encryption_key:       '%kernel.secret%'
    url_suffix:           .html
    upload_path:          files
    preview_script:       ''
    csrf_cookie_prefix:   csrf_
    csrf_token_name:      contao_csrf_token
    pretty_error_screens: false
    error_level:          8183
    locales:

        # Defaults:
        - en
        - pl
        - ja
        - it
        - cs
        - ru
        - pt
        - zh
        - sr
        - nl
        - de
        - fr
        - es
        - fa
    image:
        bypass_cache:         false
        target_path:          null
        target_dir:           /contao/assets/images
        valid_extensions:

            # Defaults:
            - jpg
            - jpeg
            - gif
            - png
            - tif
            - tiff
            - bmp
            - svg
            - svgz
            - webp

        # As of Contao 4.6, Contao automatically detects the best Imagine service out of Gmagick, Imagick and Gd (in this order). 
        # To use a specific service, set its service ID here:
        # - Gmagick: "contao.image.imagine.gmagick"
        # - Imagick: "contao.image.imagine.imagick"
        # - Gd     : "contao.image.imagine.gd"
        imagine_service:      null
        imagine_options:
            jpeg_quality:         80
            jpeg_sampling_factors:

                # Defaults:
                - 2
                - 1
                - 1
            png_compression_level: ~
            png_compression_filter: ~
            webp_quality:         ~
            webp_lossless:        ~
            interlace:            plane
        reject_large_uploads: false
        sizes:

            # Prototype
            name:
                width:                ~
                height:               ~
                resizeMode:           ~ # One of "crop"; "box"; "proportional"
                zoom:                 ~
                cssClass:             ~
                densities:            ~
                sizes:                ~
                skipIfDimensionsMatch: ~
                formats:

                    # Prototype
                    source:               []
                items:

                    # Prototype
                    -
                        width:                ~
                        height:               ~
                        resizeMode:           ~ # One of "crop"; "box"; "proportional"
                        zoom:                 ~
                        media:                ~
                        densities:            ~
                        sizes:                ~
    security:
        two_factor:
            enforce_backend:      false
    localconfig:          ~
```

{{% notice warning %}}
**Cache leeren**  
Damit die Änderungen aktiv werden, muss am Ende der Anwendungs-Cache über den Contao Manager (»Systemwartung« > 
»Prod.-Cache erneuern«) oder alternativ über die Kommandozeile geleert werden.

```bash
vendor/bin/contao-console cache:clear --env=prod --no-warmup
```

{{% /notice %}}
