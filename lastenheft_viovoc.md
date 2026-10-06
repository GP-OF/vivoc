# Lastenheft: iPhone-Vokabeltrainer

**Version:** 1.0 · **Status:** Fachliche Vorgabe für einen Entwicklungsagenten in VS Code  
**Ziel:** Eine lokal nutzbare, spielerische iPhone-App zum Lernen englischer, lateinischer und deutscher Vokabeln.

> **Auftrag an den Agenten:** Implementiere die nachstehenden Anforderungen als lauffähige iPhone-App. Dokumentiere technische Entscheidungen und Abweichungen. Erfinde keine Produktregeln, wenn diese als offen markiert sind. Liefere Quellcode, Tests, Beispiel-CSV, Installations- und Testanleitung. Teste insbesondere auf einem iPhone SE (2. Generation) und mit echten Foto-Vorlagen. Keine Cloud, kein Konto, keine kostenpflichtigen APIs.

## 1. Rahmen und Zielgruppe

- Ein einzelner Nutzer, ein iPhone; Daten bleiben lokal auf dem Gerät.
- Ältestes vorgesehenes Testgerät: iPhone SE (2. Generation). Die tatsächlich installierte iOS-Version vor Festlegung des Deployment-Targets ermitteln. Oberfläche auf kleinem Display und bei eingeblendeter Tastatur testen.
- App-Oberfläche auf Deutsch; Trainingssprachen Englisch ↔ Deutsch und Latein ↔ Deutsch.
- Zunächst Entwicklungs-App zum eigenen Test, keine Veröffentlichung im App Store.
- Offline nutzbar, insbesondere Vokabelverwaltung, Training, Statistiken, CSV und Fotoverarbeitung. Falls die iPhone-Systemdiktierfunktion netzabhängig ist, muss Texteingabe weiterhin funktionieren.
- Keine Lernerinnerungen in Version 1.

## 2. Begriffe und fachliche Grundregeln

- **Vokabel:** Ein Eintrag mit fremdsprachiger Seite und mindestens einer deutschen Antwort.
- **Richtung:** Fremdsprache → Deutsch oder Deutsch → Fremdsprache. Beide Richtungen haben voneinander unabhängige Lernstände.
- **Karte:** Kombination aus Vokabel und Richtung.
- **Versuch:** Eine abgeschickte Antwort; jeder Versuch zählt einzeln in die Statistik.
- **Sessiongröße:** Anzahl unterschiedlicher Vokabeln; zusätzliche Wiederholungen falscher Antworten kommen hinzu.
- **Fällig:** Karte, deren nächster Übungstermin erreicht ist.
- **Liste:** Frei benennbare Sammlung; die Zugehörigkeit einer Vokabel zu mehreren Listen ist als technische Erweiterbarkeit vorzusehen. Für Version 1 genügt mindestens eine Liste pro Vokabel.

## 3. Funktionsanforderungen

### F01 – Vokabeln und Listen verwalten

- Vokabeln manuell anlegen, suchen, filtern, bearbeiten und nach Bestätigung löschen.
- Sprachpaar, Fremdwort, mindestens eine deutsche Übersetzung und Liste erfassen; optionale weitere gültige Übersetzungen, Beispielsatz und Notiz.
- Für Deutsch → Fremdsprache mehrere zulässige fremdsprachige Antworten erfassen können, falls erforderlich.
- Duplikate anhand Sprachpaar und normalisierter Wortpaarung erkennen; Nutzer entscheidet über Überspringen oder Übernahme. Keine stillschweigende Überschreibung.
- Frei benennbare Listen anlegen, umbenennen und für das Training auswählen.

### F02 – CSV-Import

