# Psychedelic Portal Garden v11

## Sichtbarkeit
- AR/MR: ausschließlich das rote Eingangsportal ist sichtbar.
- VR-Garten: ausschließlich das rote Ausgangs-/Rückportal ist sichtbar.
- Beim Warp werden die Portale explizit umgeschaltet.

## Bidirektionale Portalnutzung
Beide Portale können von beiden Seiten durchschritten werden.
Die Erkennung:
1. Nutzer muss sich mindestens 0,45 m auf einer beliebigen Seite der Portalebene befinden.
2. Portal wird für genau diese Annäherung aktiviert.
3. Kopf/Kamera muss innerhalb der Ringöffnung sein.
4. Lokale Z-Position muss die Portalebene mit einer ±0,10-m-Totzone vollständig kreuzen.
5. Erst dann wird der Warp ausgelöst.

Der Portalabstand aus v10 bleibt konfigurierbar, Default 1,0 m.
