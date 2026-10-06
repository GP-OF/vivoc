# vivoc: Schritt für Schritt zur eigenen Vokabel-App für das iPhone

Diese Checkliste führt dich von der Idee bis zu einer veröffentlichten App. Du brauchst noch keine Programmierkenntnisse. Arbeite die Punkte von oben nach unten ab und setze ein Häkchen, wenn das jeweils genannte Ergebnis vorliegt. Die nummerierten Schritte lassen sich später eindeutig besprechen, zum Beispiel: „Hilf mir bei Schritt 026.“

**Ausgangspunkt:** Dieses Repository enthält bisher nur eine README und diese Planung. Eine ausführbare App existiert noch nicht. Die Checkliste beschreibt die noch auszuführenden Arbeiten; leere Kästchen bedeuten offene Aufgaben.

**Empfohlener Weg:** Eine native iPhone-App mit **Swift**, **SwiftUI** und **SwiftData**. Swift ist die Programmiersprache, SwiftUI baut die Bedienoberfläche und SwiftData speichert strukturierte Daten auf dem Gerät. SwiftData setzt iOS 17 oder neuer voraus. Falls du ältere iPhones unterstützen möchtest, musst du vor dem Projektstart eine andere Speicherlösung wählen.

**Wichtig für die Werkzeuge:** Planung, Dokumentation und viele Änderungen am Quellcode sind hier in der Cloud möglich. Für den regulären Bau einer nativen iPhone-App, den iPhone-Simulator und die Apple-Werkzeuge brauchst du macOS mit Xcode, zum Beispiel auf einem eigenen oder gemieteten Mac. Diese Cloud-Umgebung ersetzt diesen Mac nicht. Plane außerdem Tests auf einem echten iPhone ein.

**Deine erste Version:** Eigene Vokabellisten anlegen, Wörter mit Übersetzungen speichern, Karteikarten abfragen, Antworten selbst bewerten und fällige Wörter später wiederholen. Die App funktioniert offline und ohne Benutzerkonto. Synchronisierung, KI, Abos und soziale Funktionen kommen bei Bedarf nach der ersten Veröffentlichung.

Die Reihenfolge ist bewusst in kleine Etappen unterteilt. Du musst nicht alles im Voraus beherrschen: Lerne zunächst das, was du für den nächsten Schritt brauchst. Die Veröffentlichung ist ein eigener Abschnitt; für eine auf deinem eigenen iPhone nutzbare App kannst du bereits vorher einen Meilenstein erreichen.

## Etappe 1 — Ziel und Rahmen festlegen

- [ ] **001 — Schreibe die Idee in einem Satz auf.** Beispiel: „vivoc hilft mir, meine eigenen Englisch-Vokabeln täglich fünf Minuten auf dem iPhone zu üben.“
  - **Warum:** Ein klarer Satz hilft dir zu entscheiden, welche Funktionen zum Ziel passen.
  - **Erledigt, wenn:** Der Satz in einer Planungsdatei, etwa `docs/APP-PLAN.md`, steht. Lege den Ordner bei Bedarf an.

- [ ] **002 — Beschreibe deine ersten Nutzer.** Entscheide zunächst zwischen einer konkreten Gruppe, etwa Schülern, Reisenden oder dir selbst.
  - **Warum:** Verschiedene Menschen benötigen unterschiedliche Wörter, Erklärungen und Bedienabläufe.
  - **Erledigt, wenn:** Eine Zielgruppe und ihr wichtigstes Lernproblem im App-Plan stehen.

- [ ] **003 — Lege die ersten Sprachen fest.** Wähle zum Beispiel Deutsch als Ausgangssprache und Englisch als Lernsprache; verwende für die erste Oberfläche Deutsch.
  - **Warum:** Ein konkretes Sprachenpaar macht Beispiele und Tests einfacher. Die Daten sollten die Sprachen trotzdem ausdrücklich speichern.
  - **Erledigt, wenn:** Ausgangssprache, Lernsprache und Sprache der Oberfläche dokumentiert sind.

- [ ] **004 — Beschreibe eine typische Nutzung.** Beispiel: „Ich lege zehn Wörter an, starte eine Übung und wiederhole morgen meine fälligen Wörter.“
  - **Warum:** Dieser Ablauf verbindet einzelne Funktionen zu einer tatsächlich brauchbaren App.
  - **Erledigt, wenn:** Du den Ablauf mit fünf bis acht kurzen Aktionen beschreiben kannst.

- [ ] **005 — Prüfe deine Arbeitsmittel.** Kläre, ob du Zugang zu einem Mac und zu einem iPhone hast. Prüfe auf Apples Xcode-Seite, welche macOS-Version die benötigte Xcode-Version voraussetzt.
  - **Warum:** Xcode läuft auf macOS. Ein Windows- oder Linux-Rechner allein reicht für diesen empfohlenen Entwicklungsweg nicht aus.
  - **Erledigt, wenn:** Dein Zugang zu einem kompatiblen Mac und einem Test-iPhone feststeht; andernfalls ist dieser Bedarf im Plan ausdrücklich offen.

- [ ] **006 — Lege Zeit und Kostenrahmen fest.** Plane kurze, regelmäßige Lernblöcke und notiere mögliche Kosten für Mac-Zugang und spätere Apple-Mitgliedschaft.
  - **Warum:** Lernen, Fehlersuche und Tests brauchen Zeit. Ein realistischer Rahmen verhindert, dass du zu viele Funktionen gleichzeitig beginnst.
  - **Erledigt, wenn:** Dein wöchentlicher Zeitrahmen und dein Kostenlimit im Plan stehen.

## Etappe 2 — Eine kleine erste Version planen

- [ ] **007 — Schreibe die Pflichtfunktionen auf.** Für Version 1: Listen anlegen, Wörter hinzufügen/bearbeiten/löschen, Karten abfragen, Antworten bewerten, Wiederholungen planen und Daten lokal speichern.
  - **Warum:** Diese kleinste sinnvoll nutzbare Version heißt häufig MVP, kurz für „Minimum Viable Product“. Sie löst bereits das wichtigste Problem.
  - **Erledigt, wenn:** Eine verbindliche Liste der Pflichtfunktionen im App-Plan steht.

- [ ] **008 — Lege eine Liste für spätere Ideen an.** Verschiebe Anmeldung, Geräte-Synchronisierung, Aussprache, Import, Benachrichtigungen, KI und Bezahlung zunächst dorthin.
  - **Warum:** Jede Zusatzfunktion bringt weitere Bedienabläufe, technische Abhängigkeiten und Tests mit sich.
  - **Erledigt, wenn:** Pflichtfunktionen und spätere Ideen getrennt dokumentiert sind.

- [ ] **009 — Entscheide, woher Vokabeln kommen.** Starte mit selbst eingegebenen Wörtern und selbst erstellten Beispielen. Übernimm keine fremden Wörterbücher ungeprüft.
  - **Warum:** Inhalte und Beispielsätze können Nutzungsbedingungen oder Urheberrechten unterliegen. Eigene Eingaben benötigen zunächst keine externe Datenquelle.
  - **Erledigt, wenn:** Die Datenquelle festgelegt ist und eventuelle fremde Inhalte eine dokumentierte Nutzungserlaubnis haben.

- [ ] **010 — Lege fest, woran du Version 1 erkennst.** Beispiel: „Zehn Wörter anlegen, App beenden, erneut öffnen, Wörter wiederfinden und eine vollständige Übung abschließen.“
  - **Warum:** Solche Abnahmekriterien beschreiben beobachtbares Verhalten. „Die App funktioniert“ wäre zu ungenau.
  - **Erledigt, wenn:** Für jede Pflichtfunktion mindestens ein konkretes Erfolgskriterium notiert ist.

