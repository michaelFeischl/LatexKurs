# Tabellen, Abbildungen und Floats

## Tabellen mit `booktabs`

```latex
\begin{table}[htbp]
  \centering
  \caption{Messwerte}
  \label{tab:messwerte}
  \begin{tabular}{lrr}
    \toprule
    Probe & Wert 1 & Wert 2 \\
    \midrule
    A     & 12.3   & 45.6   \\
    B     & 11.9   & 47.1   \\
    \bottomrule
  \end{tabular}
\end{table}
```

## Abbildungen einbinden

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.7\textwidth]{bilder/plot.pdf}
  \caption{Beispielplot}
  \label{fig:plot}
\end{figure}
```

## Float-Verhalten verstehen

`table` und `figure` sind Gleitobjekte. Positionen wie `[h]`, `[t]`, `[b]`, `[p]` sind Wünsche, keine absoluten Befehle.

## Verzeichnisse

```latex
\listoffigures
\listoftables
```

## Gute Praxis

- Für Diagramme bevorzugt PDF (vektorbasiert).
- Sinnvolle Dateinamen verwenden (`experiment_2026_01.pdf` statt `bild1.pdf`).
- Jede Tabelle/Abbildung bekommt `\caption` und `\label`.
