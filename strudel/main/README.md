# Strudel Studio v0.1

Erster ausführbarer Architekturprototyp auf Basis des Strudel Performance Controllers v0.4.7.

## Start

Im Verzeichnis `strudel-studio-v0.1` ausführen:

```bash
python -m http.server 8000
```

Dann `http://localhost:8000` im Browser öffnen. Zum ersten Start wird Internet benötigt: `@strudel/web@1.3.0` wird über unpkg geladen und Sample-Mappings werden bei Bedarf registriert.

## Umfang

- Original-Strudel-Runtime, Soundbank-Initialisierung und serialisierte Audio-Kommandos
- Visuelle 16-Step-Patterns und freie Strudel-Code-Patterns
- Track-Editor, Mixer, Clip-Timeline (4-Cycle-Raster), Arrangement-Compiler
- Import/Export von Projekt-JSON; Legacy-Code der v0.4.7 integriert
- Lokales Speichern (localStorage) und Service-Worker für die App-Shell
- WebAudio-, Strudel-Synth- und Sample-Diagnose

## Bekannte Grenzen

- Die Anwendung wurde statisch geprüft, aber nicht mit Audio im Browser verifiziert.
- CDN-Runtime und Audio-Samples sind noch nicht offline gebündelt. Eine vollständige Offline-PWA ist deshalb noch nicht erreicht.
- Der Taktzähler ist eine UI-Schätzung, keine Scheduler-Synchronisierung.
- Arrangement unterstützt derzeit keine überlappenden Clips pro Track.
- Beim Playback-Update wird das gesamte Pattern neu evaluiert.
- Legacy-Code wird unverändert evaluiert, nicht automatisch in Tracks umgewandelt.
- Importierter JavaScript-Code wird ausgeführt: nur vertrauenswürdige Dateien öffnen.
- Für die erste Version ist der JSON-Export das verlässlichere Backup; localStorage ist kein Ersatz für eine Datei.


## v0.1.2 – Soundbank-Fehlerbehandlung

Die VCSL- oder Dirt-Registry kann je nach Netzwerk, CORS, Hosting-Sandbox oder Serverzustand nicht erreichbar sein. Fehler einzelner Registries werden beim Start abgefangen und angezeigt; die Engine-Initialisierung wird fortgesetzt. Dies garantiert **nicht**, dass Samples aus der fehlgeschlagenen Registry abspielbar sind. Für einen Synthesizer-Test die Soundbank **Nur Synth** auswählen, dann Play oder Test B. Nach erstmaliger Initialisierung erfordert ein Soundbank-Wechsel ein Neuladen. Ein offlinefähiges Samplepaket ist noch nicht enthalten.


## Neu in v0.1.2: Playback-Highlighting

- Aktive Clip-Zelle und Track im Arrangement werden hervorgehoben.
- Aktive Patterns werden in der Bibliothek markiert.
- Der aktuelle Step eines ausgewählten, gerade spielenden Structured-Patterns erhält einen gelben Playhead.
- Der Event-Indikator nennt Treffer auf aktiven strukturierten Tracks.
- Freie Code-Patterns werden nur auf Pattern-Ebene markiert. Legacy-Kompositionen erhalten keine Track-/Event-Zuordnung.
- **Timing-Einschränkung:** Die Darstellung basiert auf `performance.now()` und BPM und ist eine Annäherung, keine Rückmeldung des Strudel-Audio-Schedulers. Die Anzeige kann bei Audio-Latenz, langen Patterns und Live-Neuevaluation abweichen.
