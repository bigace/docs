# Configuration Files

There are two types of configuration Files, the first one are valid for the entire System, the othe ones are Community dependend.

## System Configurations

System wide configurations can be found in Config Files within the directory **/system/config/**.

**config.system.php**
In dieser Datei finden sich die wichtigsten Einstellungen, z.B. die Verbindungsdaten zur Datenbank. Diese Datei ist interessant für Systemadministratoren, hier können unter anderem Session Einstellungen verändert werden.

**[consumer.ini](manual/community#consumer.ini)**
Hier finden Sie die Verknüpfungen zwischen Domain Namen zu Consumer ID, Wartungsarbeiten und Default Consumer. Zum Editieren dieser Datei stehen mehrere Administratrationsmasken zur Verfügung. Es wird dringend davon abgeraten diese Datei manuell anzupassen!

**mimetypes.ini**
Diee Datei enthält die Konfiguration für die Zuordnung zwischen Dateitypen und Itemtypes. Sollten Sie nicht in der Lage sein bestimmte Dateitypen hochzuladen, ist hier der richtige Ansatzpunkt.

**services.ini**
Diese Datei ist ein elementarer Bestandteil des Core Systems, hier werden die Implementationen der API Interfaces konfiguriert. Seien Sie vorsischtig wenn Sie hier Änderungen vornehmen. Hier können Sie z.B. das Loglevel anpassen.


## Community Configurations

Community dependend configurations can be found in your Community Directory [/consumer/cid{CID}/config/](cid_cid).

**config.system.cid{CID}.inc.php** 	
Alle hier aufgeführten Werte überschreiben die Einstellungen der Datei config.system.php (siehe auch the section called “System Configurations”). Die so überschriebenen Einstellungen gelten dann nur für den jeweiligen Consumer.

Kopieren Sie die entsprechenden Einstellungen einfach von den System Dateien in die Community Konfiguration und passen sie dort entsprechend an.

Zum Beispiel wäre es möglich eigene Datenbanken für bestimmte Communitys zu verwenden. Häufiger wird man aber das Loglevel für einzelne Communitys anpassen wollen...

**config.statistic.cid{CID}.inc.php**
Hier ist die Datenbankverbindung für die Statistik Tabellen eingetragen. Da bei eingeschalteten Statistiken eine große Menge an schreibenden Zugriffen stattfindet, sollten diese - aus Performancegründen - in eine andere Datenbank ausgelagert werden.

**config.email.cid{CID}.inc.php**
Hier finden Sie die Einstellungen, welche benutzt werden um Emails zu versenden (z.B. über das "Nachrichten versenden" Modul). Die wichtigsten dieser Einstellungen werden von Ihnen während der Installation eingetragen.

**config.select.inc.php**
In dieser Datei können die Spalten konfiguriert werden, welche von bei Datenbank Abfragen selektiert werden. Dies kann die Performance der Abfragen erhöhen. Sie sollten diese Einstellungen jedoch nur unter Vorsicht ändern, da hierdurch auch einiges "kaputt" konfiguriert werden kann (siehe auch the section called “Database Tuning”).

**user_attributes.ini**
In dieser Datei konfigurieren Sie, welche Felder in der Benutzeradministration für einen Benutzer angezeigt werden sollen. Sie können diese Werte bedenkenlos anpassen, vorhandene Werte werden in der Datenbank nicht verändert oder gelöscht, sie werden schlimmstenfalls nicht mehr angezeigt. Sollte sich in den Übersetzungsdateien (/system/language/XX/userAdmin.lang.php) kein Schlüssel für den jeweiligen Wert finden, wird der Wert zweite Wert als Bezeichnung angezeigt.


