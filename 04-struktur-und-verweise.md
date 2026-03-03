# Struktur, Inhaltsverzeichnis und Querverweise

## 1. Überschriftenebenen

```latex
\section{Einleitung}
\subsection{Problemstellung}
\subsubsection{Beispieldaten}
```

In `report` und `book` kommt zusätzlich `\chapter{...}` dazu.

## 2. Inhaltsverzeichnis

```latex
\tableofcontents
```

Nach Änderungen an Überschriften: mindestens zweimal kompilieren.

## 3. Labels und Referenzen

```latex
\section{Methode}\label{sec:methode}
Siehe Abschnitt~\ref{sec:methode}.
```

Für Gleichungen:

```latex
\begin{equation}
  E = mc^2
  \label{eq:einstein}
\end{equation}

Vgl. Gleichung~\eqref{eq:einstein}.
```

## 4. Label-Konventionen

Empfehlte Präfixe:

- `sec:` für Abschnitte
- `fig:` für Abbildungen
- `tab:` für Tabellen
- `eq:` für Gleichungen
- `thm:` für Theoreme

## 5. Klickbare Dokumente mit `hyperref`

```latex
\usepackage[hidelinks]{hyperref}
```

Damit werden interne Verweise und Inhaltsverzeichnis-Einträge klickbar.

## 6. Typische Referenzprobleme

- `??` im PDF: meist zu wenige Läufe oder falsches `\label`
- falsche Nummer: Label versehentlich außerhalb der Umgebung gesetzt
- Seitenverweis falsch: nach großen Umbrüchen erneut kompilieren

## 7. Beispiel: saubere Referenzkette

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=.7\textwidth]{bilder/plot.pdf}
  \caption{Messkurve}
  \label{fig:messkurve}
\end{figure}

Wie in Abbildung~\ref{fig:messkurve} zu sehen, ...
```
