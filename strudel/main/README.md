# Strudel Studio v0.3.0 — Step-Sequencer

## Neu
- 16, 32 oder 64 Steps je Cycle für strukturierte Patterns.
- Pro Step ein Velocity-Wert (0–100 %), umgesetzt als Strudel `.gain()`-Pattern.
- Pattern duplizieren und Steps löschen.
- Rechtsklick auf einen Step öffnet dessen Velocity-Einstellung; normaler Klick schaltet den Step um.
- Der Scheduler-Playhead berücksichtigt die ausgewählte Pattern-Auflösung; Event-Highlights verwenden ebenfalls die Auflösung.
- Bestehende Projekte ohne `stepCount` oder `velocities` werden mit 16 Steps und 100 % Velocity weiterverwendet.

## Test
1. Demo starten, Pattern Kick auswählen.
2. Auf 32 oder 64 Steps umstellen, zusätzliche Anschläge setzen.
3. Rechtsklick auf einen aktiven Step, Velocity reduzieren.
4. Kontrollieren, ob der Playhead über alle Steps läuft.
5. Pattern duplizieren und als Variante bearbeiten.

## Hinweise
Das Pattern-Grid beschreibt weiterhin einen Cycle. Bei 64 Steps entspricht ein Step einem 64stel eines Cycles. Die Bearbeitung eines Patterns während der Wiedergabe startet den Strudel-Playback aktuell neu. Ein Piano-Roll, Probability, Ratchets und Microtiming sind noch nicht umgesetzt. Die Runtime und die Soundbank-Initialisierung wurden nicht verändert. Browser-Audio wurde hier nicht verifiziert.
