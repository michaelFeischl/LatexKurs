# Erstes LaTeX-Dokument

## Minimalbeispiel

```latex
\documentclass[a4paper,11pt]{article}
\usepackage[T1]{fontenc}
\usepackage[ngerman]{babel}
\usepackage[hidelinks]{hyperref}

\title{Mein erstes LaTeX-Dokument}
\author{Max Mustermann}
\date{\today}

\begin{document}
\maketitle

Hallo Welt! Das ist mein erster gesetzter Text.

\end{document}
```

## Kompilieren

```bash
pdflatex main.tex
```

Wenn Warnungen über fehlende Referenzen auftauchen: nochmals kompilieren.

## Häufige Anfängerfehler

- Fehlendes `\end{document}`
- Tippfehler in Befehlen (z. B. `\begin{docment}`)
- Nicht geschlossene Klammern `{...}`
- Sonderzeichen im falschen Kontext (`_`, `%`, `&`, `#`)

## Sonderzeichen escapen

```latex
\% \$ \& \# \_ \{ \}
```
