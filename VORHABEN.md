# Vorhaben — Baby-Orakel

Lebende Arbeitsliste: alle aktuellen und abgeschlossenen Vorhaben dieses Projekts
mit ihrem Status. Anders als PROJEKTGEDAECHTNIS.md (Geschichtsbuch, wird nur
angehaengt) wird diese Tabelle laufend AKTUALISIERT — der Status einer Zeile wird
ueberschrieben, sobald sich der Stand aendert.

Status-Stufen: Idee -> Spezifiziert -> In Arbeit -> Verifiziert -> Erledigt
("Verifiziert" heisst hier: am echten Artefakt geprueft — nicht nur "fertig gebaut",
siehe Lessons Learned Kap. 3, Verifikations-Werkzeugkasten.)

| Nr. | Vorhaben | Status | Spezifikation |
|-----|----------|--------|----------------|
| 001 | Projekt anlegen, Seite als `index.html` uebernehmen | Verifiziert (md5-Vergleich gegen Original) | - |
| 002 | Seite oeffentlich erreichbar machen (GitHub Pages) | In Arbeit | - |
| 003 | Karte-speichern und Text-kopieren auf einem echten Handy testen (iPhone UND Android) | Idee | - |
| 004 | Antworten zentral sammeln statt nur pro Geraet (Auswertung nach der Geburt) | Idee — bewusst NICHT Teil der ersten Fassung, siehe README | - |

## Regeln
- Nur Vorhaben, die Code oder Datenverhalten aendern, brauchen eine Spezifikation
  (Vorlage: templates/SPEZIFIKATION.md). Tippfehler, Doku, Kleinkram: direkt hier
  eintragen, Status kann dabei auch sofort "Erledigt" sein.
- Spezifikationen liegen unter spezifikationen/<Nr.>-<kurztitel>.md, verlinkt in
  der letzten Spalte dieser Tabelle.
- Diese Datei ersetzt NICHT das Projektgedaechtnis. Der Abschnitt "Offene Punkte"
  im Projektgedaechtnis sollte auf diese Tabelle verweisen statt sie zu duplizieren
  — sonst gibt es zwei Quellen fuer denselben Stand.
- Nach jeder Aktualisierung dieser Datei: erneut lesen und die geaenderte Zeile
  zeigen, bevor der Stand als gespeichert gilt (siehe ~/.claude/CLAUDE.md,
  Abschnitt "Arbeitsweise mit Nils" — Schreiben-dann-nachlesen).
