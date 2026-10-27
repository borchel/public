# Strudel Studio v0.2.0 – Visual Sync

Basiert auf der funktionierenden v0.1.3. Strudel `@strudel/web@1.3.0`, Soundbank-Fallback, Projekt-JSON, Legacy-Modus, Pattern-Editor und Mixer bleiben erhalten.

## Änderungen

- Zeitreferenz für die Visualisierung bevorzugt `AudioContext.getOutputTimestamp()` und fällt auf `AudioContext.currentTime` bzw. `performance.now()` zurück.
- Einstellbarer visueller Offset von -300 bis +300 ms; wird lokal gespeichert. Positive Werte verschieben die Anzeige nach hinten.
- Pro 1/32-Cycle-Zeitfenster nur eine Eventabfrage und eine Eventprotokoll-Aktualisierung; weniger mehrfaches Flackern und redundante Abfragen.
- Bei Stop und Play werden Zeitreferenz und Eventfenster zurückgesetzt.
- Status zeigt die aktuell verwendete Zeitbasis an.

## Wichtig: technische Grenze

Diese Version **verwendet keine Strudel-Scheduler-Callbacks**. `getOutputTimestamp()` synchronisiert die UI-Uhr mit der Web-Audio-Ausgabezeit, aber nicht mit dem tatsächlichen Beginn der Strudel-Events. Der Zeitpunkt der ersten `evaluate()`-Ausgabe ist nicht aus der verwendeten API ableitbar. Auch Audio-Geräte- und Sample-Latenzen können Abweichungen verursachen. Die Haps stammen aus `queryArc()`, ihre Anzeige erfolgt anhand einer modellbasierten Zeitachse. Daher ist dies eine Verbesserung der Zeitreferenz und Kalibrierung, **keine samplegenaue Event-Synchronisation**.

## Start

`index.html` auf `http://localhost` oder einem HTTPS-Host öffnen. Die Strudel-Runtime wird weiter über das CDN geladen, und Samples benötigen Internet. Bei Problemen mit den Soundbanks „Nur Synth“ auswählen.

## Test

1. Demo laden und Play starten.
2. Status der Audio-Uhr prüfen.
3. 16tel/32stel-Highlights mit den hörbaren Anschlägen vergleichen.
4. Offset bei Bedarf anpassen und Stop/Play wiederholen.
5. Legacy-Modus prüfen: dieser besitzt weiterhin keine Track-/Event-Zuordnung.

## Bekannte Grenzen

- Kein Scheduler-Callback und kein exaktes Event-Audio-Timestamp-Mapping.
- Visuelle 16-Step-Raster; Event-Abfragen mit 32 Unterteilungen.
- Projekt ist noch keine vollständig offlinefähige PWA.
- Beliebiger importierter JavaScript-Code wird ausgeführt: nur vertrauenswürdige Quellen verwenden.
- Keine Audio-Browsertests in dieser Umgebung.
