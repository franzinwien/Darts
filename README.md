# OCHE — Darts Motion Lab

Browser-basiertes Bewegungs-Analyse-Tool für Dartwürfe. Erfasst Schulter-, Ellbogen- und Handgelenks-Kinematik per **MediaPipe Pose** und berechnet Release-Winkel, Ellbogen-Drift, Peak-Geschwindigkeit und Wurf-zu-Wurf-Konsistenz — **komplett lokal im Browser**, keine Daten verlassen das Gerät.

## Live-Demo

→ **https://franzinwien.github.io/Darts/**

## So funktioniert's

1. **Setup:** Handy oder Webcam *seitlich* auf Wurfarm-Seite positionieren, ca. 2–3 m Abstand, Höhe Brust. Schulter, Ellbogen und Handgelenk müssen im Bild sein.
2. **Kalibrierung:** Rechts- oder Linkshänder wählen. Das Pose-Modell trackt automatisch die relevanten Gelenke.
3. **Aufnahme starten:** Klick auf *Aufnahme* und normal werfen. Die App erkennt Wurfphasen (Backswing → Forward → Release → Follow-through) automatisch via Speed-Profil des Handgelenks.
4. **Analyse:** Pro Wurf werden Release-Winkel (Ellbogen beim Speed-Peak), Ellbogen-Drift, Peak-Hand-Geschwindigkeit und Wurfdauer erfasst.
5. **Konsistenz-Score:** Ab 3 Würfen wird ein Gesamt-Grade (A–D) aus Drift und Release-Streuung berechnet.

## Tech-Stack

- **Pose Engine:** [MediaPipe Tasks Vision](https://developers.google.com/mediapipe) (`pose_landmarker_lite`, GPU-Delegate)
- **Rendering:** Vanilla Canvas 2D Overlay über `<video>`
- **UI:** Single-File HTML/CSS/JS, keine Build-Tools, keine Dependencies
- **Fonts:** Bebas Neue, JetBrains Mono, Fraunces (Google Fonts)
- **Hosting:** Static via GitHub Pages

## Lokale Entwicklung

```bash
python3 -m http.server 8000
```

Dann im Browser http://localhost:8000 öffnen. Kamera-Zugriff erfordert HTTPS oder `localhost`.

## Lizenz

MIT — siehe [LICENSE](./LICENSE).
