# Tabellen und Layout-Bausteine

## 1. Tabellen mit `tabular`

```latex
\begin{tabular}{lcr}
Name & Wert & Einheit \\
A    & 1.23 & m \\
B    & 4.56 & m
\end{tabular}
```

Spaltentypen:

- `l` links,
- `c` zentriert,
- `r` rechts,
- `p{Breite}` Absatzspalte.

## 2. Professionelle Linien mit `booktabs`

```latex
\begin{tabular}{lrr}
  \toprule
  Probe & Messung 1 & Messung 2 \\
  \midrule
  A & 12.3 & 45.6 \\
  B & 11.9 & 47.1 \\
  \bottomrule
\end{tabular}
```

## 3. Tabellen als Float

```latex
\begin{table}[htbp]
  \centering
  \caption{Messwerte}
  \label{tab:messwerte}
  ...
\end{table}
```

## 4. Mehrspaltige Zellen

```latex
\multicolumn{2}{c}{Kopf}
```

## 5. Minipage für nebeneinanderliegende Inhalte

```latex
\begin{minipage}[t]{.48\textwidth}
Linker Inhalt
\end{minipage}
\hfill
\begin{minipage}[t]{.48\textwidth}
Rechter Inhalt
\end{minipage}
```

## 6. Wann `tabbing` sinnvoll ist

`tabbing` kann für schnell gesetzte, tabulatorartige Strukturen nützlich sein,
ist aber für echte Datentabellen meist weniger robust als `tabular`.

## 7. Tabellenqualität

- Einheiten in Kopfzeilen,
- Dezimalstellen konsistent,
- Tabellen nicht überladen,
- jede Tabelle mit Aussage im Fließtext einführen.