- [ ] **011 — Teile die Arbeit in Meilensteine.** Verwende: Planung fertig → Oberfläche mit Beispieldaten → Speicherung → Lernfunktion → iPhone-Tests → Veröffentlichung.
  - **Warum:** Kleine Zwischenziele machen Fortschritt sichtbar und Fehler leichter eingrenzbar.
  - **Erledigt, wenn:** Jeder Meilenstein ein überprüfbares Ergebnis besitzt. Plane Termine erst, wenn du deinen Arbeitsaufwand besser einschätzen kannst.

## Etappe 3 — Lernablauf und Wiederholungen definieren

- [ ] **012 — Wähle für Version 1 genau eine Abfragerichtung.** Zum Beispiel: deutsches Wort anzeigen, englische Übersetzung erinnern.
  - **Warum:** Die umgekehrte Richtung ist eine eigene Lernleistung. Ein gemeinsamer Fortschritt für beide Richtungen wäre irreführend.
  - **Erledigt, wenn:** Die Richtung im Plan steht. Eine spätere zweite Richtung bekommt eigenen Lernfortschritt.

- [ ] **013 — Definiere die Karteikarten-Schritte.** Erst das Wort zeigen, dann die Lösung auf Wunsch aufdecken, anschließend „Gewusst“ oder „Noch üben“ auswählen.
  - **Warum:** Das aktive Erinnern übt den Abruf. Die Selbstbewertung vermeidet am Anfang komplizierte Regeln für Schreibfehler und mehrere richtige Übersetzungen.
  - **Erledigt, wenn:** Reihenfolge und Beschriftungen eindeutig sind; Bewerten ist erst nach dem Aufdecken möglich.

- [ ] **014 — Wähle eine einfache Wiederholungsregel.** Ein möglicher Start: nach erfolgreicher Bewertung in 1, 3, 7 und danach jeweils 14 Tagen wiederholen; bei „Noch üben“ auf die erste Stufe zurücksetzen und am nächsten Tag erneut einplanen.
  - **Warum:** „Spaced Repetition“ bedeutet Wiederholung mit zeitlichen Abständen. Diese Regel ist ein verständlicher Einstieg und keine Garantie für einen optimalen Lernalgorithmus.
  - **Erledigt, wenn:** Intervalle, maximale Stufe und Verhalten bei beiden Bewertungen schriftlich feststehen.

- [ ] **015 — Definiere neue und fällige Wörter.** Neue Wörter sind sofort lernbar. Bereits geübte Wörter sind fällig, sobald ihr Wiederholungsdatum erreicht ist; noch nicht fällige Wörter werden im normalen Ablauf ausgelassen.
  - **Warum:** Die App muss zuverlässig entscheiden können, welche Karten heute drankommen.
  - **Erledigt, wenn:** Du für ein neues, ein überfälliges und ein erst morgen fälliges Wort das erwartete Verhalten erklären kannst.

- [ ] **016 — Lege die Größe und Reihenfolge einer Übung fest.** Beginne beispielsweise mit höchstens zehn verschiedenen Wörtern: zuerst die am längsten fälligen, dann neue Wörter in einer stabilen Reihenfolge.
  - **Warum:** Kurze Übungen sind überschaubar. Eine festgelegte Sortierung lässt sich leichter testen als zufälliges Verhalten.
  - **Erledigt, wenn:** Auswahl, Reihenfolge und Verhalten bei weniger als zehn verfügbaren Wörtern definiert sind.

- [ ] **017 — Entscheide, was bei einer falschen Antwort in derselben Übung passiert.** Einfacher Start: Die Karte bleibt für morgen vorgemerkt, die aktuelle Übung geht zur nächsten Karte weiter.
  - **Warum:** Endlose Wiederholungen desselben Wortes können eine Übung blockieren. Wiederholungen innerhalb einer Sitzung kannst du später gezielt ergänzen.
  - **Erledigt, wenn:** Jedes ausgewählte Wort höchstens einmal bewertet wird und die Übung sicher enden kann.

- [ ] **018 — Lege fest, wie Unterbrechungen behandelt werden.** Speichere jede abgeschlossene Bewertung sofort; nach erneutem Öffnen kann eine neue Übung aus den dann fälligen Wörtern beginnen.
  - **Warum:** Auf dem iPhone können Apps jederzeit unterbrochen oder beendet werden. Bereits geleistete Arbeit soll erhalten bleiben.
  - **Erledigt, wenn:** Verhalten bei App-Wechsel, Abbruch und erneutem Start dokumentiert ist.

- [ ] **019 — Bestimme eine einfache Ergebnisanzeige.** Zeige nach der Übung die Anzahl bewerteter Wörter sowie „Gewusst“ und „Noch üben“. Zähle neue Wörter nicht automatisch als gelernt.
  - **Warum:** Nutzer sollen verstehen, was tatsächlich passiert ist. Große Statistiken sind für den ersten funktionierenden Lernablauf nicht nötig.
  - **Erledigt, wenn:** Die Bedeutung jeder angezeigten Zahl feststeht.

## Etappe 4 — Bildschirme und Bedienung skizzieren

- [ ] **020 — Liste die notwendigen Bildschirme auf.** Start: Listenübersicht, Wörter einer Liste, Wortformular, Lernkarte und Übungsergebnis.
  - **Warum:** Ein Bildschirm übernimmt jeweils eine klar verständliche Aufgabe.
  - **Erledigt, wenn:** Für jeden Bildschirm sein Zweck und der Weg dorthin notiert sind.

- [ ] **021 — Zeichne die Listenübersicht auf Papier.** Plane Listennamen, Anzahl der Wörter, eine neue Liste und den Einstieg in eine bestehende Liste.
  - **Warum:** Eine Skizze ist schnell geändert, bevor Programmierarbeit entsteht.
  - **Erledigt, wenn:** Ein anderer Mensch anhand der Skizze eine Liste auswählen oder anlegen kann.

- [ ] **022 — Zeichne die Wortübersicht und das Eingabeformular.** Plane Wort, Übersetzung, optionalen Beispielsatz sowie Speichern und Abbrechen.
  - **Warum:** Die häufige Eingabe muss auf einem kleinen Bildschirm bequem funktionieren, auch wenn die Tastatur eingeblendet ist.
  - **Erledigt, wenn:** Alle Pflichtfelder und Aktionen erkennbar sind; lange Texte haben Platz.

- [ ] **023 — Zeichne Lernkarte und Ergebnis.** Trenne Wort, Lösung und Bewertungsaktionen. Zeige außerdem den Fortschritt der laufenden Übung, etwa „3 von 10“.
  - **Warum:** Eine klare Anordnung hilft beim Lernen und verhindert versehentliche Bewertungen.
  - **Erledigt, wenn:** Der komplette Ablauf aus Schritt 013 in den Skizzen erkennbar ist.

- [ ] **024 — Plane leere Zustände und Fehlermeldungen.** Beispiele: noch keine Liste, noch kein Wort, heute nichts fällig, Wort ohne Übersetzung und fehlgeschlagenes Speichern.
  - **Warum:** Eine App braucht auch dann verständliche Antworten, wenn keine Inhalte vorhanden sind oder etwas schiefgeht.
  - **Erledigt, wenn:** Jeder dieser Fälle einen hilfreichen Text und einen sinnvollen nächsten Schritt hat.

- [ ] **025 — Plane gut lesbare und bedienbare Elemente.** Nutze deutliche Beschriftungen, ausreichende Kontraste, skalierbaren Text und große Schaltflächen; für Berührungsflächen sind ungefähr 44 × 44 Punkte ein gängiger Apple-Richtwert.
  - **Warum:** Menschen haben unterschiedliche Seh- und Motorikfähigkeiten. Informationen sollten außerdem nicht ausschließlich durch Farbe vermittelt werden.
  - **Erledigt, wenn:** Deine Skizzen ohne winzige Texte und reine Farbhinweise auskommen.

