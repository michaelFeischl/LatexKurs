# Makros und Wiederverwendung

## 1. Warum Makros?

Makros verbessern:

- Lesbarkeit,
- Einheitlichkeit,
- Änderbarkeit,
- Fehlerrobustheit.

Beispiel:

```latex
\newcommand{\R}{\mathbb{R}}
\newcommand{\set}[2]{\left\{#1\,\middle|\,#2\right\}}
```

Anwendung:

```latex
$\set{x\in\R}{x>0}$
```

## 2. Pflicht- und optionale Argumente

```latex
\newcommand{\norm}[1]{\left\lVert #1 \right\rVert}
\newcommand{\skalar}[2]{\left\langle #1,#2 \right\rangle}
```

## 3. Bestehende Befehle sicher ersetzen

- `\newcommand` für neue Befehle
- `\renewcommand` nur, wenn ein bestehender Befehl bewusst geändert werden soll

## 4. Makrodesign in großen Projekten

- alle Makros in `preamble/macros.tex`,
- kurze, konsistente Namen,
- keine kryptischen Einbuchstaben-Makros außer in eng begrenzten Fällen.

## 5. Schlechte und gute Makros

Schlecht:

- zu allgemeine Namen (`\x`, `\a`),
- Layout und Logik vermischt,
- harte Abstände im Makro.

Gut:

- semantische Namen (`\RealNumbers`, `\EnergyNorm`),
- stabile Klammerung,
- klare Argumentstruktur.

## 6. Beispiel für ein Theorem-Makroset

```latex
\newtheorem{satz}{Satz}[section]
\newtheorem{lemma}[satz]{Lemma}
\newtheorem{korollar}[satz]{Korollar}
```

So teilen sich alle Umgebungen eine gemeinsame Nummerierung pro Abschnitt.
