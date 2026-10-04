# Psychedelic Portal Garden v9

## Portal visibility
Both entry and return portals use a strong red emissive ring plus a larger pulsing red halo.

## VR -> AR return fix
The previous return detector assumed one specific local Z direction. Depending on placement/orientation, the user could approach the VR return portal from the opposite local side, so it never armed/crossed correctly.

v9 arms the return portal from either side and triggers only when:
1. the head was clearly at least 0.48 m from the portal plane,
2. the head is inside the portal aperture,
3. local Z actually changes sign across a ±0.10 m dead-zone.

The warp then hides the virtual garden and restores the transparent AR/MR background.
