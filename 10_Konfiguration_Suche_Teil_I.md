# Konfiguration der Suche, Teil I

Die Konfiguration der Suche werden wir in zwei getrennten Kapiteln behandeln. In diesem Kapitel folgen zunächst Informationen zu den Sucheinstellungen sowie zur Definition sogenannter Suchtypen. Konkrete Einstellungen werden wir dabei nicht durchführen, da dies in hohem Maße von Ihren Anforderungen abhängig ist.

Zum Abschluss dieses Kapitels werden wir uns mit Stoppworten befassen. Im nächsten Kapitel folgt der eigentliche Datenimport, bevor wir anschließend die Konfiguration der Suche fortsetzen.

## Sucheinstellungen (Datei ```searches.ini ```)

Die Einstellungen in der Datei ```searches.ini```steuert das Verhalten der Suche innerhalb von VuFind. Neben allgemeinen Einstellungen enthält die Datei Einstellungen für die einfache Suche, die erweiterte Suche und die Suchvorschläge.

Die folgende Tabelle listet den jeweiligen Abschnitt der Datei ```searches.ini```auf.


| Einstellung | Abschnitt |
| ------------- | ------------- |
| Allgemeine Einstellungen | ```[General]``` |
| Einfache Suche | ```[Basic_Searches]``` |
| Erweiterte Suche | ```[Advanced_Searches]``` |
| Suchvorschläge | ```[Autocomplete]``` ```[Autocomplete_Types]``` |

Zu den allgemeinen Einstellungen gehören unter anderem die Definition des Standardsuchfeldes (AllFields), die Zahl der auf einer Seite der Trefferliste angezeigten Treffer, das Verhalten Suchoperatoren (Boole, Range) und das Search Result Highlighting.

Sofern Sie sich mit der erweiterten Suche befassen möchten: Innerhalb der Datei ```facets.ini```gibt es einen Abschnitt namens „\[Advanced\]“. Dort werden die Facetten definiert, welche als Limiter innerhalb der erweiterten Suche angezeigt werden.

## Definition von Suchtypen (Datei ```searchspecs.yaml ```)

In der Datei ```searchspecs.yaml```sind die innerhalb von VuFind verfügbaren Suchtypen definiert. Die Datei befindet sich im zentralen Konfigurationsverzeichnis. Sofern Sie die Definitionen für die Suchtypen anpassen möchten, sollten Sie die Datei in Ihr lokales Konfigurationsverzeichnis kopieren.

Eine Sucheingabe im Suchschlitz der Katalogoberfläche von VuFind wird mittels eines Query Parser in eine Suchanfrage an den Suchindex übersetzt. In VuFind werden zwei verschiedene Query Parser verwendet: Der DisMax Query Parser und der Lucene Query Parser.

In der Datei ```searchspecs.yaml```sind Einstellungen für DisMax anhand des Elements „DismaxFields“ erkennbar. Einstellungen für Lucene sind anhand des Elementes „QueryFields“ erkennbar.

Einstellbar sind beispielsweise Eigenschaften wie die Gewichtung einzelner Suchfelder und die Unschärfe der Suche.

## Stoppworte

Die Stoppwortliste für VuFind befindet sich in der Datei ```stopwords.txt```im Verzeichnis ``` /usr/local/vufind2/solr/biblio/conf/```. In einer frisch durchgeführten Installation enthält die Liste Stoppworte in englischer Sprache.

Sofern Sie mit Stoppworten in deutscher Sprache arbeiten möchten, sollten Sie in der Stoppwortliste Ihre Stoppworte ergänzen oder die vorhandenen Stoppworte mit Ihren gewünschten ersetzen. Wenn Sie nicht mit einer Stoppwortliste arbeiten möchten, sollten Sie den Inhalt der Stoppwortliste leeren.

  --------- ----------------------------------------------------------------------------------------------------------------------------------------------------
  **!!!**   Sie sollten die Datei ```stopwords.txt ```nicht umbenennen oder löschen. Ohne diese Datei funktioniert der Suchindex von VuFind nicht.
  --------- ----------------------------------------------------------------------------------------------------------------------------------------------------

Nach einer Bearbeitung der Stoppwortliste ist eine erneute Indexierung aller im Index vorhandenen Datensätze erforderlich. Im Tutorial werden wir ohne Stoppworte arbeiten und haben daher bisher nur mit den Daten aus dem Testimport gearbeitet.

Öffnen Sie die Datei ```stopwords.txt```, entfernen Sie alle darin enthaltenen Einträge und speichern Sie die Datei ab.

## Sicherungspunkt

Fahren Sie Xubuntu herunter und setzen Sie in VirtualBox einen Sicherungspunkt namens „Konfiguration abgeschlossen, bereit für Datenimport“.

## Quellen

Search Customization. VuFind Documentation.
<https://vufind.org/wiki/searches_customizing_tuning_adding>

Stop Words and Synonyms. VuFind Documentation.
<https://vufind.org/wiki/stop_words_and_synonyms>
