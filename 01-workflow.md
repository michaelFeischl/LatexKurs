# Workflow: Lokal mit `pdflatex` und online mit Overleaf

## 1. Grundidee: Quelltext statt Direktformatierung

LaTeX trennt Inhalt, Struktur und Layout. Du schreibst semantischen Quelltext
(z. B. "Das ist eine Überschrift", "Das ist eine Formel"), LaTeX setzt daraus ein konsistentes PDF.

Vorteile:

- gleichmäßige Typografie,
- robuste Nummerierungen und Referenzen,
- gute Wiederverwendbarkeit bei großen Dokumenten,
- klare Versionshistorie bei Teamarbeit.

## 2. Lokale Arbeit mit `pdflatex`

Minimallauf:

```bash
pdflatex main.tex
```

Mit Literatur:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

Warum mehrere Läufe?

- Beim ersten Lauf werden Hilfsdateien erstellt (`.aux`, `.toc`, `.bcf` ...).
- Danach werden Referenzen, Verzeichnisse und Literatur aufgelöst.
- Ein letzter Lauf stabilisiert Seiten- und Nummernverweise.

## 3. Online-Arbeit mit Overleaf

Overleaf ist praktisch für schnellen Start und Zusammenarbeit.

Empfohlene Regeln:

- klare Ordnerstruktur,
- sprechende Dateinamen,
- keine riesige `main.tex`, sondern Kapiteldateien,
- Warnungen aktiv prüfen, nicht ignorieren.

## 4. Empfohlene Projektstruktur

```text
projekt/
  main.tex
  kapitel/
    01-einleitung.tex
    02-methode.tex
    03-ergebnisse.tex
  bilder/
    aufbau.pdf
    plot1.pdf
  tabellen/
    messwerte.tex
  literatur.bib
```

## 5. Dateitypen im Alltag

Typische Hilfsdateien:

- `.aux`: Referenzdaten
- `.log`: Build-Protokoll
- `.toc`: Inhaltsverzeichnis
- `.out`: PDF-Lesezeichen/Metadaten
- `.bbl`/`.bcf`: Literaturdaten

Diese Dateien sind normal und wichtig für den Buildprozess.

## 6. Qualitätsroutine nach jedem Abschnitt

1. Kompilieren.
2. Warnungen lesen.
3. PDF visuell prüfen.
4. Erst dann mit neuem Inhalt weitermachen.

```{note}
Viele LaTeX-Probleme werden klein gehalten, wenn du früh und oft kompilierst.
```
