# Index und Stichwortverzeichnis

## 1. Wozu ein Index?

Ein Index erhöht die Nutzbarkeit längerer Dokumente deutlich,
vor allem bei Skripten, Büchern und Nachschlagewerken.

## 2. Grundaufbau

Präambel:

```latex
\usepackage{makeidx}
\makeindex
```
`makeidx` aktiviert die Indexfunktionen. `\makeindex` initialisiert den Index für das gesamte Dokument.

Im Text:

```latex
Das Stichwort LaTeX\index{LaTeX} erscheint im Index.
```
`\index{...}` erzeugt einen Indexeintrag genau an dieser Textstelle; beim Build werden alle Einträge gesammelt und sortiert.

Ausgabe:

```latex
\printindex
```
`\printindex` gibt das fertige Stichwortverzeichnis an der gewünschten Stelle aus.

## 3. Build-Ablauf mit Index

Typischer Ablauf:

1. `pdflatex main.tex`
2. `makeindex main`
3. `pdflatex main.tex`

## 4. Qualität eines guten Index

- relevante Fachbegriffe aufnehmen,
- Synonyme einheitlich behandeln,
- keine überfrachteten Einzelwörter,
- sinnvolle Untereinträge.

## 5. Untereinträge

```latex
\index{Integral!numerisch}
\index{Integral!analytisch}
```
Das `!` trennt Haupteintrag und Untereintrag. So werden thematisch zusammengehörige Begriffe sauber gruppiert.

## 6. Hinweise

In kurzen Hausübungen ist ein Index meist unnötig.
Bei längeren Lehrtexten lohnt er sich sehr.
