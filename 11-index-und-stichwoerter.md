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

Im Text:

```latex
Das Stichwort LaTeX\index{LaTeX} erscheint im Index.
```

Ausgabe:

```latex
\printindex
```

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

## 6. Hinweise

In kurzen Hausübungen ist ein Index meist unnötig.
Bei längeren Lehrtexten lohnt er sich sehr.
