# Kurzüberblick: Präsentationen mit Beamer

## Minimalbeispiel

```latex
\documentclass{beamer}
\usepackage[ngerman]{babel}

\title{Kurze Präsentation}
\author{Max Mustermann}
\date{\today}

\begin{document}

\begin{frame}
  \titlepage
\end{frame}

\begin{frame}{Motivation}
  \begin{itemize}
    \item Punkt 1
    \item Punkt 2
  \end{itemize}
\end{frame}

\end{document}
```

## Kompilieren

```bash
pdflatex vortrag.tex
```

## Hinweise für gute Folien

- Eine Kernaussage pro Folie
- Große Schrift, wenig Text
- Mathe nur so detailreich wie nötig
- Konsistente Struktur (Agenda, Hauptteil, Fazit)
