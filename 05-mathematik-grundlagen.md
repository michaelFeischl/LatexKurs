# Mathematik-Grundlagen

## 1. Mathemodus
Es gibt zwei verschieden Arten Formeln zu setzen:

1. Inline:

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">Die Folge \$x_n\$ konvergiert gegen \$0\$.</code></pre> | Die Folge $x_n$ konvergiert gegen $0$. |

`$...$` schaltet in den Inline-Mathemodus. Mit `_` erzeugst du Indizes (`x_n`), und normaler Text bleibt außerhalb der Dollarzeichen.

2. Abgesetzt:

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\\[<br>  \sum_{k=1}^{n} k = \frac{n(n+1)}{2}<br>\\]</code></pre> | $$\sum_{k=1}^{n} k = \frac{n(n+1)}{2}$$ |

`\\[ ... \\]` setzt eine abgesetzte Formel ohne Nummer. `\sum_{k=1}^{n}` verwendet unten/oben Grenzen, und `\frac{...}{...}` erzeugt einen sauber skalierten Bruch.

## 2. Wichtige Bausteine

- Exponenten: `x^2`
- Indizes: `x_i`
- kombinierte Indizes: `x_{i+1}`
- Brüche: `\frac{a}{b}`
- Wurzeln: `\sqrt{x}`, `\sqrt[n]{x}`
- Integrale: `\int_a^b f(x)\,dx`, `\iint_\Omega g\,dA`
- Normen: `\|x\|`, skaliert mit `\left\| x \right\|`
- Pfeile: `\to`, `\mapsto`, `\Rightarrow`, `\iff`
- Mengen und Zahlbereiche: `\in`, `\subseteq`, `\mathbb{R}`, `\mathbb{N}`
- Quantoren: `\forall`, `\exists`

## 3. Klammern korrekt skalieren

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\left( \frac{a}{b} \right),\quad<br>\left\\{ x \in \mathbb{R} \mid x > 0 \right\\}</code></pre> | $$\left( \frac{a}{b} \right),\quad \left\{ x \in \mathbb{R} \mid x > 0 \right\}$$ |

`\left` und `\right` passen Klammergrößen automatisch an den Inhalt an. `\mid` erzeugt den senkrechten Strich als "mit"-Trenner in Mengen.

## 4. Mathematische Funktionen

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\sin x, \log x, \exp(x), \max\\{a,b\\}</code></pre> | $$\sin x, \log x, \exp(x), \max\{a,b\}$$ |

Funktionsnamen werden als Befehle geschrieben (`\sin`, `\log`), damit sie aufrecht gesetzt werden. Bei `\max\{a,b\}` sind die geschweiften Klammern mit `\{` und `\}` maskiert.

Nicht kursiv als Variablen schreiben (`sin`, `log`), sondern Funktionsbefehle nutzen.

## 5. Nummerierte Gleichungen

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{equation}<br>  \nabla \cdot \mathbf{u} = 0<br>  \label{eq:divfrei}<br>\end{equation}</code></pre> | $$\nabla \cdot \mathbf{u} = 0$$ |

`equation` erzeugt eine nummerierte Gleichung. `\label{...}` speichert die Gleichungsnummer für spätere Verweise mit `\ref` oder `\eqref`.

## 6. Mehrzeilige Formeln (einfach)

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{align}<br>  f(x) &= x^2 + 2x + 1 \\\\<br>       &= (x+1)^2<br>\end{align}</code></pre> | $$\begin{align} f(x) &= x^2 + 2x + 1 \\ &= (x+1)^2 \end{align}$$ |

In `align` richtet `&` die Zeilen an derselben Stelle aus (hier am Gleichheitszeichen). `\\` beendet jeweils eine Zeile und startet die nächste Umformung.

## 7. Mathepakete

```latex
\usepackage{amsmath,amssymb,amsthm}
```
`amsmath`  liefert Umgebungen wie `align`, `amssymb` ergänzt mathematische Symbole, und `amsthm` stellt Theorem-/Beweis-Umgebungen bereit.

Diese Kombination deckt den Großteil wissenschaftlicher Standardfälle ab.
