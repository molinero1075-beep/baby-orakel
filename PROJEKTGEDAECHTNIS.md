# Projektgedaechtnis — Baby-Orakel

## AKTUELLER STAND
*(wird bei jedem Export KOMPLETT NEU geschrieben, nicht ergaenzt)*

**Stand 11.09.2026.** Das Projekt ist frisch angelegt. Es enthaelt die von Nils'
Freundin gelieferte Babyparty-Seite als `index.html` (bit-genau identisch zum
Original, md5 `fcccdc5edf2bae4d836c66a105a898e2`) sowie die Pflichtdateien nach
Projekt-Standard. Naechster Schritt ist die Veroeffentlichung ueber GitHub Pages,
damit Gaeste die Seite ueber einen Link aufrufen koennen.

Offene Punkte: siehe VORHABEN.md (dort ist der verbindliche Stand). Kurz:
- 002 Veroeffentlichung ueber GitHub Pages — in Arbeit
- 003 Test auf einem echten iPhone und einem echten Android-Geraet — offen
- 004 zentrale Sammlung der Antworten — bewusst nicht Teil dieser Fassung

---

## Protokoll 11.09.2026 — Projektstart und Uebernahme der Seite

### 1. Ausgangslage
Nils' Freundin hat eine fertige HTML-Datei "Baby-Orakel_Webversion_v2-7.html"
(13.562 Bytes) geliefert: ein Babyparty-Formular, das aus den Eingaben eine Karte
als PNG-Bild erzeugt. Die Datei lag zweifach im Windows-Downloads-Ordner
(einmal mit dem Zusatz "(1)"), beide Fassungen sind bit-genau identisch
(md5 `fcccdc5edf2bae4d836c66a105a898e2`). Ziel laut Briefing: die Seite soll im Netz
liegen, damit Gaeste auf der Babyparty per Link darauf zugreifen, das Formular
ausfuellen, die fertige Karte herunterladen und in einer WhatsApp-Gruppe teilen
koennen. Ausdruecklicher Wunsch: "schnell, einfach, unkompliziert".

### 2. Entscheidungen
a) Hosting ueber GitHub Pages statt Drag-and-drop-Diensten (Netlify Drop,
   tiiny.host): Nils' GitHub-Zugang ist auf diesem Rechner bereits eingerichtet und
   angemeldet (gh 2.98.0, Konto molinero1075-beep, Token-Rechte `repo`), die Seite
   bleibt dauerhaft und kostenlos erreichbar und laeuft nicht nach Tagen ab.
b) Kein Login fuer Gaeste. Im Briefing war von "einloggen" die Rede; das ist bewusst
   nicht umgesetzt, weil die Seite keine Benutzerverwaltung hat und ein Login auf
   einer Party nur eine Huerde waere. Gaeste oeffnen den Link und legen los.
c) Keine zentrale Sammlung der Antworten in dieser Fassung. Die Seite arbeitet rein
   oertlich im Browser; jeder Gast behaelt seine eigene Karte. Begruendung:
   "schnell und unkompliziert" war die Vorgabe, und eine Sammelstelle wuerde
   personenbezogene Daten Dritter auf einem Server speichern (DSGVO-Dimension).
   Als Vorhaben 004 vermerkt, nicht gebaut.
d) `index.html` liegt im Wurzelverzeichnis, obwohl PROJEKT_STANDARD.md "kein Code im
   Wurzelverzeichnis" verlangt — GitHub Pages erwartet die Startseite genau dort.
   Begruendete Abweichung, in CLAUDE.md vermerkt.
e) Python-Teile des Projekt-Standards entfallen (src/, tests/, requirements.txt,
   pytest.ini, .env.example): Es gibt keinen Programmcode ausserhalb der Seite,
   keine Abhaengigkeiten und keine Zugangsdaten.
f) Die gelieferte Datei wird inhaltlich NICHT veraendert, nur umbenannt. Damit bleibt
   sie mit dem Original vergleichbar; die Freundin kann jederzeit eine neue Fassung
   liefern.

### 3. Ergebnisse / Artefakte
Neues Projekt `~/baby-orakel` mit:
- `index.html` — die Seite, md5 gegen das Original verifiziert
- `README.md` — Briefing, Nicht-Ziele, Aufbau, Veroeffentlichungsweg
- `CLAUDE.md` — Projektregeln, Leseregel fuers Gedaechtnis, Do-NOT-Liste
- `VORHABEN.md` — Vorhaben 001 bis 004 mit Status
- `PROJEKTGEDAECHTNIS.md` — diese Datei
- `.gitignore` — aus der zentralen Vorlage, projektspezifisch ergaenzt
- `diagnose.conf` — nur `TOOLS=git`, da kein Datenprojekt
- `archive/` mit `.gitkeep`

### 4. Erkenntnisse / Fakten
- Die Seite ist vollstaendig eigenstaendig: HTML, CSS und Javascript stecken in einer
  einzigen Datei, es werden keine fremden Bibliotheken nachgeladen. Deshalb genuegt
  jeder statische Webspeicher, und die Seite funktioniert auch ohne Netz, wenn sie
  einmal geladen ist.
- Die Karte entsteht im Browser: Das Javascript baut ein SVG-Bild (1080x1600) und
  zeichnet es auf eine Canvas-Flaeche, daraus wird ein PNG. Es wird nichts an einen
  Server geschickt.
- Die Seite zeigt die fertige Karte zusaetzlich als Vorschaubild an. Das ist wichtig
  fuer iPhones: Der normale Download-Knopf funktioniert in Safari nicht zuverlaessig,
  ueber "langes Tippen aufs Bild -> Sichern" geht es dagegen immer.
- `gh auth status` meldet fehlende Token-Rechte `read:org`. Fuer eigene Repos und
  GitHub Pages ist das ohne Belang; nur Organisations-Abfragen sind eingeschraenkt.

### 5. Verworfen / Sackgassen
- Netlify Drop und tiiny.host: schneller im ersten Moment, aber die kostenlosen
  Links laufen ab bzw. haengen an keinem dauerhaften Konto. Fuer eine Adresse, die
  auf einer Party herumgereicht wird, zu unsicher.
- Ein privates Repo (Standardfall laut PROJEKT_START.md Punkt 1): mit einem
  kostenlosen GitHub-Konto laesst sich GitHub Pages nur aus einem oeffentlichen Repo
  betreiben. Bewusste Abweichung; die Datei enthaelt keine persoenlichen Daten.

### 6. Offene Punkte
Verbindlich in VORHABEN.md. Zusaetzlich zu klaeren, sobald die Seite steht:
- Funktioniert "Baby-Orakel als Bild speichern" auf dem Handy der Freundin?
- Soll die Adresse kuerzer/huebscher sein (eigene Domain), oder reicht die
  github.io-Adresse?

### 7. Kontextwissen
- Nils ist kein Entwickler und liest die Antworten selbst. Erklaerungen in normalem
  Deutsch, ein Schritt pro Antwort.
- Commit und Push macht Nils selbst im rohen Terminal (Regel aus PROJEKT_START.md).
- Die Datei stammt von Nils' Freundin; inhaltliche Aenderungswuensche kommen ueber
  ihn. Neue Fassungen von ihr ersetzen `index.html`, die alte Fassung wandert
  vorher nach `archive/`.