- [ ] **026 — Gehe die Skizzen mit einer Person durch.** Bitte sie, eine Liste anzulegen und drei Wörter zu üben, ohne ihr die Bedienung vorzusagen.
  - **Warum:** Du erkennst so Missverständnisse, die du als Ersteller leicht übersiehst.
  - **Erledigt, wenn:** Du mindestens die beobachteten Stolperstellen notiert und die Skizzen entsprechend überarbeitet hast.

## Etappe 5 — Werkzeuge auf dem Mac einrichten

- [ ] **027 — Installiere eine passende stabile Xcode-Version.** Verwende den Mac App Store oder Apples offizielle Downloads, starte Xcode und installiere die angebotenen erforderlichen Komponenten.
  - **Warum:** Xcode enthält Editor, Compiler, Simulator und Werkzeuge zum Bauen und Prüfen einer iPhone-App. Der Compiler übersetzt deinen Swift-Code in ein ausführbares Programm.
  - **Erledigt, wenn:** Xcode vollständig startet und ein passender iOS-Simulator verfügbar ist.

- [ ] **028 — Stelle dasselbe Repository auf dem Mac bereit.** Klone `GP-OF/vivoc` oder verwende einen vorhandenen Checkout; vermeide mehrere unübersichtliche Kopien.
  - **Warum:** Das Repository ist die gemeinsame Ablage für Quellcode und Dokumentation. Bereits vorhandene Dateien sollen erhalten bleiben.
  - **Erledigt, wenn:** Du `README.md` und diese Checkliste lokal öffnen kannst. Cloud-Aufgaben verwenden ebenfalls den bestehenden Checkout; ein zusätzlicher Git-Worktree ist hierfür nicht erforderlich.

- [ ] **029 — Lerne die drei wichtigsten Git-Aktionen.** Prüfe Änderungen mit `git status` und `git diff`, speichere einen zusammenhängenden Stand mit einem Commit und übertrage ihn bewusst mit einem Push.
  - **Warum:** Git macht Änderungen nachvollziehbar und ältere Stände wiederherstellbar. Ein lokaler Commit ist noch keine Sicherung auf GitHub.
  - **Erledigt, wenn:** Du den Unterschied zwischen Arbeitsdateien, lokalem Commit und remote gespeichertem Stand erklären kannst.

- [ ] **030 — Lege eine passende `.gitignore` an.** Schließe Build-Ausgaben, `DerivedData`, persönliche Xcode-Zustände und lokale Geheimnisse aus; behalte Swift-Dateien, Projektkonfiguration und gemeinsame Ressourcen im Repository.
  - **Warum:** Andere sollen das Projekt nachbauen können, ohne deine temporären Dateien oder Zugangsdaten zu erhalten.
  - **Erledigt, wenn:** `git status` sinnvolle Projektdateien anzeigt und keine lokalen Build-Verzeichnisse oder privaten Schlüssel zur Übertragung anbietet.

- [ ] **031 — Erstelle das iOS-App-Projekt im Repository.** Wähle in Xcode die iOS-App-Vorlage, Swift als Sprache und SwiftUI als Oberfläche; aktiviere passende Unit- und UI-Testziele, falls die Vorlage sie anbietet.
  - **Warum:** Die Vorlage erzeugt einen gültigen Einstiegspunkt und die Einstellungen, die Xcode zum Bauen benötigt. Ein Testziel bündelt ausführbare Tests.
  - **Erledigt, wenn:** Das Projekt etwa unter `ios/` liegt und Xcode es öffnen kann. Verwende das vorhandene Git-Repository statt eines zweiten darin.

- [ ] **032 — Lege Kennung und unterstützte iOS-Version fest.** Nutze eine eigene eindeutige Bundle-ID, zum Beispiel nach dem Muster `de.deinname.vivoc`, und für SwiftData mindestens iOS 17 als Deployment Target.
  - **Warum:** Die Bundle-ID identifiziert die App. Das Deployment Target legt die älteste unterstützte iOS-Version fest; es ist nicht dasselbe wie die installierte Simulator-Version.
  - **Erledigt, wenn:** Deine tatsächliche Kennung und Mindestversion in den Projekteinstellungen stehen und die verwendeten APIs dazu passen.

- [ ] **033 — Starte die unveränderte Vorlage im Simulator.** Wähle ein iPhone-Modell als Ausführungsziel und benutze Run in Xcode.
  - **Warum:** Ein erfolgreicher Start zeigt, dass die Grundinstallation funktioniert, bevor eigener Code zusätzliche Fehler verursachen kann.
  - **Erledigt, wenn:** Der erste Bildschirm im Simulator sichtbar ist und kein Build- oder Startfehler offen bleibt.

## Etappe 6 — Die nötigen Grundlagen praktisch lernen

- [ ] **034 — Übe Swift-Werte und Datentypen.** Lerne `let` für unveränderliche Werte, `var` für veränderliche Werte sowie `String`, `Int` und `Bool` anhand eines Beispielworts.
  - **Warum:** Wörter, Zähler und Ja/Nein-Zustände sind die Bausteine deiner App-Daten.
  - **Erledigt, wenn:** Du ein Wort, seine Übersetzung und einen Übungszähler selbst darstellen kannst, etwa in einem kleinen separaten Übungsprojekt.

- [ ] **035 — Übe Bedingungen, Funktionen und Listen.** Schreibe eine Funktion, die aus mehreren Beispielwörtern diejenigen auswählt, deren Wiederholungsdatum erreicht ist.
  - **Warum:** Eine Funktion bündelt einen Ablauf, Bedingungen treffen Entscheidungen und Arrays halten mehrere Elemente zusammen.
  - **Erledigt, wenn:** Du erklären kannst, was die Funktion erhält und welches Ergebnis sie zurückgibt.

- [ ] **036 — Lerne Strukturen, Klassen und optionale Werte kennen.** Verwende ein kleines Wortmodell und einen optionalen Beispielsatz; mache dir klar, dass spätere SwiftData-Modelle Klassen verwenden.
  - **Warum:** Eigene Datentypen halten zusammengehörige Informationen zusammen. Ein Optional beschreibt, dass ein Wert fehlen darf, ohne einen erfundenen Ersatz einzutragen.
  - **Erledigt, wenn:** Dein Beispiel einen vorhandenen und einen fehlenden Beispielsatz sicher verarbeitet.

- [ ] **037 — Baue eine kleine SwiftUI-Ansicht.** Verwende `Text`, `Button`, `TextField`, `List` und `NavigationStack` mit wenigen Beispieldaten.
  - **Warum:** SwiftUI beschreibt, was auf dem Bildschirm erscheinen soll. Diese Elemente decken große Teile deiner ersten Oberfläche ab.
  - **Erledigt, wenn:** Du einen Text ändern, eine Schaltfläche drücken und zu einer zweiten Ansicht wechseln kannst.

- [ ] **038 — Verstehe Zustand und Datenbindung.** Übe `@State` und `@Binding` mit einem Eingabefeld und einer aufklappbaren Lösung.
  - **Warum:** Zustand ist veränderliche Information, die eine Ansicht beeinflusst. Eine Bindung verbindet ein Bedienelement mit dem Wert, den es ändern soll.
  - **Erledigt, wenn:** Du erklären kannst, warum der Bildschirm nach einer Eingabe oder einem Klick automatisch aktualisiert wird.

- [ ] **039 — Übe Fehlersuche in Xcode.** Lerne Fehlermeldungen, Konsole und einen Breakpoint kennen; halte eine kleine Funktion an und prüfe ihre Werte.
  - **Warum:** Ein Breakpoint pausiert die Ausführung an einer bestimmten Stelle. So kannst du Ursachen untersuchen, statt nur Änderungen zu raten.
  - **Erledigt, wenn:** Du einen kleinen absichtlich verursachten Fehler in deinem Übungsprojekt finden und beheben kannst.

