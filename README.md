# Eye Hand Synth

Interactive webcam instrument by Tommaso Martire.
Both eyes closed = kick, left wink = hi-hat, right wink = clap, right hand drop = snare, left hand drop = tom, pupils = soft synth note, right hand fingers = tone, left hand pinch = filter.
After a blink the page keeps a burst of open and closed frames of each eye, registers them, averages, denoises (non-local means) and upscales x4 with bicubic and super-resolution. "Make beat video" then cuts those stages on a 90 BPM hip hop beat and records a webm.
After a blink, the open-eye and closed-eye crops are co-registered (skin around the eye only) and upscaled x4 with bicubic and with a super-resolution network.

## Run
The camera needs HTTPS or localhost.
- Locally: `python3 -m http.server 8000` in this folder, then open http://localhost:8000
- Online: push the folder to a GitHub repo and enable GitHub Pages.
No mouse-only fallback needed: without a camera, "demo" mode uses mouse and keyboard.

## Privacy
Everything runs in the browser. No video or image leaves your device.

## Credits
- MediaPipe Face Mesh and Hands (Apache-2.0), vendored in `vendor/`
- TensorFlow.js (Apache-2.0)
- UpscalerJS ESRGAN-slim x4 weights (MIT, trained on DIV2K), see `vendor/sr/LICENSE-esrgan-slim.txt`
