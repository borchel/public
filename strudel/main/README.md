# Strudel Studio v0.2.2 — kontinuierlicher Pattern-Playhead

## Behobener Fehler
In v0.2.1 blieb der Pattern-Playhead beim letzten ausgelösten Event stehen, weil seine Position nur bei eintreffenden `onTrigger`-Events aktualisiert wurde.

Jetzt bestimmt der erste Strudel-Scheduler-Callback die Zeitankerposition (Audio-Zielzeit und Cycle-Position). Die Oberfläche berechnet daraus in jedem Animationsframe die laufende musikalische Position. Dadurch wandert die Step-Markierung auch über Pausen hinweg. Die Anschlags-Highlights kommen weiterhin ausschließlich aus tatsächlichen `onTrigger`-Callbacks.

## Test
1. Demo starten, Pattern-Ansicht öffnen und Kick-Pattern wählen.
2. Gelbe Playhead-Markierung muss alle 16 Steps durchlaufen, auch wenn kein Kick erklingt.
3. Tatsächliche Anschläge blitzen zusätzlich kurz auf.
4. Stop/Play mehrfach testen und Timing-Offset nach Bedarf justieren.

## Grenzen
Der Playhead wird aus einem Scheduler-Callback verankert und anschließend mit BPM fortgeschrieben. Er ist kein eigener kontinuierlicher Callback der Strudel-Engine. Tempoänderungen lösen durch erneutes Play eine neue Verankerung aus. Audio-Latenz und Browser-Timing können weiterhin kleine Abweichungen verursachen. Legacy-Kompositionen verwenden weiterhin den bisherigen Fallback. Kein tatsächlicher Browser-Audiotest durchgeführt.
