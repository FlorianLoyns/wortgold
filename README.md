# Wortgold

**Englisch-Vokabeltrainer mit Karteibox und Leitner-System, CEFR-Niveau A1 bis C1.**

[![Lizenz: CC BY-NC-SA 4.0](https://img.shields.io/badge/Lizenz-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.de)
![Keine Abhängigkeiten](https://img.shields.io/badge/Abh%C3%A4ngigkeiten-keine-brightgreen)
![PWA](https://img.shields.io/badge/PWA-offline--f%C3%A4hig-goldenrod)

Ein mobiler Vokabeltrainer für die häufigsten englischen Wörter im Alltagsgebrauch, nach CEFR-Niveau strukturiert. Eine HTML-Datei, kein Build-System, offline-fähig, ohne Tracker.

## Lernprinzip

Eine Karte zeigt vorne ein englisches Wort (mit Wortart und CEFR-Niveau), hinten die deutsche Übersetzung. Tippen flippt die Karte um. Selbstbewertung über drei Knöpfe: **Wusste nicht** (zurück in Fach 1), **Unsicher** (Fach bleibt), **Wusste ich** (Fach +1, +1 XP). Karten wandern durch fünf Fächer mit Wartezeiten 1/2/4/8/16 Tage.

## Was die App kann

- **CEFR-Niveau-Filter** — wähle in den Einstellungen, welche Stufen (A1, A2, B1, B2, C1) trainiert werden. Default: A1.
- **Wortart-Badge** — auf jeder Karte siehst du, ob es ein `n.`, `v.`, `adj.` ist (zum Disambiguieren bei Wörtern wie *close* oder *back*).
- **Aussprache per Tap** — Lautsprecher-Symbol auf der Karte, nutzt die System-Sprachausgabe (en-US).
- **Combo-Counter** — ab 3 in Folge fliegt die Pille von oben rein.
- **Tagesziel-Ring** — Daily-Goal als Goldverlauf-Ring.
- **Streak-Heatmap** — letzte 30 Tage auf einen Blick.
- **XP- und Level-System** — vom *Lehrling* zum *Großmeister*.
- **Sounds und Haptik** — abschaltbar.
- **Hell- und Dunkelmodus** — System / Hell / Dunkel.
- **Offline-fähig** — PWA, einmal geladen, funktioniert ohne Netz.
- **DSGVO-freundlich** — keine Tracker, keine Konten, alles bleibt im Browser.

## Vokabeln pflegen

Die Wortschatz-Decks liegen unter **`decks/cefr-{a1,a2,b1,b2,c1}.csv`** — eine Datei pro CEFR-Niveau. Jede Datei lässt sich in Excel, Numbers, Google Sheets oder einem Text-Editor öffnen.

Format:

```
wort;übersetzung;wortart;niveau;thema
abandon;aufgeben;v.;C1;
abdomen;Bauch / Unterleib;n.;B2;
ability;Fähigkeit;n.;A2;
…
```

Spalten:

- **wort** — englisches Wort (Vorderseite der Karte)
- **übersetzung** — deutsche Übersetzung (Rückseite)
- **wortart** — n. / v. / adj. / adv. / prep. / conj. / pron. / det. / exclam. / number etc.
- **niveau** — A1 / A2 / B1 / B2 / C1
- **thema** — optional, für späteres Filtern (z. B. „Familie", „Reisen")

Trennzeichen ist Semikolon (`;`); Komma und Tab gehen auch — der Parser erkennt es automatisch. Zeilen mit `#` am Anfang sind Kommentare. Die Header-Zeile wird automatisch übersprungen. Beim Speichern unbedingt **UTF-8** wählen.

Updates werden beim nächsten Start sofort geladen (Service Worker ist auf Network-First für die CSVs).

## Technisches

Eine einzige HTML-Datei plus 5 CSVs, kein Build-System, keine Frameworks, keine externen Abhängigkeiten zur Laufzeit. Service Worker für Offline-Cache, `localStorage` für Fortschritt — keine Daten verlassen das Gerät.

## Impressum

Verantwortlich: Florian Loyns. Pflichtangaben nach § 5 DDG und Kontakt: [Impressum](https://florianloyns.github.io/Impressum/)

## Lizenz

[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.de) — Code und deutsche Übersetzungen unter Namensnennung, nicht-kommerziell, unter gleichen Bedingungen.
