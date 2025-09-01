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