## Etappe 7 — Daten und Code übersichtlich strukturieren

- [ ] **040 — Definiere das Listenmodell.** Plane eindeutige ID, Namen, Ausgangssprache, Lernsprache und Erstellungsdatum einer Liste.
  - **Warum:** Eine ID identifiziert eine Liste auch nach einer Umbenennung. Der Name allein wäre dafür ungeeignet.
  - **Erledigt, wenn:** Felder und erlaubte Werte im App-Plan dokumentiert sind.

- [ ] **041 — Definiere das Wortmodell.** Plane ID, zugehörige Liste, Ausgangswort, Übersetzung und optionalen Beispielsatz. Speichere Inhalte als Unicode-Text.
  - **Warum:** Unicode unterstützt Umlaute und verschiedene Schriftsysteme. Die Listenbeziehung ordnet Wörter zuverlässig zu.
  - **Erledigt, wenn:** Beispielwörter mit Umlauten und längeren Texten in dein Modell passen.

- [ ] **042 — Definiere den Lernfortschritt.** Plane pro Wort die aktuelle Wiederholungsstufe, das nächste Fälligkeitsdatum und bei Bedarf den Zeitpunkt der letzten Bewertung.
  - **Warum:** Wortinhalt und Lernfortschritt erfüllen verschiedene Aufgaben, selbst wenn du sie anfangs in einem gemeinsamen SwiftData-Modell speicherst.
  - **Erledigt, wenn:** Die Regeln aus Etappe 3 vollständig mit diesen Feldern abbildbar sind.

- [ ] **043 — Lege Eingabe- und Löschregeln fest.** Wort und Übersetzung dürfen nach Entfernen äußerer Leerzeichen nicht leer sein. Beim Löschen einer Liste sollen ihre Wörter und Lernstände mit gelöscht werden.
  - **Warum:** Klare Regeln vermeiden unbrauchbare Einträge und verwaiste Daten. Entscheide auch, ob identische Wörter in derselben Liste erlaubt sind oder einen Hinweis erhalten.
  - **Erledigt, wenn:** Pflichtfelder, Duplikatverhalten und Löschfolgen schriftlich feststehen.

- [ ] **044 — Lege das Verhalten beim Bearbeiten fest.** Ein korrigierter Beispielsatz kann den Fortschritt behalten; bei inhaltlich geändertem Wort oder geänderter Übersetzung bietet sich ein Zurücksetzen an.
  - **Warum:** Ein guter Lernstand für ein anderes Wort wäre irreführend. Eine Entscheidung verhindert später widersprüchliches Verhalten.
  - **Erledigt, wenn:** Die genaue Regel im Plan steht und die Oberfläche einen nötigen Hinweis vorsieht.

- [ ] **045 — Teile den Code nach Aufgaben auf.** Lege etwa `Models`, `Views` und `Learning` an; sammle die Wiederholungsberechnung in einer eigenen Funktion oder einem kleinen Dienst.
  - **Warum:** Eine Trennung von Daten, Oberfläche und Lernregeln macht Änderungen und Tests leichter. Für die erste App genügt eine einfache Struktur.
  - **Erledigt, wenn:** Du für jede wichtige Datei ihren Zweck erklären kannst und die Lernregel ohne Bildschirm ausführbar ist.

## Etappe 8 — Oberfläche zunächst mit Beispieldaten bauen

- [ ] **046 — Erstelle wenige lokale Beispieldaten.** Nutze zwei Listen und ungefähr zehn selbst erstellte Wörter, darunter ein langes Wort und eines mit Umlauten.
  - **Warum:** Beispiele machen die Oberfläche früh sichtbar, ohne dass Speicherung und Lernalgorithmus bereits fertig sein müssen.
  - **Erledigt, wenn:** Die Daten in einer Vorschau oder einem Entwicklungsmodus verfügbar sind; sie gelangen später nicht ungefragt in Nutzerdaten.

- [ ] **047 — Baue die Listenübersicht.** Zeige Namen und Anzahl der Wörter; ergänze Navigation und die leere Ansicht aus deiner Skizze.
  - **Warum:** Das ist der Einstiegspunkt in die App. Ein verständlicher leerer Zustand erklärt neuen Nutzern die erste Aktion.
  - **Erledigt, wenn:** Du eine Beispielliste öffnen kannst und auch eine Übersicht ohne Listen sinnvoll aussieht.

- [ ] **048 — Baue die Wortübersicht einer Liste.** Zeige Ausgangswort und Übersetzung sowie Aktionen zum Hinzufügen und Bearbeiten.
  - **Warum:** Nutzer müssen ihre Lerninhalte vor einer Übung prüfen und pflegen können.
  - **Erledigt, wenn:** Unterschiedliche Listen die jeweils richtigen Beispielwörter anzeigen.

- [ ] **049 — Baue das Wortformular mit Prüfung.** Entferne äußere Leerzeichen, verhindere leere Pflichtfelder und ermögliche Abbrechen ohne Übernahme.
  - **Warum:** Eingabeprüfung heißt Validierung. Sie hält unvollständige Daten aus der Speicherung fern und erklärt dem Nutzer die nötige Korrektur.
  - **Erledigt, wenn:** Gültige Eingaben übernommen und ungültige Eingaben verständlich zurückgewiesen werden.

- [ ] **050 — Baue die Lernkarte mit einer Beispielvokabel.** Verberge die Lösung zunächst und ermögliche erst nach dem Aufdecken eine Bewertung.
  - **Warum:** Du prüfst den wichtigsten Bedienablauf zunächst unabhängig von Wiederholung und Speicherung.
  - **Erledigt, wenn:** Aufdecken und beide Bewertungsaktionen im Simulator funktionieren; beim Wechsel zur nächsten Karte ist die Lösung wieder verborgen.

- [ ] **051 — Baue die Ergebnisansicht und den Rückweg.** Zeige zunächst nachvollziehbare Beispielzahlen und einen Weg zurück zur Liste.
  - **Warum:** Eine Übung braucht einen klaren Abschluss und darf den Nutzer nicht in einer Sackgasse lassen.
  - **Erledigt, wenn:** Der komplette Bildschirmablauf im Simulator durchgehbar ist. Markiere Beispielzahlen als Entwicklungsdaten, bis echte Ergebnisse angebunden sind.

## Etappe 9 — Lokale Speicherung einbauen

- [ ] **052 — Richte SwiftData ein.** Ergänze die geeigneten Modellklassen, ihre Beziehungen und einen persistenten `ModelContainer` am App-Einstieg.
  - **Warum:** Der Container verwaltet den Datenspeicher. Nur eine Sammlung im Arbeitsspeicher wäre nach dem Beenden der App verloren.
  - **Erledigt, wenn:** Die App mit dem echten lokalen Speicher startet und Fehler beim Öffnen des Speichers sichtbar behandelt werden.

- [ ] **053 — Verbinde die Listenansicht mit gespeicherten Daten.** Ersetze die Beispielquelle durch echte Abfragen und speichere neue Listen.
  - **Warum:** Die Oberfläche soll den tatsächlichen Datenbestand anzeigen und nach Änderungen automatisch aktualisieren.
  - **Erledigt, wenn:** Eine neu angelegte Liste erscheint und nach einem vollständigen Neustart erhalten bleibt.

- [ ] **054 — Speichere neue Wörter und ihre Zuordnung.** Verbinde das Formular mit dem Datenkontext und der gewählten Liste; behandle Speicherfehler statt sie still zu ignorieren.
  - **Warum:** Ein Datenkontext verwaltet Änderungen an Modellen. Ein Erfolgshinweis darf erst erscheinen, wenn das Speichern gelungen ist.
  - **Erledigt, wenn:** Ein Wort nach einem Neustart in der richtigen Liste wieder sichtbar ist.

