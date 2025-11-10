# 🛒 Prototype Shopping List

> 📋 Part of [Prototype Roadmap](prototype-roadmap.md) – Phase 1

## 🎯 Purpose
Track recommended hardware, accessories, and tools needed for building and testing the **Private Cloud Camera System** prototype described in the [Prototype Roadmap](prototype-roadmap.md).

---

## 📷 Cameras

| Item | Model | Notes | Link | Status |
|------|--------|--------|------|--------|
| ✅ | **Reolink RLC-820A (8MP/4K PoE)** | Compact turret-style camera supporting RTSP + ONVIF. Ideal for Phase 1 prototyping (Track A & B). RLC-810A is an alternative, but RLC-820A is preferred due to smaller profile. | [Reolink Product Page](https://reolink.com/product/rlc-820a/) | ⏳ To be ordered |

---

## 💻 Edge Device

| Item | Model | Notes | Status |
|------|--------|--------|--------|
| ✅ | Raspberry Pi 4 (4GB or 8GB) | For Track B motion detection and local buffering tests. | ☐ Existing hardware |

---

## ⚙️ Accessories

| Item | Purpose | Notes | Status |
|------|----------|--------|--------|
| PoE Injector/Switch | Power & network for camera | Must support IEEE 802.3af | ☐ |
| Ethernet Cable (Cat6) | Reliable wired connection | Outdoor-rated if exposed | ☐ |
| MicroSD Card (128 GB+) | Edge recording buffer | For RPi or camera | ☐ |

---

## 📦 Cloud & Dev Tools

| Item | Purpose | Notes | Status |
|------|----------|--------|--------|
| AWS Account | Private cloud environment | For KVS, S3, Lambda, CDK stack | ✅ |
| CDK Project Repo | Infra automation | Mirrors `prototype-roadmap.md` | ✅ |
| Optional: OpenCV / FFmpeg | Local motion detection | Install via Pi or Mac | ☐ |

---

*Author: Ryan Pelavin*  
*Revision: v0.1 – Initial scaffold*