- Feste, dokumentierte CSV-Vorlage bereitstellen; keine allgemeine Spaltenzuordnung erforderlich.
- Datei auswählen, Vorschau zeigen, Fehler pro Zeile verständlich ausweisen und Duplikate markieren.
- Nur bestätigte, gültige Zeilen übernehmen; fehlerhafte Zeilen nicht stillschweigend importieren.
- UTF-8 und Umlaute unterstützen. Standard: Semikolon als Trennzeichen, CSV-konforme Anführungszeichen für Werte mit Semikolon, Anführungszeichen oder Zeilenumbruch.
- Beispielvorlage: `sprachpaar;fremdwort;deutsch;weitere_deutsche_antworten;weitere_fremdsprachige_antworten;beispielsatz;notiz;liste`. Mehrfachantworten in einem Feld müssen eindeutig kodiert und dokumentiert werden.
- Für Sicherungsdateien zusätzlich Lernstände beider Richtungen importieren; Formatversion und IDs dokumentieren. Vor Wiederherstellung Vorschau und Konfliktbehandlung anbieten; bestehende Daten nicht unbemerkt überschreiben.

### F03 – CSV-Export und Wiederherstellung

- Alle Vokabeln oder eine Liste als CSV über die iPhone-Dateifreigabe exportieren.
- Export enthält Vokabeln, Zusatzfelder, Listen und **Lernstände beider Richtungen**, einschließlich nächstem Fälligkeitstermin und Zählern.
- Exportierte Datei muss auf einem leeren Datenbestand wieder importierbar sein und Vokabeln sowie Lernstände erhalten. Vollständige Antwort-Historie muss nicht exportiert werden; im UI deutlich machen, dass historische Statistiken bei Wiederherstellung aus CSV möglicherweise nicht vollständig rekonstruierbar sind.
- CSV-Datei als Sicherung kennzeichnen; vor Import in nicht leeren Bestand Konflikte anzeigen.

### F04 – Fotoimport mit verpflichtender Nutzerprüfung

- Foto mit Kamera aufnehmen oder aus Fotos auswählen; Sprachpaar und Zielliste wählen.
- Gedruckte zweispaltige Listen, handschriftliche Vokabelhefte und Buchseiten mit Zusatztext als Anwendungsfälle berücksichtigen. Texterkennung und Zuordnung der Wortpaare sind getrennte Verarbeitungsschritte; Erkennungsqualität anhand echter Beispiele prüfen.
- Ergebnis **nur als Vorschläge** in einer Prüfansicht anzeigen. Originalfoto zum Abgleich sichtbar bzw. aufrufbar halten.
- Je Vorschlag fremdsprachiges Wort, deutsche Antwort und optional Zusatzfelder editieren; einzeln **bestätigen, korrigieren und bestätigen oder verwerfen**.
- Unvollständige Einträge und mögliche Duplikate deutlich markieren. Unvollständige Einträge erst nach Korrektur bestätigen lassen.
- Erst nach ausdrücklicher abschließender Freigabe die bestätigten Einträge dauerhaft speichern. Keine automatische Übernahme. Bei Abbruch bleibt die bestehende Sammlung unverändert.
- Für unklare Spaltenzuordnung muss manuelles Korrigieren möglich sein; keine scheinbar sicheren Übersetzungen erfinden.

### F05 – Training konfigurieren

- Sprachpaar, Abfragerichtung, optional Liste und Anzahl unterschiedlicher Vokabeln wählen.
- Schnellauswahl 5, 10, 20, 30; zusätzlich frei wählbare positive Anzahl, begrenzt auf verfügbare Wörter.
- Verfügbare Anzahl vor Start anzeigen. Sind weniger Wörter verfügbar, mit den verfügbaren starten und verständlich informieren.
- Fällige schwierige und neue Karten bevorzugen; sicher beherrschte seltener auswählen. Nicht fällige Karten nur als Auffüllung nutzen und dies im Auswahlverfahren dokumentieren.

### F06 – Antwort eingeben, Tipps und Feedback

