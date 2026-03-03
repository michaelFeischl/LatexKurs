# Dokumentklassen, Präambel und Pakete

## 1. Dokumentklasse wählen

Die Klasse bestimmt Grundstruktur und Standardlayout.

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
- `twoside` (für echten Buchdruck)

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

## 4. Reihenfolge und Verantwortung von Paketen

- Sprach- und Schriftpakete früh laden.
- Fachpakete (Mathe, Grafik, Tabellen) danach.
- `hyperref` weit hinten laden, um Konflikte zu minimieren.

## 5. Was aus älteren Kursen heute anders ist

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
