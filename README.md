# freepbx 17.0

## CID Superfecta

Was mich schon immer gestört hat, dass die FreePBX irgendwie keine Nummern aus dem Globalen Telefonbuch aufgelöst hat. Sie hat immer Probleme mit den Internationalen Vorwahlen, welche ja nun mit +49 usw. beginnen. Denn übergeben werden z.B. von der Deutschen Telekom die Anrufernummern in dem Internationalen Format. Die FreePBX mit dem CallerID Superfecta sucht aber schlichtweg falsch. Sie scheint die Internationale Kennung zu unterdrücken. Mir ist der Fehler, trotz intensiver Suche, nirgends aufgefallen, so dass ich nun kurzerhand ein eigenes Modul aufgebaut habe. Das sucht so wie es sich gehört im Globalen Adressbuch, fertig.

Getestet mit FreePBX 17.0.19.32

Die Datei

```source-MicroBook.module```

nach

```/var/www/html/admin/modules/superfecta/sources/```

kopieren

```fwconsole reload``` ausführen und ab jetzt sollte in der CID Superfecta der Eintrag "MicroBook" existieren. Den aktivieren, fertig. Ab jetzt sollte jeder das Globale Adressbuch nutzen können und die Namen werden auf jedem Telefon zur Anzeige gebracht.

## Funktion einschalten

Damit die Suche auch funktioniert, muss unter **Connectivity** -> **Inbound Routes** -> **Deine Konfiguration** -> other -> das Superfecta Scheme auch ausgewählt werden, welches man zuvor in der Admin-Umgebung ausgewählt und eingestellt hat.

# English

What has always bothered me is that FreePBX somehow did not resolve numbers from the global phone book. It always has problems with international dialling codes, which now start with +49, etc. This is because Deutsche Telekom, for example, transmits caller numbers in international format. However, FreePBX with CallerID Superfecta simply searches incorrectly. It seems to suppress the international code. Despite intensive searching, I couldn't find the error anywhere, so I decided to build my own module. It searches the global address book as it should, and that's it.

Tested with FreePBX 17.0.19.32.

Copy the file

```source-MicroBook.module```

to

```/var/www/html/admin/modules/superfecta/sources/```

Copy

```fwconsole reload``` Execute and from now on, the entry ‘MicroBook’ should exist in CID Superfecta. Activate it, done. From now on, everyone should be able to use the global address book and the names will be displayed on every telephone.

## Enable function

For the search to work, you must also select the Superfecta Scheme under **Connectivity** -> **Inbound Routes** -> **Your configuration** -> other -> which you previously selected and set in the admin environment.
