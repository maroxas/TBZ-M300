# TBZ - M300 Plattformübergreifende Dienste LB1

In diesem Projekt LB1 wurden zwei Versuche durchdeführt. Beim Versuch 1 sind die Services (Apache, MySQL und PHPMyAdmin) nur auf einem Server bzw. VM installiert. Beim Versuch 2 wurden die Services separiert in zwei VMs.

**Ich bevorzuge den Versuch 1 zu korrigieren**, da beim Versuch 2 ungenaue Fehler aufgetreten sind, somit können die Services nicht getestet werden.

# Testen

Folgen Sie die untenstehende Punkte, um die Services zu testen:

```
1) git clone https://github.com/maroxas/TBZ-M300/edit/master/
2) vagrant up
```
Nachdem die von Vagrant ausgeführten Sachen ausgeführt sind, gehen Sie folgendes durch:
```
3) Apache Webserver kontrollieren:
  - http://localhost:5000 in Web Browser aufrufen.
4) PHPMyAdmin kontrollieren:
  - http://localhost:5000/phpmyadmin in Web Browser aufrufen
  -> Username: root
  -> Password: test
5) DB Daten auf PHPMyAdmin kontrollieren
```

## Vagrantfile

Mit folgendem Befehl können Sie den Vagrantfile in VisualStudio o.a. anzeigen lassen:

```
code Vagrantfile
```

## Author

**Marc Anthony Roxas** - *Initial work* - [TBZ]
