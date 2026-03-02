# Mathematik in LaTeX

## Inline und abgesetzte Formeln

Inline:

```latex
Die Gleichung $a^2+b^2=c^2$ ist bekannt.
```

Abgesetzt:

```latex
\[
  a^2+b^2=c^2
\]
```

## Nummerierte Gleichungen

```latex
\begin{equation}
  E = mc^2
  \label{eq:einstein}
\end{equation}
```

Referenz im Text:

```latex
Wie in Gleichung~\ref{eq:einstein} gezeigt, ...
```

## Mehrzeilige Formeln mit `align`

```latex
\begin{align}
  f(x) &= x^2 + 2x + 1 \\
       &= (x+1)^2
\end{align}
```

- `&` markiert Ausrichtungspunkte.
- `\\` beendet eine Zeile.

## Typische Mathe-Pakete

```latex
\usepackage{amsmath,amssymb,amsthm}
```

## Theoreme und Beweise

```latex
\newtheorem{satz}{Satz}

\begin{satz}
Jede gerade Zahl ist durch 2 teilbar.
\end{satz}

\begin{proof}
Folgt direkt aus der Definition der Geradzahligkeit.
\end{proof}
```
