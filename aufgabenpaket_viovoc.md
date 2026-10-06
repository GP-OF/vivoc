# Aufgabenpakete für den VS-Code-Agenten: iPhone-Vokabeltrainer

**Grundlage:** `Lastenheft_iPhone_Vokabeltrainer.md` aus dem Gespräch. Dieses Dokument ist ein Ausführungsplan, kein Ersatz für das Lastenheft. Bei Widersprüchen gilt das Lastenheft; Unklarheiten vor der betroffenen Umsetzung benennen. **Immer nur ein Paket beauftragen und abnehmen.**

## So arbeitest du mit dem Agenten

1. Lege Lastenheft und diese Aufgabenliste im Projektverzeichnis ab. Teile dem Agenten beide Dateien mit und lass ihn vor Paket 0 die Anforderungen lesen.
2. Gib dem Agenten jeweils **nur den Prompt des nächsten Pakets**. Keine spätere Funktion vorziehen, außer für eine kleine, ausdrücklich benannte technische Vorbereitung.
3. Lass nach jedem Paket Änderungen, Tests, bekannte Einschränkungen und den Commit dokumentieren. Prüfe das Ergebnis; erst dann nächstes Paket.
4. Bei Fehlern: im aktuellen Paket reparieren oder auf den letzten grünen Commit zurückgehen. Nicht auf einem kaputten Zwischenstand weiterbauen.
5. Ein Paket ist erst fertig, wenn die Definition of Done erfüllt ist; „Code geschrieben“ genügt nicht.

## Unveränderliche Leitplanken für **jedes** Paket

- Lastenheft erneut lesen und betroffene Anforderungen nennen; vorhandene Architektur, Schnittstellen, Datenformate und Tests respektieren.
- Nur den beauftragten Umfang ändern. Keine stillschweigenden Umbenennungen, Massenrefactorings, Datenbank-Resets oder Änderungen an bereits abgenommenen Produktregeln.
- Vorherigen grünen Stand erfassen. Änderungen möglichst klein und überprüfbar halten; neue Funktionen hinter klaren Komponenten/Schnittstellen ergänzen.
- Nach Änderung alle bisherigen automatisierten Tests plus neue Tests ausführen; Build prüfen. Bestehende Tests nicht löschen oder abschwächen, nur um Grün zu erreichen.
- Änderungen an persistentem Datenmodell, CSV-Schema oder Bewertungsregeln nur mit begründeter, rückwärtsverträglicher Migration und Regressionstests. Vorhandene Nutzerdaten niemals stillschweigend löschen.
- Keine Mockdaten als echte Daten ausgeben; keine Fotoerkennung oder Gerätetests als „bestanden“ markieren, wenn nur Simulator-/Unit-Tests durchgeführt wurden.
- Zum Abschluss melden: implementiert, geänderte Dateien, ausgeführte Befehle/Tests und Resultate, offene Punkte, Auswirkungen auf frühere Pakete, Commit-ID. Falls Build/Gerät nicht verfügbar: klar „nicht verifiziert“.
- Der Nutzer entscheidet über den Übergang zum nächsten Paket. Keine automatischen Folgeschritte.

## Paket 0 – Projektprüfung und technische Basisentscheidung

**Ziel:** Entwicklungsumgebung und Zielgerät klären, ohne Produktfunktionen zu implementieren.

**Aufgaben:** Lastenheft lesen; Xcode/Swift-Toolchain, Signierung und Zugriff auf iPhone SE (2. Generation) prüfen; installierte iOS-Version erfragen, falls nicht verfügbar. Deployment-Target begründen; lokale Persistenz, Kamera/Fotoauswahl, OCR und Systemdiktat auf diesem Ziel auf grundsätzliche Eignung prüfen. Kurze Architektur- und Risikoübersicht erstellen, insbesondere Handschrift und Buchlayout. Technische Parameter, die das Lastenheft offenlässt, als konfigurierbare Vorschläge dokumentieren, nicht heimlich festlegen.

**Ergebnis:** `docs/TECHNICAL_BASELINE.md` mit bestätigten Fakten, Annahmen, offenen Blockern, Modulgrenzen und Teststrategie.

**Abnahme:** Keine unbestätigte Behauptung über Gerätekompatibilität; Zielversion oder klarer Blocker dokumentiert. Kein produktiver Code erforderlich.

