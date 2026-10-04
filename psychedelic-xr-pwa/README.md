# Psychedelic Portal Garden v6
Einheitlicher Ablauf:
1. Wenn `immersive-ar` verfügbar: AR/MR starten, Portal real platzieren.
2. Durch das Portal gehen.
3. Automatischer Warp.
4. Psychedelischer Garten wird innerhalb derselben XR-Session vollständig virtuell dargestellt.
5. Ohne AR: Desktop/Mobil-3D-Fallback mit demselben Portalablauf.

Warum dieselbe AR-Session? Browser erlauben nicht zuverlässig einen automatischen Wechsel von `immersive-ar` zu `immersive-vr` ohne neue Benutzeraktivierung. Das visuelle Ergebnis wird daher in AR-fähigen Geräten als vollständig virtuelle Szene innerhalb der laufenden Session erzeugt.


## v7 Portal-Fix
Nach Platzierung 1,2 s Sperrzeit. Der Nutzer muss danach zuerst eindeutig auf der Vorderseite (z > 0,45 m) erkannt werden. Warp startet nur bei echter Querung der Portalebene innerhalb der Öffnung.
