# TBZ - M300 Plattformübergreifende Dienste LB1

In diesem Projekt LB1 wurden zwei Versuche durchgeführt. Beim Versuch 1 sind die Services (Apache, MySQL und PHPMyAdmin) nur auf einem Server bzw. VM installiert. Beim Versuch 2 wurden die Services separiert in zwei VMs.

-> Siehe Ordner /TBZ-M300/Versuch1 und /TBZ-M300/Versuch2

**Ich bevorzuge den Versuch 1 zu korrigieren**, da beim Versuch 2 ungenaue Fehler aufgetreten sind, somit können die Services nicht getestet werden.

# Testen

Folgen Sie die untenstehende Punkte, um die Services zu testen:

```
1) git clone https://github.com/maroxas/TBZ-M300/
2) vagrant up
```

Nachdem die von Vagrant ausgeführten Sachen ausgeführt sind, gehen Sie folgendes durch:
```
3) Apache Webserver kontrollieren:

  - http://localhost:5000 in Web Browser aufrufen.
  
  Erwartetes Ergebnis: Apache Webseite erreichbar.
  
4) PHPMyAdmin kontrollieren:

  - http://localhost:5000/phpmyadmin in Web Browser aufrufen
  
  -> Username: root
  -> Password: test
  
  Erwartetes Ergebnis: PHPMyAdmin Webseite erreichbar und Anmeldung erfolgreich.
  
5) DB Daten auf PHPMyAdmin kontrollieren

  Erwartetes Ergebnis: DB Daten auf PHPMyAdmin ersichtlich.
```

# Vagrantfile

Mit folgendem Befehl können Sie den Vagrantfile in VisualStudio o.a. anzeigen lassen:

```
code Vagrantfile
```

## Author

**Marc Anthony Roxas** - *Initial work* - [TBZ]
