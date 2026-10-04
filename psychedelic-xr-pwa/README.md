# Psychedelic Universal XR PWA
Eine adaptive PWA für Desktop, Mobilgeräte und WebXR-Headsets.

- Desktop: 3D mit WASD + Maus
- Mobil: 3D mit Touch-Joystick + Touch-Look; AR falls `immersive-ar` verfügbar
- Quest/XR-Headset: AR/MR falls verfügbar; VR falls verfügbar; Controller-Trigger zur AR-Platzierung
- Die Buttons werden über `navigator.xr.isSessionSupported()` automatisch aktiviert/deaktiviert.

GitHub Pages: gesamten Ordner in Repository-Root hochladen und Pages für `main / root` aktivieren.
Hinweis: Three.js wird in dieser Fassung noch von jsDelivr geladen.