- [ ] **055 — Ergänze Bearbeiten und Löschen.** Setze die Regeln aus Schritten 043 und 044 um und bestätige insbesondere das Löschen ganzer Listen.
  - **Warum:** Nutzer müssen Fehler korrigieren können. Die Bestätigung schützt vor versehentlichem Verlust vieler Wörter.
  - **Erledigt, wenn:** Änderungen und Löschungen einen Neustart überstehen und keine zugehörigen Daten zurückbleiben.

- [ ] **056 — Prüfe den Offline-Betrieb.** Verwende die App ohne Internet und wiederhole Anlegen, Bearbeiten, Speichern und Öffnen.
  - **Warum:** Dein erster Funktionsumfang verspricht lokale Nutzung. Dazu dürfen diese Abläufe keinen Server benötigen.
  - **Erledigt, wenn:** Die Kernfunktionen ohne Verbindung arbeiten und nach einem Neustart alle erwarteten Daten vorhanden sind.

- [ ] **057 — Dokumentiere die Grenzen der Speicherung.** Halte fest: Version 1 hat keine eigene Synchronisierung oder Exportfunktion; beim Löschen der App können lokale Daten verloren gehen. Verlasse dich nicht auf eine ungetestete Gerätesicherung.
  - **Warum:** Lokale Speicherung ist einfach, bietet aber nicht automatisch eine vom Nutzer kontrollierte Datensicherung.
  - **Erledigt, wenn:** Diese Grenze verständlich in den geplanten Hilfeinformationen steht und Backup/Export auf der Liste für spätere Versionen steht.

## Etappe 10 — Den echten Lernablauf implementieren

- [ ] **058 — Implementiere die Auswahl der Übungskarten.** Verwende die Regeln für neue und fällige Wörter, Reihenfolge und Höchstzahl aus Etappe 3.
  - **Warum:** Die Kartenauswahl bestimmt, was die App tatsächlich trainiert. Sie sollte getrennt von der Darstellung nachvollziehbar sein.
  - **Erledigt, wenn:** Ein Beispieldatenbestand mit bekannten Fälligkeitsdaten genau die erwarteten Karten liefert.

- [ ] **059 — Implementiere die Berechnung des nächsten Termins.** Übergebe Bewertung, bisherige Stufe und ein ausdrücklich übergebenes aktuelles Datum an die Berechnungsfunktion.
  - **Warum:** Eine Funktion mit übergebenem Datum lässt sich testen, ohne tatsächlich Tage warten zu müssen. Verwende Kalenderberechnungen statt der Annahme, jeder Kalendertag dauere genau 24 Stunden.
  - **Erledigt, wenn:** Beide Bewertungen die Regeln aus Schritt 014 erfüllen und die höchste Stufe sicher behandelt wird.

- [ ] **060 — Verbinde die Bewertung mit dem Speichern.** Aktualisiere den Fortschritt nach jeder Antwort und verhindere eine zweite Übernahme derselben Karte durch schnelles mehrfaches Tippen.
  - **Warum:** Doppeltes Speichern kann Stufen überspringen und Ergebniszahlen verfälschen. Eine fehlgeschlagene Speicherung darf keine erfolgreich abgeschlossene Bewertung vortäuschen.
  - **Erledigt, wenn:** Pro Karte genau eine erfolgreiche Bewertung zählt und der neue Lernstand einen Neustart übersteht.

- [ ] **061 — Implementiere Beginn, Fortschritt und Ende einer Übung.** Verwalte die ausgewählten Karten, den aktuellen Index und die tatsächlichen Bewertungen; beende nach der letzten Karte.
  - **Warum:** Eine feste Kartenauswahl für die laufende Übung verhindert, dass das Aktualisieren eines Termins die Sitzung unerwartet verändert.
  - **Erledigt, wenn:** Übungen mit einer, drei und zehn Karten korrekt enden und die Ergebniszahlen stimmen.

- [ ] **062 — Behandle Abbruch und leere Auswahl.** Erlaube einen verständlichen Rückweg; zeige bei null verfügbaren Karten „Heute nichts fällig“ statt einer leeren Lernkarte.
  - **Warum:** Ein normaler Sonderfall soll sich wie ein fertiger Teil der App anfühlen. Bereits gespeicherte Bewertungen bleiben nach einem Abbruch bestehen.
  - **Erledigt, wenn:** Beide Abläufe ohne Absturz, falsche Zähler oder verlorene Bewertungen funktionieren.

- [ ] **063 — Prüfe Datumsgrenzen.** Lege fest, ob Fälligkeit nach lokalem Kalendertag oder genauem Zeitpunkt gilt, und teste Tageswechsel sowie Sommerzeit anhand künstlich gesetzter Daten.
  - **Warum:** Ein iPhone kann in verschiedenen Zeitzonen genutzt werden. Unklare Datumsregeln führen zu zu frühen oder fehlenden Wiederholungen.
  - **Erledigt, wenn:** Die Regel dokumentiert ist und Auswahl und Terminberechnung dieselbe Regel verwenden.

## Etappe 11 — Mit automatischen Tests absichern

- [ ] **064 — Schreibe Tests für die Wiederholungsregel.** Teste jede Stufe, „Noch üben“, die höchste Stufe und die Datumsfälle aus Schritt 063.
  - **Warum:** Ein Unit-Test prüft einen kleinen Teil des Codes mit festgelegten Eingaben und erwarteten Ergebnissen. Er erkennt unbeabsichtigte Änderungen an den Lernregeln.
  - **Erledigt, wenn:** Die Tests tatsächlich ausgeführt werden und bei einer absichtlich falschen Berechnung fehlschlagen.

- [ ] **065 — Schreibe Tests für die Kartenauswahl.** Prüfe neue, überfällige und zukünftige Wörter, die Höchstzahl, Sortierung und eine leere Liste.
  - **Warum:** Die App kann optisch funktionieren und trotzdem die falschen Wörter auswählen. Diese Tests prüfen ihr Lernverhalten direkt.
  - **Erledigt, wenn:** Alle Fälle mit festen Beispieldaten die erwarteten Karten liefern.

- [ ] **066 — Teste Speicherung und Löschbeziehungen getrennt.** Nutze einen isolierten Testspeicher, prüfe Wortzuordnung, Änderungen und das Löschen einer Liste einschließlich ihrer Wörter.
  - **Warum:** Tests sollen reproduzierbar sein und niemals deine echten Lerndaten verändern. Ein reiner Speicher-im-RAM-Test ersetzt außerdem nicht den Neustarttest mit dauerhaftem Speicher.
  - **Erledigt, wenn:** Die isolierten Tests bestehen und die manuelle Prüfung aus Etappe 9 weiterhin erfolgreich ist.

- [ ] **067 — Schreibe einen UI-Test für den Hauptablauf.** Lass den Test eine Liste anlegen, ein Wort speichern, die Lernkarte öffnen, die Lösung aufdecken und bewerten.
  - **Warum:** Ein UI-Test bedient die App ähnlich wie ein Mensch. Er prüft, ob Navigation, Oberfläche und Logik zusammenarbeiten.
  - **Erledigt, wenn:** Der Ablauf von einem definierten leeren Teststand bis zur Ergebnisanzeige automatisch durchläuft.

- [ ] **068 — Halte die tatsächlichen Testergebnisse fest.** Notiere Datum, Testumgebung, ausgeführte Tests, Fehler und übersprungene Prüfungen, etwa in `docs/TESTPROTOKOLL.md`.
  - **Warum:** Ein grüner Build sagt nur, dass die App gebaut werden konnte. Er beweist weder, dass Tests liefen, noch dass Nutzerabläufe stimmen.
  - **Erledigt, wenn:** Keine Pflichtprüfung ungeklärt fehlschlägt und nicht ausgeführte Prüfungen eindeutig als offen markiert sind.