- Frage anzeigen; Antwort mit iPhone-Tastatur eintippen oder über deren System-Diktierfunktion eingeben. Kein eigener Mikrofonknopf erforderlich.
- Diktierten Text vor Absenden anzeigen und editierbar lassen; App muss nicht erkennen, ob Eingabe getippt oder diktiert wurde.
- Tipp 1: erster Buchstabe; Tipp 2: erste zwei Buchstaben der erwarteten Antwort. Bei einem einbuchstabigen Wort nur vorhandene Zeichen anzeigen. Bereits gegebene Tipps bleiben für den Versuch vermerkt.
- Bei mehreren zulässigen Antworten die Hauptantwort als Grundlage für die Buchstabentipps nutzen und dies in der Oberfläche verständlich halten.
- Nach Absenden Ergebnis und hinterlegte gültige Lösungen zeigen. Jede hinterlegte alternative Übersetzung zählt als richtig.
- Normalisierung: äußere Leerzeichen und Groß-/Kleinschreibung ignorieren; sonst keine stillschweigende Gleichsetzung unterschiedlicher Formen, insbesondere lateinischer Endungen.
- Kleine Tippfehler als **„fast richtig“** anbieten, nicht automatisch als richtig zählen. Nutzer entscheidet „als richtig werten“ oder „als falsch werten“. Eine als richtig gewertete Fast-richtig-Antwort zählt in der Quote als richtig, wird aber früher wieder fällig als eine fehlerfrei richtige Antwort. Entscheidung und ursprünglicher Status werden gespeichert.
- Ähnlichkeitsregel konservativ und testbar implementieren; bei unsicheren Fällen keine automatische Korrektur. Bei alternativen Antworten jeweils gegen die hinterlegten Lösungen vergleichen.

### F07 – Wiederholungsplanung

- Lernstand pro Karte (Vokabel × Richtung) separat speichern.
- Neue und falsch beantwortete Karten häufiger, sicher richtige seltener fällig machen. Richtig mit Tipp und „fast richtig, als richtig gewertet“ früher als sofort richtig ohne Tipp wiederholen.
- Falsch beantwortete Wörter nach einigen anderen Karten in derselben Session erneut anzeigen. Wenn nicht genug andere Karten verfügbar sind, dennoch wiederholen, ohne eine Endlosschleife zu erzeugen.
- Innerhalb einer Session Wiederholungen begrenzen und Regel dokumentieren; ein Wort darf die Session nicht endlos blockieren.
- Jeder Versuch bleibt für Statistik erhalten. Spätere richtige Antwort verbessert den Lernstand, löscht den vorherigen Fehlversuch nicht.
- Intervalle und Auswahlgewichte zentral konfigurierbar halten und mit Tests absichern; konkrete Werte vor Implementierung als dokumentierte Annahmen festlegen.

### F08 – Statistik und Lernzeit

- Filter: Heute, Woche, Monat sowie Sprachpaar und Richtung.
- Kennzahlen: Anzahl Versuche, Anzahl unterschiedlicher trainierter Vokabeln, aktive Trainingszeit, Richtigquote; zusätzlich richtige Antworten ohne Tipp ausweisen.
- Quote = als richtig gewertete Versuche / alle abgeschickten Versuche. Beispiel: erst falsch, dann richtig = 1/2 = 50 %.
- Unterschiedliche Vokabeln pro Zeitraum anhand Vokabel-ID zählen, auch wenn beide Richtungen oder mehrere Versuche vorkommen; gefilterte Ansichten entsprechend begrenzen.
- Zeit nur während aktiver Session zählen; bei längerer Untätigkeit automatisch pausieren und bei Interaktion fortsetzen. Inaktivitätsschwelle zentral konfigurierbar dokumentieren.
- Nicht abgeschickte Karten zählen nicht als Versuche. Tages-/Wochen-/Monatsgrenzen nach lokaler Zeitzone des Geräts definieren; Woche beginnt Montag.

### F09 – Spielerische Elemente

