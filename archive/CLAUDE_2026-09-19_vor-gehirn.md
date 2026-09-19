# Baby-Orakel

Projektregeln fuer diesen Ordner. Ergaenzend gelten die globalen Regeln in ~/.claude/CLAUDE.md.

## Zweck
Eine einzelne statische Webseite (`index.html`) fuer eine Babyparty: Gaeste tippen
Geburtstermin, Gewicht, Name usw., bekommen daraus eine fertige Karte als Bild und
teilen sie selbst in einer WhatsApp-Gruppe. Veroeffentlicht ueber GitHub Pages.

## Projektgedaechtnis lesen (Token sparen)
Bei neuem Chat: NUR den Abschnitt "AKTUELLER STAND" oben in PROJEKTGEDAECHTNIS.md
UND den juengsten (untersten) Protokollblock vollstaendig lesen. Aeltere Bloecke
NICHT laden, sondern nur bei konkretem Bedarf gezielt per grep/Read durchsuchen.

## Befehle (woertlich zum Kopieren)

```bash
# Seite oertlich im Windows-Browser ansehen (kein Server noetig):
explorer.exe "$(wslpath -w ~/baby-orakel/index.html)"

# Veroeffentlichen (macht Nils selbst im rohen Terminal):
cd ~/baby-orakel && git add -A && git commit -m "..." && git push

# Zustandsuebersicht:
bash ~/admin-tools/diagnose.sh ~/baby-orakel
```

Es gibt keine Tests und keine Abhaengigkeiten: Die Seite braucht weder Python noch
einen Server, sondern laeuft vollstaendig im Browser des Gastes.

## Ordnerkarte
- `index.html` — die komplette Seite (HTML, CSS, Javascript in einer Datei)
- `archive/` — abgeloeste Fassungen der Seite
- `README.md` — Anforderungen (Briefing) und Aufbau fuer Menschen
- `VORHABEN.md` — lebende Vorhabenliste mit Status
- `PROJEKTGEDAECHTNIS.md` — AKTUELLER STAND + chronologisches Archiv

## Konventionen
- `index.html` liegt bewusst im Wurzelverzeichnis, obwohl PROJEKT_STANDARD.md "kein
  Code im Wurzelverzeichnis" verlangt: GitHub Pages erwartet die Startseite genau
  dort. Begruendete Abweichung, kein Versehen.
- Der Projekt-Standard ist fuer Python geschrieben; `src/`, `tests/`,
  `requirements.txt`, `pytest.ini` und `.env.example` entfallen hier mangels
  Programmcode, Abhaengigkeiten und Zugangsdaten.
- Aenderungen an `index.html`: die bisherige Fassung vorher nach `archive/` mit
  Datum im Namen kopieren (die Datei ist ein geliefertes Dokument, nicht unser
  eigener Code — deshalb gilt hier "Archivieren statt Loeschen").
- Nach jeder Aenderung im Browser nachsehen, BEVOR etwas als fertig gilt: einmal
  ausfuellen, Karte erzeugen, Bild pruefen.

## Do NOT
- Keine Analyse-Werkzeuge, keine Frameworks, kein Build-Schritt einbauen. Die Staerke
  dieser Seite ist, dass sie eine einzige Datei ohne Serverbedarf ist.
- Keine Eingaben der Gaeste an einen Server senden, solange Nils das nicht
  ausdruecklich beauftragt (Datenschutz: Daten Dritter, siehe README, Vorhaben 004).
- Nicht committen oder pushen: Commit und Push macht Nils selbst im rohen Terminal.
- Keine Aenderungen an zentralen Admin-Werkzeugen (~/admin-tools, ~/lessons-learned)
  aus diesem Projekt heraus — stattdessen ein Briefing fuer den Admin-Chat liefern.