## Etappe 12 — Auf einem echten iPhone prüfen

- [ ] **069 — Richte die Ausführung auf deinem Gerät ein.** Melde dich in Xcode mit deinem Apple Account an, wähle dein Team, verbinde das iPhone und befolge die nötigen Vertrauens- und Entwicklermodus-Schritte.
  - **Warum:** Code Signing verknüpft die App mit einer Entwickleridentität. Testen auf eigenen Geräten ist unter Einschränkungen auch mit einem kostenlosen Account möglich; TestFlight und App-Store-Verteilung benötigen das passende kostenpflichtige Programm.
  - **Erledigt, wenn:** Die App direkt aus Xcode auf deinem iPhone startet. Speichere Zugangsdaten und Signierschlüssel niemals im Repository.

- [ ] **070 — Prüfe den kompletten Hauptablauf auf dem iPhone.** Lege zehn Wörter an, beende die App vollständig, öffne sie erneut und führe eine Übung aus.
  - **Warum:** Simulator und echtes Gerät unterscheiden sich unter anderem bei Bedienung, Lebenszyklus und Geschwindigkeit.
  - **Erledigt, wenn:** Alle Erfolgskriterien aus Schritt 010 auch auf dem echten Gerät erfüllt sind.

- [ ] **071 — Teste Eingaben und Bildschirmgrößen.** Prüfe Tastatur, lange Wörter, Umlaute, große Schrift, ein kleines iPhone und ein größeres Modell im Simulator.
  - **Warum:** Ein abgeschnittenes Eingabefeld oder verdeckter Speichern-Button kann die App unbenutzbar machen.
  - **Erledigt, wenn:** Wichtige Inhalte und Aktionen in allen gewählten Größen erreichbar und verständlich sind.

- [ ] **072 — Prüfe Dunkelmodus und VoiceOver.** Schalte den Dunkelmodus um und bediene den Hauptablauf mit Apples Bildschirmlesefunktion VoiceOver.
  - **Warum:** Barrierefreiheit betrifft tatsächliche Nutzung. Buttons brauchen verständliche Namen und die Lösung darf vor dem Aufdecken auch für VoiceOver nicht zugänglich sein.
  - **Erledigt, wenn:** Die Abfrage ohne visuelle Orientierung bedienbar ist und Texte in beiden Darstellungen lesbar bleiben.

- [ ] **073 — Teste Unterbrechungen und schnelle Eingaben.** Wechsle während einer Übung die App, sperre das Gerät, starte neu und tippe schnell mehrfach auf Bewertungsaktionen.
  - **Warum:** Diese Alltagssituationen decken doppelte Bewertungen und verlorene Zustände auf.
  - **Erledigt, wenn:** Die Regeln aus Schritten 018 und 060 eingehalten werden und kein Absturz entsteht.

- [ ] **074 — Prüfe einen größeren Datenbestand.** Erzeuge in einer getrennten Testinstallation beispielsweise mehrere Hundert eigene Testwörter und teste Listenanzeige, Eingabe und Übungsstart.
  - **Warum:** Mit zehn Wörtern bleibt eine langsame Datenabfrage leicht unbemerkt. Die Testdaten gehören nicht automatisch in die veröffentlichte App.
  - **Erledigt, wenn:** Die Kernabläufe weiterhin flüssig wirken; messbare Verzögerungen sind untersucht und gegebenenfalls mit Xcodes Instruments analysiert.

- [ ] **075 — Lass eine Person die echte App ausprobieren.** Gib nur die Aufgabe vor, etwa „Lege fünf Wörter an und übe sie“, und beobachte die Nutzung.
  - **Warum:** Funktionierender Code garantiert noch keine verständliche Bedienung. Dieser Test ergänzt die Prüfung deiner frühen Skizzen.
  - **Erledigt, wenn:** Blockierende Stolperstellen behoben sind und übrige Wünsche als spätere Ideen erfasst sind.

## Etappe 13 — Eine robuste erste Version fertigstellen

- [ ] **076 — Gleiche die App mit den Pflichtfunktionen ab.** Gehe die Kriterien aus Etappe 2 einzeln durch und erfasse gefundene Fehler mit Schritten zum Nachstellen.
  - **Warum:** Eine konkrete Fehlerbeschreibung macht eine Korrektur überprüfbar. Neue Wünsche müssen die erste Veröffentlichung nicht ständig verschieben.
  - **Erledigt, wenn:** Jede Pflichtfunktion nachweislich erfüllt ist und kein bekannter Absturz oder Datenverlust offen bleibt.

- [ ] **077 — Verbessere Fehler- und Hinweistexte.** Erkläre das Problem in Alltagssprache und zeige eine passende Aktion; bewahre Eingaben bei einem Speicherfehler auf.
  - **Warum:** Nutzer müssen verstehen, wie sie fortfahren können. Interne Fehlermeldungen allein helfen ihnen dabei selten.
  - **Erledigt, wenn:** Bekannte Fehlerfälle verständlich behandelt werden und fehlgeschlagenes Speichern kein falsches Erfolgssignal zeigt.

- [ ] **078 — Entferne Entwicklungshilfen aus der Nutzeroberfläche.** Prüfe Beispielzahlen, automatisch eingefügte Testdaten, Debug-Schaltflächen und Protokolle mit eingegebenen Vokabeln.
  - **Warum:** Die veröffentlichte App soll echte Daten zeigen und private Lerninhalte nicht unnötig protokollieren.
  - **Erledigt, wenn:** Eine frische Installation sauber startet und ausschließlich gewünschte Inhalte und Funktionen enthält.

- [ ] **079 — Schreibe die tatsächlichen Start- und Testanweisungen auf.** Ergänze in der README den Xcode-Projektpfad, benötigte Versionen, Start im Simulator, Start auf dem Gerät und Ausführung der Tests.
  - **Warum:** So kannst du das Projekt später selbst wieder öffnen und andere können es nachvollziehen. Dokumentiere getestete Schritte statt vermuteter Befehle.
  - **Erledigt, wenn:** Du anhand der Anleitung aus einem frischen Checkout bauen und testen kannst. Nutze den vorhandenen Checkout; zusätzliche Worktrees sind kein notwendiger Bestandteil.

- [ ] **080 — Sichere einen nachvollziehbaren Stand mit Git.** Prüfe den vollständigen Diff, committe zusammengehörige Änderungen und übertrage den Stand bewusst ins Repository.
  - **Warum:** Ein nachvollziehbarer Stand bildet die Grundlage für Fehlerkorrekturen und Veröffentlichung. Übertrage nur geprüfte Dateien und keine Geheimnisse.
  - **Erledigt, wenn:** Der getestete Stand auf GitHub vorhanden ist und die Tests auch mit diesem Stand funktionieren.

**Meilenstein:** Ab hier hast du eine auf deinem eigenen iPhone nutzbare erste Version. Die folgenden Schritte bereiten die Verteilung an andere Menschen und den App Store vor.

## Etappe 14 — Datenschutz und Veröffentlichung vorbereiten

- [ ] **081 — Erfasse die tatsächlich verarbeiteten Daten.** Notiere Vokabeln und Lernstände sowie mögliche Datenübertragungen durch zusätzliche Bibliotheken. Für den empfohlenen Start sind weder Konto noch Analyse-SDK nötig.
  - **Warum:** Für Datenschutzangaben zählt das echte Verhalten der App einschließlich eingebauter Dienste. Lokal gespeicherte Daten und an einen Server übermittelte Daten sind unterschiedlich zu beurteilen.
  - **Erledigt, wenn:** Daten, Speicherorte, Empfänger und Zwecke nachvollziehbar dokumentiert sind.