- Punkte, tägliche Lernserie, Abzeichen, Level, einstellbares Tagesziel und kleine Animationen.
- Punkte nicht allein für schnelles Durchklicken vergeben; klare, dokumentierte Regeln. Tipps und selbst bestätigte Fast-richtig-Antworten dürfen nicht gleich belohnt werden wie sofort richtige Antworten ohne Tipp.
- Tagesziel anhand eines eindeutig ausgewiesenen Werts definieren, standardmäßig Anzahl unterschiedlicher trainierter Vokabeln. Tagesziel vom Nutzer anpassbar.
- Lernserie anhand lokaler Kalendertage mit erreichtem Tagesziel; Ausfalltage und Tageswechsel nachvollziehbar behandeln.
- Abzeichen und Level anhand dokumentierter Schwellen; Belohnungen beeinflussen weder Richtigquote noch Wiederholungsplanung.
- Animationen kurz, abschaltbar bei reduzierter Bewegung; Trainingsansicht bleibt übersichtlich.

## 4. Bildschirmübersicht

1. Start: fällige Karten, Tagesziel, Lernserie, Training starten.
2. Vokabeln/Listen: Suche, Filter, Anlegen, Bearbeiten, Löschen.
3. Import/Export: CSV-Vorlage, Import, Sicherung, Fotoimport.
4. Foto-Prüfansicht: Original, Vorschläge, Bearbeiten, Bestätigen/Verwerfen, abschließende Freigabe.
5. Session vorbereiten: Sprache, Richtung, Liste, Anzahl.
6. Training: Frage, Texteingabe, Tipp 1/2, Antwort prüfen, Feedback.
7. Session-Ende: Versuche, unterschiedliche Wörter, Quote, Zeit, Punkte.
8. Statistik: Tag/Woche/Monat und Filter.
9. Einstellungen: Tagesziel, Datenverwaltung, Animationen.

## 5. Datenmodell, fachlich

- **Vocabulary:** ID, Sprachpaar, Fremdwort, gültige fremdsprachige Antworten, gültige deutsche Antworten, Beispielsatz, Notiz, Listenbezug, Erstellungs-/Änderungsdatum.
- **List:** ID, Name.
- **LearningState:** Vokabel-ID, Richtung, Fälligkeit, Wiederholungsstufe/Intervall, richtig/falsch/mit Tipp, letzter Versuch.
- **Session:** ID, Start, Ende, aktive Dauer, Filter, geplante Zahl unterschiedlicher Wörter, Status.
- **Attempt:** ID, Session-ID, Vokabel-ID, Richtung, Zeitpunkt, Eingabe, korrekt/falsch, fast-richtig-Status, Nutzerentscheidung, Zahl verwendeter Tipps.
- **GamificationState:** Punkte, Level, Abzeichen, Tagesziel und daraus abgeleitete Lernserie; berechenbare Werte nach Möglichkeit aus Versuchen ableiten.
- **PhotoImportDraft:** temporäre Vorschläge und Prüfstatus; darf vor abschließender Freigabe nicht als Vocabulary erscheinen.

## 6. Technische Leitplanken

- Native iPhone-Umsetzung bevorzugt; Architektur mit klar getrennten Komponenten für Oberfläche, Persistenz, CSV, Fotoerkennung, Bewertung, Planung, Statistik und Gamification.
- Agent prüft anhand der installierten iOS-Version des iPhone SE (2. Generation) geeignete Apple-Frameworks und legt Mindestversion und technische Wahl begründet fest. SwiftUI, lokale Persistenz und Vision sind Kandidaten, keine ungeprüfte Vorgabe.
- Keine Netzwerkübertragung von Fotos oder Vokabeln. Kamera-/Fotozugriff nur nach Nutzeraktion; Berechtigungen verständlich erklären.
- Kleine Displays, dynamische Schriftgrößen, VoiceOver-Beschriftungen, ausreichende Kontraste und reduzierte Bewegung berücksichtigen.
- CSV-Import atomar bzw. rückgängig machbar; bei Abbruch oder Fehler keine halb übernommenen Daten.
- Fehler verständlich und mit konkreter Zeilen- oder Eintragsangabe anzeigen.
- Tests für Datenmigration und Wiederherstellung vorsehen; kein stiller Datenverlust bei App-Updates.

