# Textsatz, Absätze und Typografie

LaTeX versucht selbständig die bestmögliche Gestaltung des Textes zu finden. Man sollte nicht zu viele Vorgaben wie Zeilenumbrüche erzwingen, sondern sich eher auf die interne Optimierung verlassen.

## 1. Grundregeln des Textsatzes

- Mehrere Leerzeichen im Quelltext werden zu einem Leerzeichen.
- Ein leerer Zeilenabstand erzeugt einen neuen Absatz.
- Zeilenumbrüche im Quelltext sind keine harten PDF-Zeilenumbrüche.

## 2. Absatzgestaltung

```latex
Dies ist der erste Absatz.
Das ist kein neuer Absatz und auch kein Zeilenumbruch im PDF.

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
Nummerierte Listen `enumerate` und nicht-nummerierte Listen `itemize` können in LaTeX wie folgt erstellt werden. 

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
Die Umgebungen können beliebig tief geschachtelt werden.

## 5. Ausrichtung und Blocksatz

Standard in LaTeX ist Blocksatz mit guter Silbentrennung.
Manuelle Eingriffe sollten selten sein.

Wenn eine andere Ausrichtung wirklich nötig ist:

- linksbündig: `\begin{flushleft} ... \end{flushleft}` (oder lokal `\raggedright`)
- rechtsbündig: `\begin{flushright} ... \end{flushright}` (oder lokal `\raggedleft`) - nur wenn unbedingt nötig, z. B. für spezielle Layout-Elemente

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
