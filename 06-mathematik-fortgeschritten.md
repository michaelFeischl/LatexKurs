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

## 2. Text in Formeln

```latex
\begin{align}
  M &= \{x\in\mathbb{N} \mid x \text{ ist gerade}\}
\end{align}
```

Für Zwischenkommentare in mehrzeiligen Formeln:

```latex
\begin{align}
  f(x) &= x^2 + 1 \\
  \intertext{Nun differenzieren wir:}
  f'(x) &= 2x
\end{align}
```

## 3. Fallunterscheidungen

```latex
f(x)=
\begin{cases}
  x^2, & x \ge 0, \\
  -x,  & x < 0.
\end{cases}
```

## 4. Matrizen

```latex
\[
A = \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}
\]
```

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
