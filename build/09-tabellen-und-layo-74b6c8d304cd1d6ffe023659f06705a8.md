# Tabellen und Layout-Bausteine

## 1. Tabellen mit `tabular`

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{tabular}{lcr}<br>Name & Wert & Einheit \\\\<br>A    & 1.23 & m \\\\<br>B    & 4.56 & m<br>\end{tabular}</code></pre> | <table><thead><tr><th style="text-align:left">Name</th><th style="text-align:center">Wert</th><th style="text-align:right">Einheit</th></tr></thead><tbody><tr><td style="text-align:left">A</td><td style="text-align:center">1.23</td><td style="text-align:right">m</td></tr><tr><td style="text-align:left">B</td><td style="text-align:center">4.56</td><td style="text-align:right">m</td></tr></tbody></table> |

In `tabular{lcr}` definiert jede Position eine Spalte (`l`, `c`, `r`). `&` trennt Spalten, `\\` beendet eine Tabellenzeile.

Spaltentypen:

- `l` links,
- `c` zentriert,
- `r` rechts,
- `p{Breite}` Absatzspalte.

## 2. Professionelle Linien mit `booktabs`

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{tabular}{lrr}<br>  \toprule<br>  Probe & Messung 1 & Messung 2 \\\\<br>  \midrule<br>  A & 12.3 & 45.6 \\\\<br>  B & 11.9 & 47.1 \\\\<br>  \bottomrule<br>\end{tabular}</code></pre> | <table><thead><tr><th style="text-align:left">Probe</th><th style="text-align:right">Messung 1</th><th style="text-align:right">Messung 2</th></tr></thead><tbody><tr><td style="text-align:left">A</td><td style="text-align:right">12.3</td><td style="text-align:right">45.6</td></tr><tr><td style="text-align:left">B</td><td style="text-align:right">11.9</td><td style="text-align:right">47.1</td></tr></tbody></table> |

`\toprule`, `\midrule` und `\bottomrule` kommen aus `booktabs` und ersetzen harte Doppel-/Vertikallinien durch saubere horizontale Struktur.

## 3. Tabellen als Float

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{table}[htbp]<br>  \centering<br>  \caption{Messwerte}<br>  \label{tab:messwerte}<br>  ...<br>\end{table}</code></pre> | <table><caption>Messwerte</caption><thead><tr><th>Beispiel</th><th>Wert</th></tr></thead><tbody><tr><td>A</td><td>1.23</td></tr></tbody></table> |

`table` ist eine Float-Umgebung; `[htbp]` gibt Platzierungswünsche an. `\label` sollte nach `\caption` stehen, damit die Tabellenreferenz korrekt ist.

## 4. Mehrspaltige Zellen

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\multicolumn{2}{c}{Kopf}</code></pre> | <table><thead><tr><th colspan="2" style="text-align:center">Kopf</th></tr></thead><tbody><tr><td>Spalte 1</td><td>Spalte 2</td></tr></tbody></table> |

`\multicolumn{2}{c}{...}` fasst zwei Spalten zu einer Zelle zusammen; `c` gibt die Ausrichtung des zusammengefassten Inhalts an.

## 5. Minipage für nebeneinanderliegende Inhalte

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{minipage}[t]{.48\textwidth}<br>Linker Inhalt<br>\end{minipage}<br>\hfill<br>\begin{minipage}[t]{.48\textwidth}<br>Rechter Inhalt<br>\end{minipage}</code></pre> | <table><tbody><tr><td style="width:48%; border:1px solid #d8d8d8;">Linker Inhalt</td><td style="width:4%; border:none;"></td><td style="width:48%; border:1px solid #d8d8d8;">Rechter Inhalt</td></tr></tbody></table> |

`minipage` erzeugt eine Box mit fester Breite. `[t]` richtet beide Boxen oben aus, `\hfill` verteilt den horizontalen Abstand dazwischen.


## 7. Tabellenqualität

- Einheiten in Kopfzeilen,
- Dezimalstellen konsistent,
- Tabellen nicht überladen,
- jede Tabelle mit Aussage im Fließtext einführen.
