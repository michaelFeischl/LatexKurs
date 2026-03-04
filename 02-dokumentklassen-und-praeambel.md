# Dokumentklassen, Präambel und Pakete

## 1. Dokumentklasse wählen

Die Klasse bestimmt Grundstruktur und das Layout.

```latex
\documentclass[a4paper,11pt]{article}
```
`\documentclass` legt die Basis des Dokuments fest. Optionen in `[...]` konfigurieren das Layout, die Klasse in `{...}` bestimmt den Dokumenttyp.

Häufig:

- `article`: kurze wissenschaftliche Texte, Übungsblätter, Berichte
- `report`: längere Arbeiten mit Kapiteln
- `book`: Bücher mit Frontmatter/Backmatter
- `beamer`: Präsentationen

## 2. Sinnvolle Optionen

Typische Optionen in Textdokumenten:

- `a4paper`
- `10pt`, `11pt` oder `12pt`
- `oneside` (meist für PDFs)
- `twoside` (für echten Buchdruck, rückt den Seiteninhalt weg von der Buchfalz)

## 3. Moderne Präambel (Basis)

```latex
\documentclass[a4paper,11pt]{article}

\usepackage[T1]{fontenc}
\usepackage[ngerman]{babel}
\usepackage{microtype}
\usepackage{csquotes}
\usepackage{amsmath,amssymb,amsthm}
\usepackage{graphicx}
\usepackage{booktabs}
\usepackage[hidelinks]{hyperref}
```
Jede `\usepackage{...}`-Zeile lädt ein Paket mit Zusatzfunktionen. Optionen wie `[ngerman]` oder `[hidelinks]` wirken nur auf das direkt folgende Paket.

Erklärung der verwendeten Pakete:

- `fontenc` mit Option `T1`: verbessert die Zeichenkodierung der Schrift im PDF (wichtig für Umlaute, Trennung und Copy/Paste).
- `babel` mit Option `ngerman`: stellt Sprache, Silbentrennung und automatische Bezeichnungen (z. B. "Inhalt", "Abbildung") auf Deutsch.
- `microtype`: verbessert den Grauwert des Textsatzes durch feine typografische Korrekturen (z. B. Randausgleich, Zeichenprotrusion).
- `csquotes`: bietet saubere, sprachabhängige Anführungszeichen und Zitatbefehle.
- `amsmath`: erweitert den Mathematiksatz um viele Umgebungen und Ausrichtungsoptionen.
- `amssymb`: ergänzt zusätzliche mathematische Symbole.
- `amsthm`: stellt Werkzeuge für Theorem-ähnliche Umgebungen (Theorem, Lemma, Beweis) bereit.
- `graphicx`: ermöglicht das Einbinden und Skalieren von Grafiken.
- `booktabs`: liefert hochwertige Tabellenlinien (`\toprule`, `\midrule`, `\bottomrule`) für professionellere Tabellen.
- `hyperref` mit Option `hidelinks`: erzeugt klickbare Querverweise und Links im PDF; `hidelinks` unterdrückt farbige Rahmen um Links.

## 4. Reihenfolge und Verantwortung von Paketen

- Sprach- und Schriftpakete früh laden.
- Fachpakete (Mathe, Grafik, Tabellen) danach.
- `hyperref` weit hinten laden, um Konflikte zu minimieren.

## 5. LaTeX und UTF-8

- UTF-8 ist in aktuellen LaTeX-Distributionen Standard.
- Viele frühere Workarounds sind nicht mehr nötig.
- Schlanke Präambeln sind wartbarer als "Paket-Sammlungen auf Vorrat".

## 6. Präambel modularisieren

Bei größeren Projekten:

```latex
% main.tex
\input{preamble/packages}
\input{preamble/macros}
```
`\input{...}` kopiert den Inhalt der angegebenen Datei an genau diese Stelle ein. So bleibt `main.tex` schlank und die Konfiguration wartbar.

Vorteile:

- bessere Übersicht,
- wiederverwendbare Konfiguration,
- schnellere Fehlersuche.

## 7. Minimalbeispiel mit sauberem Rahmen

```latex
\documentclass[a4paper,11pt]{article}
\usepackage[T1]{fontenc}
\usepackage[ngerman]{babel}
\usepackage[hidelinks]{hyperref}

\title{Kurzbericht}
\author{Max Mustermann}
\date{\today}

\begin{document}
\maketitle
\tableofcontents

\section{Einleitung}
Beispieltext.

\end{document}
```
Die Präambel endet vor `\begin{document}`; ab dort steht der eigentliche Inhalt. Befehle wie `\maketitle` und `\tableofcontents` erzeugen Titel und Inhaltsverzeichnis automatisch.
