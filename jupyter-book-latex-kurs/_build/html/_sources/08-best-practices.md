# Best Practices und Fehlersuche

## Empfehlungen für stabile Projekte

- Inhalte in mehrere Dateien aufteilen (`\input` oder `\include`).
- Einheitliche Benennung für Labels (`sec:`, `fig:`, `tab:`, `eq:`).
- Änderungen früh und oft kompilieren.
- Warnungen im Log ernst nehmen.

## Typische Fehlermeldungen

### `Undefined control sequence`

Ursache: Tippfehler oder fehlendes Paket.

### `Missing $ inserted`

Ursache: Mathe-Syntax außerhalb von Mathemodus oder umgekehrt.

### `Reference ... undefined`

Ursache: Zu wenige Kompilierläufe oder falsches `\label`.

### `Citation ... undefined`

Ursache: `biber` nicht ausgeführt oder Schlüssel in `.bib` fehlt.

## Qualitätscheck vor Abgabe

- PDF ohne Overfull/Underfull-Warnungsflut?
- Alle Referenzen auflösbar?
- Einheitliche Schreibweise, korrekte Typografie?
- Literatur vollständig und konsistent?
- Abbildungen und Tabellen korrekt beschriftet?
