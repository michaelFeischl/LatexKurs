# Abbildungen und Float-Verhalten

## 1. Grafikpaket

```latex
\usepackage{graphicx}
```
`graphicx` stellt `\includegraphics` und optionale Skalierung bereit; ohne dieses Paket können externe Bilder nicht eingebunden werden.

## 2. Grundmuster für Abbildungen

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=.75\textwidth]{bilder/ergebnisplot.pdf}
  \caption{Ergebnisplot der Simulation}
  \label{fig:ergebnisplot}
\end{figure}
```
`width=.75\textwidth` skaliert das Bild auf 75 % der Textbreite. `\caption` erzeugt die Nummer/Beschriftung, und `\label` macht die Abbildung referenzierbar.

## 3. Wahl des Dateiformats

- Diagramme/Grafiken: PDF (vektorbasiert)
- Fotos: PNG/JPG (auflösungsabhängig)

## 4. `.eps` und `pdflatex`

`pdflatex` kann `.eps`-Dateien nicht direkt einbinden. Für einen `pdflatex`-Workflow sind deshalb zwei Wege üblich:

1. `.eps` vorab nach `.pdf` konvertieren (empfohlen), dann die PDF-Datei mit `\includegraphics` einbinden.
2. mit `epstopdf` arbeiten, damit beim Build automatisch eine PDF-Version erzeugt wird.

Beispiel:

```latex
\usepackage{graphicx}
\usepackage{epstopdf}
```

Wenn ein Projekt zwingend bei `.eps` bleiben muss, kann alternativ die klassische Kette `latex -> dvips -> ps2pdf` verwendet werden statt `pdflatex`.

## 5. Floatoptionen verstehen

- `h`: hier (Wunsch)
- `t`: Seitenanfang
- `b`: Seitenende
- `p`: Float-Seite

Wichtig: LaTeX entscheidet final nach Umbruchregeln.

## 6. Abbildungs- und Tabellenverzeichnis

```latex
\listoffigures
\listoftables
```
Diese Befehle erzeugen automatisch Verzeichnisse aus vorhandenen `figure`- und `table`-Beschriftungen.

## 7. Häufige Fehler

- Bilddatei nicht gefunden (Pfad/Name prüfen)
- zu große Bilder ohne Skalierung
- fehlende `\caption`/`\label`
- Verweis im Text fehlt

## 8. Gute wissenschaftliche Praxis

- jede Abbildung hat eine Aussage,
- Beschriftung erklärt Inhalt, nicht nur "Plot 1",
- Achsen, Legenden und Einheiten klar darstellen.
