# Gaze Lab

Webcam eye tracker that runs entirely in the browser. Estimates where on the screen you're looking, which line you're reading, and logs simple focus signals (on-screen time, look-aways, blink rate, reading streaks).

- Face and iris landmarks: MediaPipe Face Landmarker (loaded from CDN)
- Gaze mapping: per-user calibration (9–16 points) + ridge regression, with a validation step that reports accuracy
- Reading mode: line tracking based on return-sweep detection and a small HMM over the text's lines

Video never leaves the page. Open `index.html` over HTTPS (or localhost) so the browser allows camera access.

## Word-confirmed calibration

Calibration dots turn into words; a point only counts once you say the word. By default the word is recognised **on the device** with [Vosk](https://alphacephei.com/vosk/) compiled to WebAssembly ([vosk-browser](https://github.com/ccoreilly/vosk-browser)), limited to the calibration words so it answers within about half a second. No audio leaves the device.

Third-party files in this repo:
- `vosk/vosk.js` — vosk-browser 0.0.8, Apache-2.0
- `models/vosk-model-small-en-us-0.15.tar.gz`, `models/vosk-model-small-es-0.3.tar.gz` — Vosk models by Alpha Cephei Inc., Apache-2.0 (see `models/COPYING`, `models/NOTICE`)
