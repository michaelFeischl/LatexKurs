# Mathematik fortgeschritten: `align`, Matrizen, Fälle, Theoremstil

## 1. Warum `align` zentral ist

`align` ist flexibler als einfache Gleichungsumgebungen:

- mehrere Zeilen,
- klare Ausrichtung über `&`,
- optionale Unterdrückung einzelner Nummern mit `\notag`.

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{align}<br>  A &= B + C \\\\<br>    &= D + E \notag \\\\<br>    &= F<br>\end{align}</code></pre> | $$\begin{align} A &= B + C \\ &= D + E \\ &= F \end{align}$$ |

`&` markiert die gemeinsame Ausrichtungsstelle aller Zeilen. `\\` trennt die Zeilen, und `\notag` unterdrückt die Nummer genau in dieser Zeile.

## 2. Text in Formeln

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{align}<br>  M &= \{x\in\mathbb{N} \mid x \text{ ist gerade}\}<br>\end{align}</code></pre> | $$\begin{align} M &= \{x\in\mathbb{N} \mid x \text{ ist gerade}\} \end{align}$$ |

`\text{...}` setzt normalen Text innerhalb der Formel. `\mathbb{N}` kommt aus `amssymb` und liefert das Symbol der natürlichen Zahlen.

Für Zwischenkommentare in mehrzeiligen Formeln:

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{align}<br>  f(x) &= x^2 + 1 \\\\<br>  \intertext{Nun differenzieren wir:}<br>  f'(x) &= 2x<br>\end{align}</code></pre> | $$\begin{align} f(x) &= x^2 + 1 \\ f'(x) &= 2x \end{align}$$ |

`\intertext{...}` fügt zwischen zwei Align-Zeilen erklärenden Fließtext ein, ohne die Ausrichtung zu zerstören.

## 3. Fallunterscheidungen

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">f(x)=<br>\begin{cases}<br>  x^2, & x \ge 0, \\\\<br>  -x,  & x < 0.<br>\end{cases}</code></pre> | $$f(x)=\begin{cases} x^2, & x \ge 0, \\ -x, & x < 0. \end{cases}$$ |

`cases` baut eine Fallunterscheidung mit zwei Spalten auf: links der Ausdruck, rechts die Bedingung. Das `&` trennt diese Spalten.

## 4. Matrizen

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\\[<br>A = <br>\begin{pmatrix}<br>      1 & 2 \\\\<br>      3 & 4<br>\end{pmatrix}<br>\\]</code></pre> | $$A=\begin{pmatrix}1 & 2 \\ 3 & 4\end{pmatrix}$$ |

`pmatrix` erzeugt eine Matrix mit runden Klammern. In jeder Zeile trennt `&` die Spalten, `\\` startet die nächste Matrixzeile.

Weitere Varianten: `matrix`, `bmatrix`, `vmatrix`.

## 5. Split-Umgebung

Für eine logisch zusammenhängende, mehrzeilige Gleichung mit gemeinsamer Nummer:

| LaTeX-Code | Ergebnis |
|---|---|
| <pre><code class="language-latex">\begin{equation}<br>\begin{split}<br>  g(x) &= (x+1)^3 \\\\<br>       &= x^3 + 3x^2 + 3x + 1<br>\end{split}<br>\end{equation}</code></pre> | $$\begin{split} g(x) &= (x+1)^3 \\ &= x^3 + 3x^2 + 3x + 1 \end{split}$$ |

`split` dient für eine mehrzeilige Gleichung mit nur einer gemeinsamen Nummer. Die Ausrichtung funktioniert wie bei `align` über `&` und `\\`.

## 6. Häufige Mathefehler

- `Missing $ inserted`: Mathemodus vergessen.
- Falsche Klammerung bei Indizes/Exponenten.
- Zu viele Ausrichtungspunkte `&` in einer Zeile.
- Manuelle Abstände als Ersatz für Struktur.

## 7. Lesbare mathematische Texte

- pro Absatz eine Idee,
- wichtige Umformungen nummerieren,
- im Fließtext auf Gleichungen verweisen,
- konsistente Symbolwahl im gesamten Dokument.
