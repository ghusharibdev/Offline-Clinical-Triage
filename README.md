# Offline Clinical Triage Agent

An offline-first mobile application that provides structured clinical triage for community health workers in regions with no internet connectivity.

**Track:** AI in Healthcare  
**Team:** Ghusharib Najam & Meesum Zaheer

---

## Problem

Over 2.3 billion people worldwide lack access to basic healthcare. In many rural and remote regions, there is only 1 doctor per 5,000 people. Community health workers — often non-medical volunteers — must make life-saving triage decisions without internet, without a doctor, and without decision-support tools.

Existing AI triage solutions rely on cloud connectivity, which is unavailable in exactly the places that need them most.

---

## Solution

An on-device AI agent that runs entirely on a mid-range Android phone — **no internet connection required**. Health workers input symptoms via text, voice, or image, and receive a structured triage output with a suspected condition, red flags, confidence score, and an auto-generated referral note.

---

## Key Features

- Fully offline triage engine — on-device inference, no cloud calls
- Multimodal input: text, voice, image
- Structured JSON output: triage level (RED / ORANGE / YELLOW / GREEN), suspected conditions, red flags, recommended action, confidence score, referral note
- Deterministic safety net: schema enforcement, confidence threshold, rule-based validation against WHO ETAT / SATS 2023
- Local patient record storage with optional sync when connectivity returns
- Voice-first UX designed for low-literacy users
- Auto-generated referral notes

---

## Architecture

```
User Input (text / voice / image)
        |
        v
Input Handler
        |
        v
On-Device Model (quantized LLM)
        |
        v
Deterministic Safety Net (schema + confidence + rules)
        |
        v
Output Renderer  -->  Local Storage  -->  Optional Sync
```

Full details in [architecture.md](architecture.md).

---

## Repository Contents

| File | Description |
|------|-------------|
| `README.md` | Project overview |
| `architecture.md` | System architecture and components |
| `output-schema.json` | Structured triage output schema |

---

## Status

Proposal stage — MVP in development.

---

## License

MIT
