# Baby-Orakel

Eine einzelne, in sich geschlossene Webseite fuer eine Babyparty: Gaeste tippen auf
einem Handy oder Rechner, wann das Baby kommt, wie schwer es wird, wie es heissen
koennte usw. Am Ende erzeugt die Seite eine fertige Karte als Bild, die man
speichern und in einer WhatsApp-Gruppe teilen kann.

## Anforderungen (Briefing von Nils, 11.09.2026)

- Die Seite liegt oeffentlich im Netz; die Gastgeberin teilt auf der Babyparty
  einen Link.
- Gaeste brauchen KEIN Konto und KEIN Passwort. Link antippen, ausfuellen, fertig.
  (Im urspruenglichen Briefing war von "einloggen" die Rede - das ist bewusst
  nicht umgesetzt, weil es nur eine Huerde waere und die Seite gar keine
  Benutzerverwaltung hat.)
- Nach dem Ausfuellen entsteht eine fertige Karte als Bild zum Herunterladen.
- Das Bild wird anschliessend von den Gaesten selbst in die WhatsApp-Gruppe
  geteilt.
- Umsetzung ausdruecklich "schnell und unkompliziert".

## Was die Seite NICHT tut (bewusst)

- Sie sammelt keine Antworten zentral. Jede Eingabe bleibt auf dem Geraet des
  Gastes; es geht nichts an einen Server. Wer spaeter auswerten will, wer am
  naechsten dran lag, muss die Karten aus der WhatsApp-Gruppe zusammentragen.
  Eine zentrale Sammelstelle waere technisch moeglich, aber deutlich aufwendiger
  und datenschutzrechtlich heikler (personenbezogene Daten Dritter) -> als
  Vorhaben 002 in VORHABEN.md vermerkt, nicht Teil dieser Fassung.
- Sie hat keine Anmeldung, keine Datenbank, kein Backend.

## Aufbau

| Datei / Ordner          | Inhalt                                                      |
|-------------------------|-------------------------------------------------------------|
| `index.html`            | die komplette Seite (HTML, CSS und Javascript in EINER Datei) |
| `archive/`              | abgeloeste Fassungen der Seite (Archivieren statt Loeschen)   |
| `PROJEKTGEDAECHTNIS.md` | Verlauf des Projekts, beginnt mit "AKTUELLER STAND"           |
| `VORHABEN.md`           | lebende Liste der Vorhaben mit Status                         |

## Oertlich ansehen

```bash
# Datei einfach im Browser oeffnen - es wird kein Server gebraucht:
explorer.exe "$(wslpath -w ~/baby-orakel/index.html)"
```

## Veroeffentlichen

Die Seite wird ueber GitHub Pages ausgeliefert (kostenloser Webspeicher von
GitHub). Der Stand des Branches `main` ist das, was im Netz steht: nach einem
`git push` ist die Aenderung nach etwa einer Minute oeffentlich sichtbar.

Oeffentliche Adresse: siehe PROJEKTGEDAECHTNIS.md, Abschnitt "AKTUELLER STAND".

## Herkunft

`index.html` ist unveraendert die von Nils' Freundin gelieferte Fassung
"Baby-Orakel_Webversion_v2-7.html" (Pruefsumme md5
`fcccdc5edf2bae4d836c66a105a898e2`), nur umbenannt - GitHub Pages erwartet als
Startseite eine Datei namens `index.html`.
