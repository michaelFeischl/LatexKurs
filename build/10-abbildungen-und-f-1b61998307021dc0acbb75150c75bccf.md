# Abbildungen und Float-Verhalten

## 1. Grafikpaket

```latex
\usepackage{graphicx}
```

## 2. Grundmuster für Abbildungen

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=.75\textwidth]{bilder/ergebnisplot.pdf}
  \caption{Ergebnisplot der Simulation}
  \label{fig:ergebnisplot}
\end{figure}
```

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

## 6. Häufige Fehler

- Bilddatei nicht gefunden (Pfad/Name prüfen)
- zu große Bilder ohne Skalierung
- fehlende `\caption`/`\label`
- Verweis im Text fehlt

## 7. Gute wissenschaftliche Praxis

- jede Abbildung hat eine Aussage,
- Beschriftung erklärt Inhalt, nicht nur "Plot 1",
- Achsen, Legenden und Einheiten klar darstellen.
