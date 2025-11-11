# Private Cloud Camera System – Prototype Roadmap

## 🎯 Overview
Goal: Build a **privacy-first, event-driven camera system** that stores and analyzes video in a **private AWS account** — not a third-party cloud.  
Prototype now, with the long-term intent to **commercialize** a low-cost, transparent, self-owned alternative to Ring/Nest.

---

## 🧩 Phase 1: Dual-Track Prototype (0–3 Months)

> 📋 See [Prototype Shopping List](prototype-shopping-list.md) for hardware and tools needed for this phase.

### Track A — Cloud-Only Baseline
- **Pipeline:** RTSP → Kinesis Video Streams → S3 → Lambda (event tagging)
- **Objectives:**
  - Prove ingestion, playback, and AI tagging (Rekognition or OpenCV).
  - Measure AWS cost per camera-hour.
  - Establish latency and reliability metrics.
- **Deliverables:**
  - CDK stack (camera ingest → storage → event detection)
  - Basic Next.js/Flutter dashboard for playback and events
  - Cost breakdown per component

### Track B — Edge-Assisted Prototype
- **Hardware:** Raspberry Pi 4 (or equivalent)
- **Pipeline:** Local motion detection → upload short clips → S3
- **Objectives:**
  - Reduce cloud ingestion and storage costs.
  - Handle network dropouts with local buffering.
  - Compare CPU, bandwidth, and event quality.
- **Deliverables:**
  - Motion-triggered upload script (Python or Node)
  - Presigned S3 URL upload
  - Logging for motion frequency and clip size

### Metrics to Capture
| Metric | Description |
|--------|--------------|
| AWS cost per camera | Total monthly estimate |
| Avg clip size & frequency | Event-driven bandwidth impact |
| Latency to first event | Motion-to-alert speed |
| Uptime & reliability | Missed events, reconnects |
| CPU load (edge) | Pi performance baseline |

---

## 🧠 Phase 2: Alpha (3–6 Months)
- Simplify setup (one-command CDK deploy).
- Add alerts (Telegram, email).
- Support multiple cameras.
- Test with friends/family in their own AWS accounts.
- **Edge Hardware Track (Optional): High-Performance Edge AI Node**
  - Introduce an edge AI device (e.g., **NVIDIA Jetson Orin Nano / Orin Nano Super**, **Google Coral Dev Board** + USB Accelerator, or similar) to run on-device inference and smart event filtering.
  - **Objectives:**
    - Run person/vehicle detection locally (e.g., YOLO/TensorRT or TFLite) across one or more RTSP streams.
    - Compare Pi-based edge pipeline vs. edge-AI node for **latency**, **upload volume**, and **missed-event rate**.
    - Measure **power draw** and **thermals**; validate enclosure/cooling requirements.
  - **Deliverables:**
    - Containerized edge service (Docker) for inference + local buffering + AWS publishing (MQTT/SNS/S3 presigned uploads).
    - Metrics dashboard (Grafana/CloudWatch) tracking inference latency, clip frequency, and bandwidth saved.
    - Report: **edge vs. cloud cost per camera-hour** and recommendation for Phase 3 hardware kit.
- Gather cost, reliability, and feedback data.

---

## 💵 Phase 3: Paid Beta (6–12 Months)
- Offer “Managed Private Cloud” deployments in your AWS.
- Add Cognito sign-in + simple billing (Stripe).
- Focus on **privacy, ownership, and cost transparency** as core differentiators.

---

## 🚀 Long-Term Goal
Evolve into a **commercial solution** for privacy-conscious homes and small businesses:
- Event-driven, cloud-native camera platform.
- Optional AI-based event summaries (Rekognition / Bedrock).
- Self-hosted or managed models.
- Hardware kits for plug-and-play edge ingestion.
- Potential future flexibility: deploy on **AWS, Azure, or GCP**.

---

## ✅ Success Criteria
- Reliable prototype running in your home.
- Cost < $5/month per camera (with edge assist).
- Usable dashboard and motion tagging accuracy >90%.
- Positive early feedback from external testers.

---

*Author: Ryan Pelavin*  
*Revision: v0.2 – Prototype Roadmap*