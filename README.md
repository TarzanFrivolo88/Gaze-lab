# Gaze Lab

Webcam eye tracker that runs entirely in the browser. Estimates where on the screen you're looking, which line you're reading, and logs simple focus signals (on-screen time, look-aways, blink rate, reading streaks).

- Face and iris landmarks: MediaPipe Face Landmarker (loaded from CDN)
- Gaze mapping: per-user calibration (9–16 points) + ridge regression, with a validation step that reports accuracy
- Reading mode: line tracking based on return-sweep detection and a small HMM over the text's lines

Video never leaves the page. Open `index.html` over HTTPS (or localhost) so the browser allows camera access.