**Agent-Prompt:** „Lies `Lastenheft_iPhone_Vokabeltrainer.md` und `Aufgabenpakete_iPhone_Vokabeltrainer.md`. Bearbeite ausschließlich Paket 0. Dokumentiere überprüfte Fakten getrennt von Annahmen. Frage nach der installierten iOS-Version, falls sie für das Deployment-Target fehlt. Implementiere noch keine Produktfunktionen. Berichte nach dem allgemeinen Abschlussformat.“

## Paket 1 – Projektgerüst und Qualitätsnetz

**Ziel:** Eine startbare App mit stabiler Projektstruktur und Testpipeline.

**Aufgaben:** iPhone-Projekt anlegen; Startbildschirm als Platzhalter; Modulgrenzen für Daten, CSV, Training, OCR, Statistik und Gamification vorbereiten; Testtargets und dokumentierte Build-/Testbefehle einrichten; `.gitignore`, README und Versionskontrolle. Keine Fake-Funktionen als fertig präsentieren.

**Abnahme:** App startet auf geeignetem Simulator; Build und erster Testlauf grün; Projekt lässt sich nach README öffnen. Gerätetest nur behaupten, wenn tatsächlich ausgeführt.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 1 gemäß Aufgabenliste und Lastenheft. Erzeuge ein startbares Gerüst und ein reproduzierbares Testkommando. Keine Trainings-, Import- oder OCR-Logik vorziehen. Prüfe Build und Tests und dokumentiere den Commit.“

## Paket 2 – Datenmodell, lokale Speicherung und Listen

**Ziel:** Dauerhafte, getrennte Vokabel- und Lernstandsdaten als Fundament.

**Aufgaben:** Modelle für Vokabel, Liste, Lernstand je Richtung, Session und Versuch definieren; stabile IDs und Beziehungen; lokale Speicherung; Migrationstest für spätere Schemaänderungen; manuelle Anlage/Bearbeitung/Suche/Löschen von Vokabeln und frei benannten Listen. Trennung Englisch/Deutsch und Latein/Deutsch sicherstellen. Daten über Neustart erhalten.

**Abnahme:** Zwei Richtungen einer Vokabel besitzen unabhängige Lernstände; Editieren und Neustart erhalten Daten; Löschung erfordert Bestätigung; Modelltests grün. Datenmigration als Vorgehen dokumentiert.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 2. Nutze die in Paket 1 festgelegten Modulgrenzen. Implementiere persistente Vokabeln, Listen und getrennte Lernstände mit Tests. Ändere keine abgenommenen Schnittstellen ohne begründete Migration. Führe die gesamte bisherige Testsuite aus.“

## Paket 3 – CSV-Vorlage, Import, Export und Sicherungs-Roundtrip

**Ziel:** Verlässlicher Austausch und Wiederherstellung von Vokabeln **und beiden Lernständen**.

**Aufgaben:** feste UTF-8-CSV-Vorlage und Beispiel-Datei; Semikolon und korrektes CSV-Quoting; Importvorschau, Zeilenfehler, Duplikate, Bestätigung; Export aller oder gefilterter Vokabeln samt Listen/Lernständen; Formatversion und stabile IDs; Konfliktstrategie bei Reimport; atomare Übernahme. Keine historische Antwort-Historie im CSV versprechen. Parser und Exporter getrennt von UI testen.

**Abnahme:** Export → Import in leere Datenbank erhält Wörter, Umlaute, Alternativen, Listen, beide Lernstände und Fälligkeiten; Abbruch verändert Daten nicht; fehlerhafte Zeile hat verständliche Meldung; Wiederimport überschreibt nichts unbemerkt; alle alten Tests grün.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 3. Nutze das Datenmodell aus Paket 2. Baue und teste den CSV-Roundtrip einschließlich beider Lernrichtungen. Dokumentiere Format und Konfliktstrategie. Keine Änderung der Persistenz ohne Migrationstest; gesamte Testsuite ausführen.“

## Paket 4 – Trainingskern und Antwortbewertung

**Ziel:** Echte Abfragen ohne Wiederholungsalgorithmus oder Spielmechanik.

