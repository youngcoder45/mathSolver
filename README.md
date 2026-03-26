## Gesture-Based Math Solver (OpenCV + MediaPipe)

This project is a **real-time hand gesture-based calculator** that lets you build and evaluate basic math expressions using only hand gestures in front of a webcam.

---

## Features

- Real-time gesture detection using webcam
- Supports multi-digit input (e.g., showing 2 → 4 → 7 becomes "247")
- Gesture-controlled arithmetic operations (`+`, `-`, `*`, `/`)
- Built-in evaluation and result display
- Hands-free **Clear**, **DELETE** and **Exit** commands
- Works using a standard webcam (no special hardware needed)

---

## Requirements

- Python 3
- A working webcam

---

## Install

```bash
pip install opencv-python mediapipe numpy
```

---

## Run

```bash
python mathSolver.py
```

Keyboard shortcuts while running:

- `q` or `Esc`: quit
- `c`: clear

---

---

## Tech Stack

| Tool        | Purpose                             |
|-------------|-------------------------------------|
| Python      | Core programming language           |
| OpenCV      | Video capture, frame rendering      |
| MediaPipe   | Hand landmark detection (21 points) |
| NumPy       | Distance computation, math logic    |

---

## Supported Gestures

| Gesture | Function |
|---|---|
| One hand showing 0–5 fingers | Append digit `0`–`5` |
| Two hands: one hand `5` + other hand `1`–`4` | Append digit `6`–`9` |
| Two hands: `1` + `1` | Append `+` |
| Two hands: `1` + `2` (either order) | Append `-` |
| Two hands: `1` + `3` (either order) | Append `*` |
| Two hands: `1` + `4` (either order) | Append `/` |
| Two hands: `0` + `0` | Evaluate (`=`) |
| Two hands: `5` + `5` | Clear |
| Two hands: `2` + `2` | Delete last char |
| Two hands: `1` + `1` with index fingertips very close | Exit |

Notes:

- Gestures are based on MediaPipe hand landmarks and finger state detection.
- The app uses a debounce delay (currently ~1.25s) to avoid repeated inputs; adjust `delay` in `mathSolver.py` if needed.

---

## Troubleshooting

- **Webcam not opening**: close other apps using the camera, or try changing the camera index in `cv.VideoCapture(0)`.
- **Laggy / missed gestures**: improve lighting, keep hands fully in frame, or reduce `delay`.

---

## Contributing

See `CONTRIBUTING.md` for setup and guidelines.

---

## Credits

- Original author: @youngcoder45
