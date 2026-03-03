# Struktur, Inhaltsverzeichnis und Querverweise

## 1. Überschriftenebenen

```latex
\section{Einleitung}
\subsection{Problemstellung}
\subsubsection{Beispieldaten}
```
Die Befehle erzeugen hierarchische Überschriftenebenen. Die Titel stehen jeweils in `{...}` und erscheinen automatisch im Inhaltsverzeichnis.

In `report` und `book` kommt zusätzlich `\chapter{...}` dazu.

## 2. Inhaltsverzeichnis

```latex
\tableofcontents
```
`\tableofcontents` erstellt das Inhaltsverzeichnis aus den vorhandenen Überschriften. Nach Strukturänderungen sind meist zwei Läufe nötig, damit alles aktuell ist.

Nach Änderungen an Überschriften: mindestens zweimal kompilieren.

## 3. Labels und Referenzen

```latex
\section{Methode}\label{sec:methode}
Siehe Abschnitt~\ref{sec:methode}.
```
`\label{...}` speichert die Nummer der aktuellen Strukturstelle. `\ref{...}` gibt diese Nummer aus; `~` verhindert einen Zeilenumbruch zwischen Wort und Nummer.

Für Gleichungen:

```latex
\begin{equation}
  E = mc^2
  \label{eq:einstein}
\end{equation}

Vgl. Gleichung~\eqref{eq:einstein}.
```
`\eqref{...}` ist wie `\ref`, ergänzt aber automatisch Klammern für Gleichungsnummern.

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
`hyperref` macht Referenzen klickbar. Die Option `hidelinks` unterdrückt farbige Rahmen um Links im PDF.

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
`[htbp]` sind Platzierungswünsche für den Float. `\caption` setzt die Beschriftung und Nummer, `\label` sollte direkt danach stehen, damit `\ref` korrekt auf die Abbildung zeigt.
