# Textsatz, Absätze und Typografie

## 1. Grundregeln des Textsatzes

- Mehrere Leerzeichen im Quelltext werden zu einem Leerzeichen.
- Ein leerer Zeilenabstand erzeugt einen neuen Absatz.
- Zeilenumbrüche im Quelltext sind keine harten PDF-Zeilenumbrüche.

## 2. Absatzgestaltung

```latex
Dies ist der erste Absatz.

Dies ist der zweite Absatz.
```
Die Leerzeile zwischen den Sätzen erzeugt einen neuen Absatz. Ohne Leerzeile würden beide Zeilen zum selben Absatz gehören.

Absätze sollten inhaltlich begründet sein, nicht nur optisch.

## 3. Hervorhebungen richtig nutzen

```latex
\textbf{fett}, \textit{kursiv}, \emph{betont}
```
Alle drei Befehle nutzen geschweifte Klammern für den Wirkbereich. `\emph{...}` ist semantisch, weil LaTeX je nach Kontext die passende Betonung wählt.

Empfehlung:

- `\emph{...}` für semantische Betonung,
- nicht mehrere Hervorhebungsarten gleichzeitig stapeln.

## 4. Listen

```latex
\begin{itemize}
  \item Erstes Argument
  \item Zweites Argument
\end{itemize}

\begin{enumerate}
  \item Schritt A
  \item Schritt B
\end{enumerate}
```
`\begin{...}` und `\end{...}` öffnen und schließen jeweils eine Umgebung. `\item` startet pro Listenpunkt einen neuen Eintrag.

## 5. Ausrichtung und Blocksatz

Standard in LaTeX ist Blocksatz mit guter Silbentrennung.
Manuelle Eingriffe sollten selten sein.

## 6. Sonderzeichen im Text

Folgende Zeichen müssen als Befehl gesetzt werden:

```latex
\% \$ \& \# \_ \{ \}
```
Das vorangestellte `\` maskiert Sonderzeichen, damit sie als Zeichen und nicht als LaTeX-Steuerzeichen erscheinen.

## 7. Deutsche Typografie

- `babel` aktiviert korrekte Trennung und deutsche Bezeichnungen.
- `csquotes` liefert korrekte Anführungszeichen im Sprachkontext.

Beispiel:

```latex
\enquote{Das ist ein korrekt gesetztes Zitat.}
```
`\enquote{...}` setzt sprachabhängig korrekte Anführungszeichen. Über `babel`/`csquotes` passt sich die Form automatisch an die Dokumentsprache an.

## 8. Lesbarkeit verbessern

- kurze, klare Sätze,
- konsistente Terminologie,
- keine manuelle Abstandsakrobatik,
- saubere Struktur vor Formatdetails.
