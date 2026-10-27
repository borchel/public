# Strudel Studio v0.2.3 — Event-Highlighting repariert

## Fehlerbehebung
In v0.2.2 konnte ein ausgelöstes Event (oft Step 1) gelb markiert bleiben, obwohl der Playhead weiterlief. Ursache: `event-flash` wurde im Scheduler-Pfad nur beim CSS-Event `animationend` entfernt. Dieses Ereignis kann ausbleiben, beispielsweise bei Hintergrund-Tabs oder unterbrochenen Animationen. Der Fallback-Pfad entfernte die Klasse überhaupt nicht.

In v0.2.3 erhalten alle Event-Highlights eine feste Lebensdauer von 170 ms. Eine Bereinigung erfolgt in jedem Visualisierungsframe, beim Stop/Neustart und beim Neuaufbau des Pattern-Editors. Der Playhead bleibt davon unabhängig.

## Test
1. Demo starten und Kick-Pattern öffnen.
2. Step 1 sollte beim Anschlag kurz aufblitzen, danach wieder die normale Darstellung zeigen.
3. Playhead soll unabhängig davon alle 16 Steps durchlaufen.
4. Zwischen Tabs wechseln, zurückkehren, Stop/Play wiederholen.

## Einschränkung
Die Audioausgabe wurde nicht im Browser geprüft. Die Änderung betrifft nur die CSS-Markierung, nicht die Strudel-Audioengine.
