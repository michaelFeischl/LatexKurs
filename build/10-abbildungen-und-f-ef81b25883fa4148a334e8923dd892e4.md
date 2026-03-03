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

## 4. Floatoptionen verstehen

- `h`: hier (Wunsch)
- `t`: Seitenanfang
- `b`: Seitenende
- `p`: Float-Seite

Wichtig: LaTeX entscheidet final nach Umbruchregeln.

## 5. Abbildungs- und Tabellenverzeichnis

```latex
\listoffigures
\listoftables
```
Diese Befehle erzeugen automatisch Verzeichnisse aus vorhandenen `figure`- und `table`-Beschriftungen.

## 6. Häufige Fehler

- Bilddatei nicht gefunden (Pfad/Name prüfen)
- zu große Bilder ohne Skalierung
- fehlende `\caption`/`\label`
- Verweis im Text fehlt

## 7. Gute wissenschaftliche Praxis

- jede Abbildung hat eine Aussage,
- Beschriftung erklärt Inhalt, nicht nur "Plot 1",
- Achsen, Legenden und Einheiten klar darstellen.
