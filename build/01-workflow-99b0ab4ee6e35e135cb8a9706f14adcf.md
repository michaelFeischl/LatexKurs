# Workflow: Lokal mit `pdflatex` und online mit Overleaf

## 1. Grundidee: Quelltext statt Direktformatierung

LaTeX trennt Inhalt, Struktur und Layout. Du schreibst semantischen Quelltext
(z. B. "Das ist eine Überschrift", "Das ist eine Formel"), LaTeX setzt daraus ein konsistentes PDF.

Vorteile:

- gleichmäßige Typografie,
- robuste Nummerierungen und Referenzen,
- gute Wiederverwendbarkeit bei großen Dokumenten,
- klare Versionshistorie bei Teamarbeit.

## 2. Ablauf

LaTeX muss kompiliert werden, d.h., der Quelltext muss in ein PDF übersetzt werden. Dazu benötigt man einen Kompiler. Es gibt sehr viele verschiedene Varianten, wir besprechen hier nur zwei davon.

## 2.1. Lokale Arbeit mit `pdflatex`

Siehe Kapitel "Installation". Vorteil von lokaler Installation:

- Nur Open Source Software nötig
- Unabhängig von Internetverbindung
- Einfache Integration von gewohnten Entwicklungsumgebungen


 Minimal Kompilierung im Terminal

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

Warum mehrere Kompilierdurchgänge?

- Beim ersten Durchgang werden Hilfsdateien erstellt (`.aux`, `.toc`, `.bcf` ...).
- Danach werden Referenzen, Verzeichnisse und Literatur aufgelöst.
- Ein letzter Durchgang stabilisiert Seiten- und Nummernverweise.

## 2.2. Online-Arbeit mit Overleaf

Overleaf ist praktisch für schnellen Start und Zusammenarbeit (www.overleaf.com), benötigt aber einen Account.

- Overleaf hat einen online Editor und Kompiler
- Overleaf erlaubt den Download von Quelltext und PDF
- Braucht eine stabile Internetverbindung
- Overleaf ist in der Grundversion gratis, gehört aber zu einer For-Profit Firma, d.h., es gibt keine Garantie, dass es immer gratis bleibt.



## 4. Empfohlene Projektstruktur
Empfohlene Regeln:

- klare Ordnerstruktur,
- sprechende Dateinamen,
- keine riesige `main.tex`, sondern Kapiteldateien,
- Warnungen aktiv prüfen, nicht ignorieren.

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
