# Querverweise, Links und Literatur

## Interne Verweise

```latex
\section{Methode}\label{sec:methode}
Siehe Abschnitt~\ref{sec:methode}.
```

## Klickbare Links

```latex
\usepackage[hidelinks]{hyperref}
```

`hyperref` möglichst spät in der Präambel laden.

## Literatur mit `biblatex` (modern)

Präambel:

```latex
\usepackage[
  backend=biber,
  style=authoryear,
  sorting=nyt
]{biblatex}
\addbibresource{literatur.bib}
```

Im Text zitieren:

```latex
\textcite{knuth1984} zeigt ...
Später wurde das bestätigt \parencite{lamport1994}.
```

Literaturverzeichnis ausgeben:

```latex
\printbibliography
```

## Beispiel einer `.bib`-Datei

```bibtex
@book{lamport1994,
  author    = {Leslie Lamport},
  title     = {LaTeX: A Document Preparation System},
  year      = {1994},
  publisher = {Addison-Wesley}
}
```

## Kompilierung mit Literatur

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```
