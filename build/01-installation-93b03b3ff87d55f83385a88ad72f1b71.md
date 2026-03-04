# Lokale Installation: Windows, macOS, Linux

Dieses Kapitel beschreibt die lokale Einrichtung von Latex, wenn du kein Overleaf verwenden willst.
Für die lokale Kompilierung verwenden wir `pdflatex`.

## 1. Benötigte Software

Für alle Betriebssysteme brauchst du:

- eine vollständige LaTeX-Distribution,
- ein Terminal,
- einen PDF-Viewer,
- optional einen Texteditor für `.tex`-Dateien.

```{important}
Die Kompilierung erfolgt lokal mit `pdflatex`.
Für Online-Arbeit verwendest du Overleaf.
```

## 2. Windows

### 2.1 Installation

1. Installiere **MiKTeX** oder **TeX Live**.
2. Achte darauf, dass die Programme im `PATH` verfügbar sind.
3. Starte danach ein neues Terminal (PowerShell oder Eingabeaufforderung).

### 2.2 Prüfung

```powershell
pdflatex --version
```

Wenn eine Versionsausgabe erscheint, ist die Installation grundsätzlich korrekt.

### 2.3 Erster Testlauf

Lege eine `main.tex` an (siehe Kapitel "Erstes Dokument") und führe aus:

```powershell
pdflatex main.tex
```

## 3. macOS

### 3.1 Installation

1. Installiere **MacTeX** (enthält TeX Live und Werkzeuge).
2. Öffne nach der Installation ein neues Terminal.
3. Prüfe, ob `pdflatex` gefunden wird.

### 3.2 Prüfung

```bash
pdflatex --version
```

### 3.3 Erster Testlauf

```bash
pdflatex main.tex
```

## 4. Linux

### 4.1 Installation

Empfehlung: **TeX Live** über den Paketmanager der Distribution installieren.
Je nach Distribution sind die Paketnamen unterschiedlich.
Installiere eine ausreichend vollständige TeX-Live-Auswahl, damit Standardpakete verfügbar sind.

### 4.2 Prüfung

```bash
pdflatex --version
```

### 4.3 Erster Testlauf

```bash
pdflatex main.tex
```

## 5. Optional: Literaturwerkzeug `biber`

Für Kapitel mit `biblatex`-Literaturverwaltung wird zusätzlich `biber` benötigt.
Prüfung:

```bash
biber --version
```

Wenn `biber` fehlt, installiere es über denselben Installationsweg wie die LaTeX-Distribution.

## 6. Minimaler Funktionstest für alle Systeme

1. Datei `main.tex` mit einem Minimalbeispiel anlegen.
2. Kompilieren:

```bash
pdflatex main.tex
```

3. Prüfen, ob `main.pdf` erzeugt wurde.

## 7. Häufige Installationsprobleme

### `pdflatex: command not found`

Ursache: LaTeX nicht installiert oder `PATH` nicht korrekt gesetzt.

### Pakete fehlen beim ersten Kompilierdurchgang

Ursache: unvollständige Installation.
Lösung: vollständige TeX-Distribution installieren bzw. fehlende Pakete nachinstallieren.

### `biber: command not found`

Ursache: `biber` ist nicht installiert.
Lösung: `biber` nachinstallieren und Terminal neu starten.

## 8. Empfohlener Build-Ablauf nach der Installation

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
