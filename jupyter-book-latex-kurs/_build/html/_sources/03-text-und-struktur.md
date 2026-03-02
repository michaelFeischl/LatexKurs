# Text, Gliederung und Struktur

## Abschnitte

```latex
\section{Einleitung}
\subsection{Motivation}
\subsubsection{Beispiel}
```

Für längere Arbeiten sind `report` oder `book` oft geeigneter als `article`.

## Inhaltsverzeichnis

```latex
\tableofcontents
```

Nach dem ersten Lauf ist das Verzeichnis meist unvollständig; danach erneut kompilieren.

## Listen

```latex
\begin{itemize}
  \item Punkt A
  \item Punkt B
\end{itemize}

\begin{enumerate}
  \item Schritt 1
  \item Schritt 2
\end{enumerate}
```

## Hervorhebungen

```latex
\textbf{fett}, \textit{kursiv}, \emph{betont}
```

## Saubere Textarbeit

- Ein leerer Quelltext-Zeilenabstand erzeugt einen neuen Absatz.
- Mehrere Leerzeichen im Quelltext werden zu einem Leerzeichen.
- Trenne Inhalt und Layout: keine manuellen Abstände als „Layout-Reparatur“.

## Nützliche Pakete für Lesbarkeit

- `microtype` verbessert Umbruch und Grauwert.
- `babel` sorgt für korrekte deutsche Silbentrennung.
- `csquotes` vereinfacht sprachabhängige Anführungszeichen.
