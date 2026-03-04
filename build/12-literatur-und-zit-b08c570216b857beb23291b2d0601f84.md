# Literatur und Zitieren

## 1. Ziel: Einheitliches, nachvollziehbares Zitieren

Gute Literaturarbeit bedeutet:

- vollständige Metadaten,
- konsistenter Stil,
- eindeutige Zitierstellen,
- reproduzierbare Erstellung des Verzeichnisses.

## 2. Moderner Standard: `biblatex` mit `biber`

Präambel:

```latex
\usepackage[
  backend=biber,
  style=authoryear,
  sorting=nyt
]{biblatex}
\addbibresource{literatur.bib}
```
`backend=biber` legt das Auswertungswerkzeug fest. `style=authoryear` bestimmt das Zitatformat, und `\addbibresource{...}` bindet die `.bib`-Datei ein.

Zitate:

```latex
\textcite{lamport1994} beschreibt die Grundlagen.
Eine alternative Darstellung findet sich in \parencite{knuth1984}.
```
`\textcite{...}` erzeugt ein Autor-im-Text-Zitat, `\parencite{...}` ein Klammerzitat. Die Schlüssel in `{...}` müssen exakt mit den Bib-Einträgen übereinstimmen.

Literaturverzeichnis:

```latex
\printbibliography
```
Dieser Befehl gibt alle tatsächlich zitierten Einträge als Literaturverzeichnis aus (abhängig von Stil/Filteroptionen).

## 3. Build-Ablauf

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

## 4. Beispiel einer `.bib`-Datei

```bibtex
@book{lamport1994,
  author    = {Leslie Lamport},
  title     = {LaTeX: A Document Preparation System},
  publisher = {Addison-Wesley},
  year      = {1994}
}

@book{knuth1984,
  author    = {Donald E. Knuth},
  title     = {The TeXbook},
  publisher = {Addison-Wesley},
  year      = {1984}
}
```
`@book` ist der Eintragstyp, `lamport1994` der Zitier-Schlüssel. Felder wie `author`, `title`, `publisher` und `year` liefern die Metadaten für die Ausgabe.

## 5. Einträge sorgfältig pflegen

- Autorennamen konsistent schreiben,
- Titel nicht zufällig kürzen,
- Jahr/Verlag/DOI (falls vorhanden) ergänzen,
- Schlüssel sprechend benennen.

## 6. Quellen aus MathSciNet und arXiv

Für mathematische Literatur sind MathSciNet und arXiv besonders wichtig:

- MathSciNet liefert kuratierte bibliografische Daten, oft inkl. `doi`, Journaldaten und `mrnumber`.
- arXiv liefert Preprints mit stabiler Kennung (z. B. `arXiv:2101.01234`), oft vor der Journalveröffentlichung.

Praktischer Workflow:

1. Eintrag aus MathSciNet/arXiv übernehmen.
2. Metadaten prüfen (Autor:innen, Titel, Jahr, Journal).
3. Bei arXiv nach Möglichkeit zusätzlich DOI/Journaldaten ergänzen, sobald publiziert.
4. Einen stabilen, sprechenden Schlüssel vergeben.

Beispiel für arXiv mit `biblatex`-Feldern:

```bibtex
@online{beispiel2021,
  author       = {Max Beispiel and Erika Muster},
  title        = {Ein interessantes Resultat},
  year         = {2021},
  eprint       = {2101.01234},
  eprinttype   = {arxiv},
  eprintclass  = {math.NT},
  url          = {https://arxiv.org/abs/2101.01234}
}
```

Für veröffentlichte Arbeiten sollte die zitierfähige Journalversion bevorzugt werden; die arXiv-Version bleibt als Ergänzung sinnvoll.

## 7. Historischer Hintergrund

In älteren Kursen wurde oft BibTeX mit `\bibliographystyle`/`\bibliography` verwendet.
Der heutige Standard in diesem Kurs ist `biblatex` + `biber`, weil er flexibler und sprachsensibler ist.

## 8. Typische Literaturfehler

- `Citation ... undefined`: Schlüssel fehlt oder Tippfehler
- leeres Verzeichnis: `biber` nicht ausgeführt
- inkonsistente Ausgabe: Daten in `.bib` uneinheitlich
