# Zähler, Nummerierung und Theorem-Umgebungen

## 1. Zählerkonzept

LaTeX verwaltet viele Nummern intern über Zähler:

- `section`, `subsection`
- `equation`
- `figure`, `table`
- eigene Zähler

## 2. Eigene Zähler

```latex
\newcounter{beispiel}
\setcounter{beispiel}{0}
\refstepcounter{beispiel}
```
`\newcounter` legt einen neuen Zähler an, `\setcounter` setzt den Startwert. `\refstepcounter` erhöht den Zähler und macht ihn gleichzeitig referenzierbar.

Ausgabe:

```latex
Beispiel~\arabic{beispiel}
```
`\arabic{beispiel}` formatiert den Zähler als normale Dezimalzahl.

## 3. Format der Nummerierung

Beispiel für Abschnittsbezug bei Gleichungen:

```latex
\numberwithin{equation}{section}
```
Damit wird der Gleichungszähler bei jeder neuen Section zurückgesetzt und mit der Section-Nummer kombiniert.

Dann entstehen Nummern wie `(3.5)` statt globaler Nummern.

## 4. Theorem-Umgebungen

```latex
\newtheorem{satz}{Satz}[section]
\newtheorem{lemma}[satz]{Lemma}
\newtheorem{definition}[satz]{Definition}
\theoremstyle{remark}
\newtheorem{bemerkung}[satz]{Bemerkung}
```
`\theoremstyle{remark}` ändert den Stil der danach definierten Umgebungen. Durch `[satz]` nutzen mehrere Umgebungen dieselbe Nummerierungsreihe.

## 5. Beispielblock

```latex
\begin{satz}[Zwischenwertsatz]
Sei $f$ stetig auf $[a,b]$.
Dann nimmt $f$ jeden Zwischenwert an.
\end{satz}

\begin{proof}
Standardbeweis aus der Analysis.
\end{proof}
```
Der optionale Titel `[Zwischenwertsatz]` erscheint in der Satzüberschrift. `proof` setzt automatisch eine Beweisüberschrift und das Abschlusszeichen.

## 6. Referenzierbar machen

```latex
\begin{satz}\label{thm:zww}
...
\end{satz}

Siehe Satz~\ref{thm:zww}.
```
Das Label sitzt innerhalb der Umgebung und referenziert genau diese Satznummer; über `\ref{thm:zww}` wird sie im Text ausgegeben.

## 7. Empfehlungen

- gemeinsame Nummerierung für verwandte Umgebungen,
- konsistente Benennung (`thm:`, `lem:`, `def:`),
- keine manuelle Nummerierung per Hand.