- [ ] **082 — Erstelle eine zur App passende Datenschutzerklärung und Hilfe.** Beschreibe lokale Speicherung, Löschung, mögliche Verluste beim Deinstallieren und eine Kontaktmöglichkeit. Stelle die für den Store benötigte Erklärung über eine öffentlich erreichbare URL bereit.
  - **Warum:** Nutzer sollen wissen, was mit ihren Daten geschieht. Apple verlangt für App-Store-Apps eine passende Datenschutzerklärung; pauschale Versprechen reichen nicht aus.
  - **Erledigt, wenn:** Erklärung und Hilfetexte das tatsächliche Verhalten beschreiben und aus der App erreichbar sind. Kläre erforderliche Anbieterangaben passend zu deinem Veröffentlichungsort.

- [ ] **083 — Prüfe verwendete Ressourcen und Bibliotheken.** Dokumentiere die Lizenzen von Symbolen, Bildern, Schriftarten, Code und Vokabelmaterial. Prüfe die aktuellen Apple-Vorgaben zu Privacy Manifests und erforderlichen API-Begründungen für die tatsächlich verwendeten APIs und SDKs.
  - **Warum:** Veröffentlichung setzt passende Nutzungsrechte voraus. Manche technische Datenschutzangaben betreffen auch eingebundene Komponenten.
  - **Erledigt, wenn:** Alle verwendeten Bestandteile erlaubt sind und notwendige Hinweise beziehungsweise Manifestangaben vorhanden sind.

- [ ] **084 — Prüfe den App-Namen und erstelle ein App-Icon.** Suche nach bereits verwendeten Namen und möglichen Markenproblemen; erstelle ein eigenes Icon und pflege es in Xcodes Asset-Katalog ein.
  - **Warum:** Name und Icon machen die App erkennbar. Das Icon benötigt die von den aktuellen Werkzeugen verlangten Varianten und Eigenschaften.
  - **Erledigt, wenn:** Ein passender Name feststeht und Xcode das Icon ohne entsprechende Validierungsfehler übernimmt.

- [ ] **085 — Registriere dich für die benötigte Verteilung.** Prüfe die aktuellen Kosten und Voraussetzungen des Apple Developer Program und entscheide, ob du als Einzelperson oder Organisation veröffentlichst.
  - **Warum:** Für TestFlight und öffentliche App-Store-Verteilung ist diese Mitgliedschaft erforderlich. Angaben wie der veröffentlichte Entwicklername hängen von der Registrierung ab.
  - **Erledigt, wenn:** Die Mitgliedschaft aktiv ist und du Zugang zu App Store Connect hast. Kontodaten werden ausschließlich bei Apple eingegeben.

- [ ] **086 — Lege den App-Eintrag in App Store Connect an.** Verwende dieselbe Bundle-ID wie im Projekt und trage App-Namen sowie die erforderlichen Konto- und Vertriebsangaben ein.
  - **Warum:** App Store Connect verwaltet hochgeladene Builds, Tests, Store-Texte und Veröffentlichung. Aktuelle regionale Anforderungen, etwa Händlerangaben für die EU, musst du für deine Situation prüfen.
  - **Erledigt, wenn:** Ein gültiger App-Eintrag mit der richtigen Kennung vorhanden ist und notwendige Vereinbarungen vollständig sind.

- [ ] **087 — Lege Version und Build-Nummer fest.** Starte beispielsweise mit Version `1.0` und einer passenden ersten Build-Nummer; erhöhe die Build-Nummer bei weiteren Uploads derselben Version.
  - **Warum:** Die Versionsnummer beschreibt die Ausgabe für Nutzer. Die Build-Nummer unterscheidet einzelne technische Stände dieser Ausgabe.
  - **Erledigt, wenn:** Beide Angaben korrekt in Xcode stehen und du den dazugehörigen Git-Stand kennst.

## Etappe 15 — TestFlight, App Store und Betrieb

- [ ] **088 — Erzeuge und validiere einen Veröffentlichungs-Build.** Wähle in Xcode ein geeignetes Geräte-Buildziel, erstelle ein Archive und prüfe es mit den vorgesehenen Apple-Werkzeugen.
  - **Warum:** Ein Archive ist das gebündelte App-Paket für die Verteilung. Ein erfolgreicher Simulator-Build ersetzt weder diesen Schritt noch passende Signierung.
  - **Erledigt, wenn:** Das Archiv ohne ungeklärte Validierungsfehler für den Upload vorbereitet ist.

- [ ] **089 — Lade den Build in App Store Connect hoch.** Nutze Xcodes Verteilungsablauf, warte auf die Verarbeitung und beantworte die geforderten Angaben entsprechend dem tatsächlichen App-Verhalten.
  - **Warum:** Erst ein verarbeiteter Upload kann für TestFlight oder einen Store-Antrag ausgewählt werden. Dazu können etwa Angaben zur Exportkonformität gehören.
  - **Erledigt, wenn:** Der richtige Build als verarbeitet sichtbar ist und keine erforderliche Angabe fehlt.

- [ ] **090 — Teste die Verteilung mit TestFlight.** Installiere den hochgeladenen Build zuerst selbst; lade anschließend wenige geeignete Tester ein. Beachte Apples unterschiedliche Voraussetzungen für interne und externe Tester.
  - **Warum:** TestFlight verteilt den tatsächlichen Beta-Build. Das ist ein anderer Weg als die direkte Installation aus Xcode; externe Tests können eine Beta-Prüfung erfordern.
  - **Erledigt, wenn:** Der Hauptablauf mit der über TestFlight installierten Version erfolgreich geprüft wurde.

- [ ] **091 — Sammle Rückmeldungen und behebe Pflichtfehler.** Erfasse Gerät, iOS-Version, Build-Nummer und Schritte zum Nachstellen; lade bei Änderungen einen neuen Build hoch und prüfe die betroffenen Abläufe erneut.
  - **Warum:** Eine Rückmeldung wie „Speichern klappt nicht“ braucht Kontext. Ein korrigierter Quellcode ist erst nach Prüfung des neuen Builds bestätigt.
  - **Erledigt, wenn:** Keine bekannten Fehler offen sind, die Kernfunktionen, Datenerhalt oder Benutzbarkeit verhindern.

- [ ] **092 — Erstelle echte Screenshots und Store-Texte.** Zeige den fertigen Ablauf ohne private Inhalte und beschreibe Funktionen sowie die Grenze der lokalen Speicherung verständlich.
  - **Warum:** Nutzer sollen vor dem Download erkennen können, was die App kann. Versprich keine Synchronisierung oder Funktionen, die noch nicht existieren.
  - **Erledigt, wenn:** Die aktuell geforderten Screenshot-Formate, Beschreibung, Kategorie, Support-URL und Datenschutz-URL vollständig sind.

- [ ] **093 — Fülle Altersfreigabe und Datenschutzangaben aus.** Beantworte die aktuellen Fragen anhand der App und aller eingebundenen Dienste; wähle Preis und verfügbare Regionen bewusst.
  - **Warum:** Diese Angaben beeinflussen, wie die App im Store erscheint. Offline-Betrieb allein ersetzt nicht die Prüfung jeder verwendeten Komponente.
  - **Erledigt, wenn:** Die Angaben vollständig sind und mit dem dokumentierten Verhalten übereinstimmen.

- [ ] **094 — Reiche den geprüften Build zur App-Prüfung ein.** Wähle den richtigen Build und beschreibe den Testablauf für Apples Prüfer; lege bei Bedarf nachvollziehbare Hinweise bei.
  - **Warum:** Die App-Store-Prüfung beurteilt unter anderem Funktion und Richtlinienkonformität. Eine Einreichung ist noch keine Zusage der Veröffentlichung.
  - **Erledigt, wenn:** Der Antrag eingereicht ist. Bearbeite etwaige Rückfragen konkret und prüfe Änderungen vor einer erneuten Einreichung.

