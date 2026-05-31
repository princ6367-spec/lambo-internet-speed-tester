<div align="center">

# 🏎️ VELOCITÀ

### A Lamborghini-grade internet speed tester for the web.

**Animated supercar speedometer · accurate multi-stream measurement · bufferbloat detection · zero dependencies.**

[![Stack](https://img.shields.io/badge/stack-vanilla%20JS-f4c430)](#)
[![Dependencies](https://img.shields.io/badge/dependencies-0-2ea44f)](#)
[![Size](https://img.shields.io/badge/size-~38%20KB-blue)](#)
[![Single File](https://img.shields.io/badge/build_step-none-9d6bff)](#)
[![License](https://img.shields.io/badge/license-MIT-orange)](#license)

</div>

---

## Overview

**VELOCITÀ** is a production-ready internet speed tester built as a **single, self-contained HTML file** — no frameworks, no build tools, no npm install, no tracking. It measures your connection against Cloudflare's global edge network and renders the results on a luxurious, animated **Lamborghini-style speedometer** with a live throughput chart, a graded report card, and shareable exports.

It's designed to look like a supercar dashboard and to **measure like a real tool** — taking its time with multiple parallel streams and time-boxed sampling so the numbers actually settle instead of bouncing.

> 🎯 Open one file. Hit START. Watch the needle climb.

---

## ✨ Features

### 🏁 The Speedometer
- **Lamborghini-inspired gauge** rendered in pure SVG.
- **Non-linear dial** (0 → 1000 Mbps) so slow connections still get full needle travel.
- Glowing, smoothly eased **animated needle**, sweeping color arc, and major/minor tick marks.
- A live **gear indicator (N → 8)** that shifts up as throughput rises — just like a tachometer.

### 🔬 Accurate Measurement Engine
- **Multi-stage testing** with **parallel streams (2 → 6)** to fully saturate the link.
- **Time-boxed sampling** so readings stabilize instead of spiking.
- Outlier-trimmed **ping** (14 samples, drop best + worst, take the minimum) and proper **jitter**.
- Blended final throughput (overall average + best-stage) for real-world accuracy.

### ⭐ Unique Extras
- **Bufferbloat detection** — pings *during* download saturation and reports the latency increase (Δ over idle), something most testers skip.
- **Connection Grade (A+ → F)** with a weighted 0–100 score.
- **Real-world capability badges** — instantly see if your line handles 4K streaming, competitive gaming, HD video calls, large uploads, and WFH/cloud.
- **Live throughput chart** (HTML Canvas) for download & upload streams.
- **Three drive modes** — *Strada* (blue), *Sport* (gold), *Corsa* (red) — that re-theme the whole UI.
- **Test history** — your last 20 results saved locally.
- **Exports** — copy a summary, download JSON, or generate a shareable **PNG result card**.
- Public IP, ISP / ASN, location, and the exact Cloudflare edge **colo** you tested against.
- Fully **responsive**, dark, carbon-fiber styled, and accessible.

---

## 🖼️ Preview

> _Add a screenshot or GIF here once you run it — e.g. `assets/preview.png`._
>
> ```markdown
> ![VELOCITÀ preview](assets/preview.png)
> ```

---

## 🚀 Getting Started

No installation. No dependencies. Just open the file.

```bash
# Clone
git clone https://github.com/<your-username>/velocita.git
cd velocita

# Option A — just double-click index.html

# Option B — serve locally (recommended)
python3 -m http.server 8080
# then open http://localhost:8080
```

> **Note:** The live test makes network requests to `speed.cloudflare.com` (CORS-enabled, no API key needed). It runs in any modern browser tab with an internet connection. Sandboxed environments that block network calls will render the UI but won't return live measurements.

---

## 🔬 How It Works

| Metric | Method |
|---|---|
| **Ping** | 14 tiny requests; drop the fastest + slowest; take the minimum (best-case RTT). |
| **Jitter** | Mean absolute difference between consecutive ping samples. |
| **Download** | 3 stages (1 MB → 25 MB) with 2 → 6 parallel streams, each time-boxed; final = blended overall + best-stage throughput. |
| **Upload** | 2 stages of parallel POSTs, time-boxed, blended throughput. |
| **Bufferbloat** | Latency probed continuously *during* download saturation; reported as Δ over idle ping. |
| **Grade** | Logarithmic weighting — download 45 / upload 20 / ping 20 / jitter 8 / bufferbloat 7. |

---

## 🛠️ Tech Stack

- **Pure HTML + CSS + vanilla JavaScript (ES2017)** — zero dependencies, ~38 KB total.
- **SVG** speedometer, **Canvas** live chart & result-card generator.
- **Cloudflare Speed** endpoints (`__down`, `__up`, `meta`) — CORS-enabled, key-free.
- `localStorage` for history and theme persistence.

---

## 📁 Project Structure

```
velocita/
├── index.html      # the entire app (markup + styles + engine)
├── README.md
└── assets/         # optional screenshots / icons
```

---

## 🗺️ Roadmap

- [ ] Multi-server selection & server-distance display
- [ ] Scheduled / auto-repeat tests
- [ ] Downloadable PDF report
- [ ] Light theme
- [ ] PWA / offline shell

Contributions and ideas welcome — open an issue or PR.

---

## 🤝 Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-thing`)
3. Commit your changes
4. Open a Pull Request

---

## 📄 License

Released under the **MIT License** — do whatever you like. See [`LICENSE`](LICENSE).

---

<div align="center">

**Built for speed. Styled like a supercar.** 🏎️💨

If you like it, drop a ⭐ — it helps a lot.

</div>
