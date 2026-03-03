# Dateien, Build-Kette und Fehlersuche

## 1. Was passiert beim Kompilieren?

Beim Lauf mit `pdflatex` entstehen Hilfsdateien, in denen Informationen
für Verzeichnisse, Referenzen und Literatur gespeichert werden.

## 2. Typische Dateien

- `main.tex`: Hauptdatei
- `main.pdf`: Ergebnis
- `main.log`: Fehlermeldungen und Warnungen
- `main.aux`: Referenzen
- `main.toc`: Inhaltsverzeichnis
- `main.bcf`/`main.bbl`: Literaturdaten

## 3. Standardabläufe

Ohne Literatur:

```bash
pdflatex main.tex
pdflatex main.tex
```

Mit Literatur:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

## 4. Fehler systematisch lesen

1. Erste echte Fehlermeldung im Log suchen.
2. Betroffene Zeile im Quelltext prüfen.
3. Kürzliche Änderungen rückverfolgen.
4. Erneut kompilieren.

## 5. Häufige Fehlertypen

### `Undefined control sequence`

Befehl falsch geschrieben oder Paket fehlt.

### `Missing $ inserted`

Mathemodus fehlt oder wurde unbeabsichtigt verlassen.

### `Runaway argument`

Klammern oder Umgebungen nicht korrekt geschlossen.

### `File ... not found`

Dateiname/Pfad falsch oder Datei nicht im Projekt.

## 6. Warnungen ernst nehmen

Nicht jede Warnung ist kritisch, aber wiederkehrende Warnungen
führen oft zu späteren Layout- oder Referenzproblemen.

## 7. Checkliste vor Abgabe

- alle Referenzen aufgelöst,
- Literatur vollständig,
- keine gravierenden Overfull-Warnungen,
- Abbildungen/Tabellen korrekt beschriftet,
- PDF visuell konsistent.
