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

Ausgabe:

```latex
Beispiel~\arabic{beispiel}
```

## 3. Format der Nummerierung

Beispiel für Abschnittsbezug bei Gleichungen:

```latex
\numberwithin{equation}{section}
```

Dann entstehen Nummern wie `(3.5)` statt globaler Nummern.

## 4. Theorem-Umgebungen

```latex
\newtheorem{satz}{Satz}[section]
\newtheorem{lemma}[satz]{Lemma}
\newtheorem{definition}[satz]{Definition}
\theoremstyle{remark}
\newtheorem{bemerkung}[satz]{Bemerkung}
```

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

## 6. Referenzierbar machen

```latex
\begin{satz}\label{thm:zww}
...
\end{satz}

Siehe Satz~\ref{thm:zww}.
```

## 7. Empfehlungen

- gemeinsame Nummerierung für verwandte Umgebungen,
- konsistente Benennung (`thm:`, `lem:`, `def:`),
- keine manuelle Nummerierung per Hand.
