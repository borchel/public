# Strudel Studio v0.3.2

## Neues Datenmodell
- Instrumentenbibliothek unabhängig von Patterns (Sound/Synth, Gain, LPF).
- Structured Patterns enthalten Rhythmus, Velocity und Tonhöhe pro Step.
- Umschaltbare Step- und Piano-Roll-Ansicht; Piano-Roll erlaubt das Ein- und Ausschalten von Noten.
- Der Compiler kombiniert Pattern + Instrument + Track + Arrangement.
- Bestehende Projekt-JSONs werden beim Laden migriert; die bekannte Demo-Bassfigur wird strukturiert. Beliebiger Code bleibt als Code erhalten, um Informationsverlust zu vermeiden.
- Legacy Mare Magnetica bleibt unverändert.

## Grenzen
- Die Piano-Roll unterstützt derzeit eine Note pro Step und keine unabhängig einstellbare Notenlänge.
- Komplexe freie Strudel-Code-Patterns werden nicht automatisch konvertiert.
- Die Live-Visualisierung und Audio-Scheduler-Anbindung stammen aus v0.3.1.
- Browser-Audiofunktion ist nicht automatisiert verifiziert.

## Start
index.html in einem lokalen Webserver öffnen; Runtime und Samples benötigen Internet.