- [ ] **095 — Veröffentliche bewusst nach der Freigabe.** Wähle für die erste Ausgabe beispielsweise eine manuelle Veröffentlichung, kontrolliere Store-Angaben und gib die freigegebene Version frei.
  - **Warum:** So behältst du Kontrolle über den Zeitpunkt. Die Anzeige im Store kann sich nach der Freigabe noch verzögern.
  - **Erledigt, wenn:** Die App tatsächlich im gewählten Store verfügbar ist, aus dem Store installiert wurde und der Hauptablauf erneut funktioniert.

- [ ] **096 — Dokumentiere die veröffentlichte Version.** Notiere Versionsnummer, Build-Nummer, Git-Stand, Datum und bekannte Einschränkungen; markiere den Quellstand etwa mit einem Git-Tag.
  - **Warum:** Ein Tag ist eine benannte Markierung für einen bestimmten Commit. Damit findest du später genau den Code einer veröffentlichten Version wieder.
  - **Erledigt, wenn:** Store-Version und Quellcode eindeutig zugeordnet werden können.

- [ ] **097 — Richte einen kleinen Wartungsablauf ein.** Prüfe Rückmeldungen und verfügbare Absturzberichte regelmäßig; priorisiere Datenverlust und Abstürze vor neuen Funktionen.
  - **Warum:** Eine veröffentlichte App muss auch bei neuen iOS-Versionen und unerwarteten Nutzungsfällen zuverlässig bleiben.
  - **Erledigt, wenn:** Es einen festen Prüfzeitpunkt, eine erreichbare Supportmöglichkeit und eine Liste offener Probleme gibt.

- [ ] **098 — Plane den ersten sicheren Update-Test.** Installiere eine neue Testversion über eine bereits mit Daten gefüllte ältere Version und prüfe Wörter, Listen und Lernstände.
  - **Warum:** Änderungen am Speichermodell können eine Datenmigration benötigen. Migration bedeutet, vorhandene Daten in eine neue Struktur zu überführen; einfaches Löschen des Speichers wäre keine nutzerfreundliche Lösung.
  - **Erledigt, wenn:** Vor jedem Update der Erhalt bestehender Daten nachgewiesen ist und erforderliche Migrationen getestet sind.

## Etappe 16 — Danach gezielt erweitern

- [ ] **099 — Wähle genau eine nächste Verbesserung anhand der Nutzung.** Beispiele: Rückwärts-Abfrage, Suchfunktion, Aussprache, Erinnerung oder Export. Beginne mit dem wichtigsten beobachteten Bedarf.
  - **Warum:** Eine einzelne Erweiterung lässt sich sauber planen, verstehen und testen. Rückwärts-Abfrage benötigt eigenen Fortschritt; Benachrichtigungen benötigen unter anderem eine passende Erlaubnis.
  - **Erledigt, wenn:** Nutzen, Umfang und Abnahmekriterien der nächsten Funktion dokumentiert sind.

- [ ] **100 — Plane neue Infrastruktur erst bei echtem Bedarf.** Für Synchronisierung, gemeinsame Listen oder KI prüfst du gesondert Server, Authentifizierung, Kosten, Datenschutz und sicheren Umgang mit Schlüsseln.
  - **Warum:** Ein Backend ist ein außerhalb der App laufender Dienst. Es bringt neue Anforderungen mit sich; geheime API-Schlüssel gehören weder ins Repository noch ungeschützt in eine ausgelieferte App.
  - **Erledigt, wenn:** Für die gewählte Erweiterung geklärt ist, ob externe Dienste erforderlich sind und wie sie sicher betrieben und getestet werden.

## Begriffe zum Nachschlagen

| Begriff | Einfache Erklärung |
| --- | --- |
| Native App | Eine App, die mit Werkzeugen und Schnittstellen der jeweiligen Plattform entwickelt wird; hier für iOS. |
| Swift | Apples Programmiersprache für die App-Logik und viele weitere Aufgaben. |
| SwiftUI | Apples Framework zum Beschreiben von Oberflächen und ihrer Zustände. |
| Framework | Vorgefertigte Bausteine und Regeln, auf die dein eigener Code aufbaut. |
| SwiftData | Apples Framework für die Verwaltung und Speicherung strukturierter Daten. |
| Xcode | Entwicklungsprogramm auf dem Mac zum Schreiben, Bauen, Testen und Verteilen der App. |
| Simulator | Software auf dem Mac, die viele Eigenschaften eines iPhones nachbildet; sie ersetzt nicht alle Tests auf echten Geräten. |
| Repository / Repo | Ablage für die Projektdateien und ihre durch Git verwaltete Änderungshistorie. |
| Commit | Ein lokal gespeicherter, benannter Änderungsstand in Git. |
| Push | Übertragung lokaler Git-Commits in ein entferntes Repository, etwa auf GitHub. |
| Build | Ergebnis des Übersetzens und Zusammenfügens von Code und Ressourcen zu einem Programm. |
| MVP | Die kleinste Version, die das wichtigste Nutzerproblem bereits sinnvoll löst. |
| Persistenz | Daten bleiben auch nach Beenden und erneutem Starten der App erhalten. |
| Unit-Test | Automatische Prüfung eines kleinen, möglichst isolierten Teils der Logik. |
| UI-Test | Automatische Prüfung eines Bedienablaufs über die Benutzeroberfläche. |
| Regression | Ein neuer Fehler in einem Ablauf, der vorher funktioniert hat. |
| Bundle-ID | Eindeutige technische Kennung einer App im Apple-System. |
| Code Signing | Digitale Signierung, die App und berechtigte Entwickleridentität verbindet. |
| TestFlight | Apples Dienst zum Verteilen und Testen von Beta-Versionen. |
| Backend | Ein externer Dienst, der zum Beispiel Konten, Synchronisierung oder gemeinsame Inhalte verwaltet. |

## Offizielle Anlaufstellen

Diese Quellen helfen dir beim jeweiligen Schritt. Prüfe dort insbesondere aktuelle Systemvoraussetzungen, Kosten und Veröffentlichungsvorgaben; diese können sich ändern.

- [Swift-Tour](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/guidedtour/) — Einstieg in die Sprache für Etappe 6.
- [Develop in Swift](https://developer.apple.com/tutorials/develop-in-swift) — Apples Lernmaterial für den App-Einstieg.
- [Xcode](https://developer.apple.com/xcode/) und [Xcode-Systemvoraussetzungen](https://developer.apple.com/support/xcode/) — Werkzeuge und kompatible Versionen.
- [SwiftUI](https://developer.apple.com/documentation/swiftui) — Dokumentation für die Oberfläche.
- [SwiftData](https://developer.apple.com/documentation/swiftdata) — Dokumentation für lokale Datenmodelle und Speicherung.
- [Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/) — Apples Hinweise zu verständlicher Bedienung und Barrierefreiheit.
- [Apple Developer Program](https://developer.apple.com/programs/) — Mitgliedschaft und Verteilungsmöglichkeiten.
- [App Store Connect Hilfe](https://developer.apple.com/help/app-store-connect/) — Upload, TestFlight, Store-Angaben und Veröffentlichung.
- [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/) — Aktuelle Vorgaben für die App-Prüfung.

## Dein nächster konkreter Schritt

Beginne mit **001**: Lege `docs/APP-PLAN.md` an und schreibe den einen Satz auf, der den Nutzen deiner App beschreibt. Ergänze anschließend die Entscheidungen aus den nächsten Punkten. Diese Checkliste ist eine Arbeitsvorlage: Du darfst Details bewusst anpassen, solltest die Entscheidung und ihren Grund aber festhalten.
