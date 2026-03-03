# Mathematik-Grundlagen

## 1. Mathemodus

Inline:

```latex
Die Folge $x_n$ konvergiert gegen $0$.
```

Abgesetzt:

```latex
\[
  \sum_{k=1}^{n} k = \frac{n(n+1)}{2}
\]
```

## 2. Wichtige Bausteine

- Exponenten: `x^2`
- Indizes: `x_i`
- kombinierte Indizes: `x_{i+1}`
- Brüche: `\frac{a}{b}`
- Wurzeln: `\sqrt{x}`, `\sqrt[n]{x}`

## 3. Klammern korrekt skalieren

```latex
\left( \frac{a}{b} \right),\quad
\left\{ x \in \mathbb{R} \mid x > 0 \right\}
```

## 4. Mathematische Funktionen aufrecht

```latex
\sin x, \log x, \exp(x), \max\{a,b\}
```

Nicht kursiv als Variablen schreiben (`sin`, `log`), sondern Funktionsbefehle nutzen.

## 5. Nummerierte Gleichungen

```latex
\begin{equation}
  \nabla \cdot \mathbf{u} = 0
  \label{eq:divfrei}
\end{equation}
```

## 6. Mehrzeilige Formeln (einfach)

```latex
\begin{align}
  f(x) &= x^2 + 2x + 1 \\
       &= (x+1)^2
\end{align}
```

## 7. Mathepakete

```latex
\usepackage{amsmath,amssymb,amsthm}
```

Diese Kombination deckt den Großteil wissenschaftlicher Standardfälle ab.
