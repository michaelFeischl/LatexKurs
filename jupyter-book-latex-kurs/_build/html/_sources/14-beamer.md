# Beamer ausführlich: Folien, Overlays, Handout

## 1. Start mit Beamer

```latex
\documentclass{beamer}
\usepackage[ngerman]{babel}

\title{Einführung in LaTeX}
\author{Max Mustermann}
\date{\today}
```

## 2. Grundstruktur einer Präsentation

```latex
\begin{document}

\begin{frame}
  \titlepage
\end{frame}

\begin{frame}{Agenda}
  \tableofcontents
\end{frame}

\section{Motivation}
\begin{frame}{Problem}
  Inhalt
\end{frame}

\end{document}
```

## 3. Block-Umgebungen

```latex
\begin{block}{Kernaussage}
Text
\end{block}

\begin{exampleblock}{Beispiel}
Text
\end{exampleblock}

\begin{alertblock}{Achtung}
Text
\end{alertblock}
```

## 4. Overlays

Elementweise Einblendung:

```latex
\begin{itemize}
  \item<1-> Erster Punkt
  \item<2-> Zweiter Punkt
  \item<3-> Dritter Punkt
\end{itemize}
```

Mit `\pause`:

```latex
Erster Teil\pause
Zweiter Teil\pause
Dritter Teil
```

## 5. Lesbarkeit von Folien

- große Schrift,
- wenig Text pro Folie,
- klare visuelle Hierarchie,
- pro Folie eine Kernbotschaft.

## 6. Handout-Modus

```latex
\documentclass[handout]{beamer}
```

Damit entfallen Animationseffekte in einer druckfreundlichen Version.

## 7. Kompilierung

```bash
pdflatex vortrag.tex
pdflatex vortrag.tex
```

Bei Inhaltsverzeichnis/Referenzen sind mehrere Läufe normal.