**Aufgaben:** Auswahl Sprachpaar/Richtung/Liste/Anzahl; 5/10/20/30 und freie Zahl; Session mit unterschiedlichen Vokabeln; Eingabe über normales Textfeld und iPhone-Systemdiktat; zwei Buchstabentipps; gültige Alternativen; konservative Normalisierung; „fast richtig“ mit Nutzerentscheidung. Versuche samt Tippstatus und Entscheidung speichern. Für diese Stufe einfache deterministische Reihenfolge, noch keine adaptive Auswahl.

**Abnahme:** 20 bedeutet 20 unterschiedliche Vokabeln, sofern vorhanden; Richtungen und Alternativen funktionieren; Diktattext vor Absenden korrigierbar; Tipp 1/2 korrekt; Fast-richtig-Entscheidung gespeichert; keine falsche lateinische Endung automatisch als richtig; alte Tests grün.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 4. Implementiere Trainingsablauf und isoliert testbare Antwortbewertung. Adaptive Wiederholung und Punkte bleiben für spätere Pakete. Prüfe alle bisherigen Tests und melde, ob Systemdiktat real am Gerät oder nur als Texteingabe getestet wurde.“

## Paket 5 – Adaptive Wiederholung und Wiederholungen innerhalb der Session

**Ziel:** Schwierige Karten häufiger, sichere Karten seltener; Fehler in derselben Session erneut üben.

**Aufgaben:** Auswahl- und Fälligkeitslogik als eigenständige Komponente; getrennt je Richtung; neue/fällige/schwierige Karten priorisieren; richtig ohne Tipp, richtig mit Tipp, selbst als richtig gewertetes Fast-richtig und falsch abgestuft behandeln; falsch beantwortete Vokabeln nach einigen anderen Karten wiederholen; Obergrenze gegen Endlosschleifen. Intervalle, Gewichte und Grenzen zentral konfigurieren und dokumentieren. Sessiongröße bleibt Zahl unterschiedlicher Wörter.

**Abnahme:** Tests zeigen die gewünschte relative Reihenfolge der Fälligkeit, unabhängige Richtungen, zusätzliche Wiederholung ohne Veränderung der Zahl unterschiedlicher Wörter, begrenzte Session und Erhalt früherer Fehlversuche. CSV-Roundtrip und Paket-4-Tests bleiben grün.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 5. Ergänze adaptive Planung hinter den vorhandenen Schnittstellen; ändere keine Bewertung oder CSV-Struktur ohne Tests/Migration. Dokumentiere Parameter und prüfe mit Regressionstests die Pakete 2–4.“

## Paket 6 – Lernzeit und Statistik

**Ziel:** Nachvollziehbare Kennzahlen statt geschätzter Anzeigen.

**Aufgaben:** aktive Sessionzeit messen; bei dokumentierter Inaktivitätsschwelle pausieren; Tag/Woche/Monat nach lokaler Zeitzone, Woche ab Montag; Filter nach Sprache/Richtung; Versuche, unterschiedliche Vokabeln, aktive Zeit, Richtigquote und richtige Antworten ohne Tipp berechnen. Nicht abgeschickte Karten ausschließen. Historische Statistik nicht aus bloßen CSV-Lernstandszählern vortäuschen.

**Abnahme:** erst falsch, dann richtig = zwei Versuche und 50 %; dieselbe Vokabel mehrfach = eine unterschiedliche Vokabel im Zeitraum; Zeit pausiert bei Inaktivität; Zeitzonen-/Tageswechseltests; ältere Tests grün.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 6. Berechne Statistiken aus gespeicherten Versuchen und Sessions. Teste Zeitgrenzen, Filter, Wiederholungen und Pausen. Ändere frühere Produktregeln nicht; gesamte Testsuite ausführen.“

## Paket 7 – Fotoimport: OCR-Prototyp und Prüfansicht

**Ziel:** Aus Bildern Vorschläge erzeugen, niemals ungeprüft Vokabeln speichern.

**Aufgaben:** Kamera/Fotomediathek; Texterkennung und Zuordnung zu möglichen Wortpaaren; vorläufige Importdaten getrennt vom Vokabelbestand; Originalfoto im Prüfablauf; je Vorschlag editieren, bestätigen oder verwerfen; unvollständige Einträge/Duplikate markieren; abschließende Freigabe mit atomarer Übernahme. Für gedruckte Zweispaltenliste, Handschrift und Buchseite mit Zusatztext echte Beispiele prüfen; unsichere Zuordnungen sichtbar machen statt zu erfinden.

