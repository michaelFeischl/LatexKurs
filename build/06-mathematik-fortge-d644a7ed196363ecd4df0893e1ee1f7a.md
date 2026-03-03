# Mathematik fortgeschritten: `align`, Matrizen, Fälle, Theoremstil

## 1. Warum `align` zentral ist

`align` ist flexibler als einfache Gleichungsumgebungen:

- mehrere Zeilen,
- klare Ausrichtung über `&`,
- optionale Unterdrückung einzelner Nummern mit `\notag`.

```latex
\begin{align}
  A &= B + C \\
    &= D + E \notag \\
    &= F
\end{align}
```
`&` markiert die gemeinsame Ausrichtungsstelle aller Zeilen. `\\` trennt die Zeilen, und `\notag` unterdrückt die Nummer genau in dieser Zeile.

## 2. Text in Formeln

```latex
\begin{align}
  M &= \{x\in\mathbb{N} \mid x \text{ ist gerade}\}
\end{align}
```
`\text{...}` setzt normalen Text innerhalb der Formel. `\mathbb{N}` kommt aus `amssymb` und liefert das Symbol der natürlichen Zahlen.

Für Zwischenkommentare in mehrzeiligen Formeln:

```latex
\begin{align}
  f(x) &= x^2 + 1 \\
  \intertext{Nun differenzieren wir:}
  f'(x) &= 2x
\end{align}
```
`\intertext{...}` fügt zwischen zwei Align-Zeilen erklärenden Fließtext ein, ohne die Ausrichtung zu zerstören.

## 3. Fallunterscheidungen

```latex
f(x)=
\begin{cases}
  x^2, & x \ge 0, \\
  -x,  & x < 0.
\end{cases}
```
`cases` baut eine Fallunterscheidung mit zwei Spalten auf: links der Ausdruck, rechts die Bedingung. Das `&` trennt diese Spalten.

## 4. Matrizen

```latex
\[
A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
\]
```
`pmatrix` erzeugt eine Matrix mit runden Klammern. In jeder Zeile trennt `&` die Spalten, `\\` startet die nächste Matrixzeile.

Weitere Varianten: `matrix`, `bmatrix`, `vmatrix`.

## 5. Split-Umgebung

Für eine logisch zusammenhängende, mehrzeilige Gleichung mit gemeinsamer Nummer:

```latex
\begin{equation}
\begin{split}
  g(x) &= (x+1)^3 \\
       &= x^3 + 3x^2 + 3x + 1
\end{split}
\end{equation}
```
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