## 7. Abnahmekriterien

- [ ] Englische und lateinische Vokabeln lassen sich in beiden Richtungen üben; Lernstände sind unabhängig.
- [ ] CSV-Vorlage importierbar; fehlerhafte Zeilen werden erklärt; Export und Reimport erhalten Vokabeln und beide Lernstände.
- [ ] CSV-Sicherung beschreibt klar, dass historische Einzelversuche nicht enthalten sein müssen.
- [ ] Fotoimport mit gedruckter Liste, Handschrift und Buchseite getestet; Vorschläge lassen sich einzeln korrigieren, bestätigen oder verwerfen.
- [ ] Ohne abschließende Foto-Freigabe werden keine Vorschläge als Vokabeln gespeichert; Abbruch verändert den Bestand nicht.
- [ ] Diktat über Systemtastatur und manuelle Eingabe funktionieren; erkannter Text ist vor Absenden editierbar.
- [ ] Tipp 1/2 zeigen einen bzw. zwei Buchstaben; Tippnutzung beeinflusst Lernstand und Punkte.
- [ ] „Fast richtig“ erfordert Nutzerentscheidung; als richtig gewertete Antwort zählt für die Quote, wird aber früher wiederholt.
- [ ] Bei 20 gewählten Wörtern werden 20 unterschiedliche Wörter ausgewählt, sofern vorhanden; Wiederholungen falscher Wörter kommen zusätzlich.
- [ ] Erst falsch, später richtig ergibt zwei Versuche und eine Richtigquote von 50 % für diese beiden Versuche.
- [ ] Tag/Woche/Monat, aktive Zeit, verschiedene Wörter und Richtigquote stimmen mit gespeicherten Versuchen überein.
- [ ] Punkte, Serie, Level, Tagesziel, Abzeichen und Animationen funktionieren, ohne Lernstatistik zu verfälschen.
- [ ] Oberfläche auf iPhone SE (2. Generation) mit geöffneter Tastatur nutzbar.
- [ ] Daten bleiben nach App-Neustart erhalten; Kernfunktionen ohne Konto und offline verfügbar.
- [ ] Quellcode, automatisierte Tests, Beispiel-CSV, Build-/Installationsanleitung und bekannte Grenzen werden geliefert.

## 8. Lieferumfang und Vorgehen für den Agenten

1. Zuerst installierte iOS-Version des Testgeräts und Entwicklungsumgebung feststellen; technische Architektur kurz dokumentieren.
2. Datenmodell und lokale Speicherung implementieren, danach CSV-Roundtrip samt Tests.
3. Training, getrennte Lernstände, Bewertung, Wiederholungen und Statistik implementieren.
4. Fotoerkennung und verpflichtende Prüfansicht implementieren; mit echten Fotos validieren.
5. Spielerische Elemente ergänzen und auf kleinem Display testen.
6. Automatisierte Tests und manuelle Abnahmefälle dokumentieren; keine Funktion als fertig markieren, die nur simuliert oder nicht am Gerät geprüft wurde.

## 9. Noch technische Parameter, keine offenen Kernentscheidungen

- Tatsächlich installierte iOS-Version auf dem iPhone SE (2. Generation).
- Konkrete Schwellen für „fast richtig“, Inaktivität, Wiederholungsintervalle, Wiederholungsbegrenzung, Punkte, Level und Abzeichen: Agent schlägt konservative, zentral konfigurierbare Werte vor, dokumentiert sie und testet Randfälle.
- Echte Beispielbilder für Druck, Handschrift und Buchseite zur Prüfung der Fotoerkennung. Ohne diese darf die Qualität für alle drei Formate nicht als verifiziert bezeichnet werden.