**Abnahme:** Ohne finale Freigabe keine neue Vokabel; Abbruch unveränderter Bestand; Korrektur eines OCR-Fehlers vor Übernahme möglich; Duplikate und leere Felder geprüft. Teststatus für jede der drei Bildarten separat nennen; fehlende reale Fotos als „nicht verifiziert“ markieren. Alle bisherigen Tests grün.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 7. Implementiere OCR-Vorschläge und zwingende Nutzerverifikation mit finaler Freigabe. Trenne Entwürfe strikt von gespeicherten Vokabeln. Berichte die tatsächlichen Ergebnisse je Bildart; keine Qualitätsbehauptung ohne echte Testbilder. Führe Regressionstests aus.“

## Paket 8 – Punkte, Serie, Level, Tagesziel, Abzeichen und Animationen

**Ziel:** Motivation ergänzen, ohne Lernlogik oder Statistik zu verfälschen.

**Aufgaben:** dokumentierte Punkte-/Level-/Abzeichenregeln; einstellbares Tagesziel auf Basis unterschiedlicher trainierter Vokabeln; Serie nach lokalen Tagen mit erreichtem Ziel; kurze Animationen und reduzierte Bewegung. Tipps und Fast-richtig nicht wie sofort richtige Antworten belohnen. Spielzustand aus gespeicherten Ereignissen konsistent ableiten oder robust persistieren.

**Abnahme:** Punkte ändern keine Richtigquote/Fälligkeit; Ziel/Serie an Tagesgrenze korrekt; keine Doppelvergabe bei Wiederholung oder App-Neustart; Animationen abschaltbar; alle früheren Tests grün.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 8. Ergänze Spielmechaniken ohne Änderungen an fachlicher Antwortbewertung, Wiederholung und KPI-Definitionen. Teste doppelte Vergabe, Neustart und Tageswechsel; gesamte Testsuite ausführen.“

## Paket 9 – Integration, Barrierefreiheit und reale Abnahme

**Ziel:** Alle Funktionen gemeinsam auf dem Zielgerät stabil betreiben.

**Aufgaben:** vollständige Nutzerwege testen; iPhone SE (2. Generation) mit geöffneter Tastatur; Diktat über Systemtastatur; Offline-Verhalten; CSV-Backup und Restore; OCR mit drei echten Bildarten; dynamische Schrift, VoiceOver, Kontrast, reduzierte Bewegung; Fehler- und Abbruchfälle. Regressionsfehler im verursachenden Modul gezielt beheben, nicht Tests entfernen. README, Installationsanleitung und bekannte Grenzen finalisieren.

**Abnahme:** Alle Lastenheft-Abnahmekriterien mit „bestanden“, „nicht bestanden“ oder „nicht verifiziert“ und Nachweis dokumentiert; Build und gesamte Testsuite grün; keine offenen kritischen Datenverlust- oder Importfehler; Abschluss-Commit.

**Agent-Prompt:** „Bearbeite ausschließlich Paket 9. Prüfe das gesamte Lastenheft gegen die implementierte App, führe Build, Regressionstests und verfügbare Gerätetests aus. Erstelle eine Abnahmeliste mit Nachweisen und kennzeichne nicht getestete Fälle ehrlich. Repariere Regressionen ohne frühere Anforderungen abzuschwächen.“

## Übergabeprotokoll nach jedem Paket

Der Agent soll jeweils diese kurze Vorlage ausfüllen:

```text
Paket: [Nummer/Name]
Umgesetzt: [konkrete Ergebnisse]
Geänderte Dateien/Schnittstellen: [Liste]
Datenmodell/CSV geändert? [Nein / Ja + Migration und Rückwärtskompatibilität]
Build und Tests: [Befehl, Ergebnis; bisherige + neue Tests]
Manuell geprüft: [Simulator/Gerät und konkrete Fälle]
Frühere Pakete weiterhin funktionsfähig: [Nachweis oder offene Risiken]
Offene Punkte: [klar benennen]
Commit-ID: [Hash]
Freigabe für nächstes Paket empfohlen: [Ja/Nein + Grund]
```

**Stop-Regel:** Wenn ein Paket die bisherigen Tests nicht besteht oder Nutzerdaten gefährdet, keine Freigabe für das nächste Paket. Zuerst Ursache beheben, Migration ergänzen oder den letzten grünen Stand wiederherstellen.
