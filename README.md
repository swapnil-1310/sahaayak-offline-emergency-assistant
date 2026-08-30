# 🚨 Sahaayak
## Offline AI Emergency Guidance Assistant

> A voice-first, offline emergency guidance assistant designed for situations where medical emergencies occur in areas with little or no internet connectivity.

---

## 🌍 The Problem

Medical emergencies can occur in remote highways, rural areas, trekking routes, forests, and other locations with poor or zero cellular connectivity.

When an accident happens in such locations, bystanders may not be able to access search engines, online AI assistants, emergency information, or digital health platforms. This can lead to confusion and delayed decision-making during the first few critical minutes.

Most intelligent health assistants depend on cloud connectivity. Our goal is to explore a smartphone-based system that can continue operating even when the internet is unavailable.

---

## 💡 Our Solution

**Sahaayak** is a voice-first emergency guidance assistant designed to process the core emergency workflow locally on a smartphone.

A bystander describes what happened using natural language. The application converts the voice input into text, analyzes the emergency context using an on-device AI model, extracts important information, and passes it to a deterministic emergency protocol engine.

The protocol engine then determines the next relevant question or guidance step.

```text
User Voice
    ↓
Offline Speech-to-Text
    ↓
Local AI Understanding
    ↓
Structured Emergency Information
    ↓
Emergency Protocol Engine
    ↓
Visual + Voice Guidance
```

The core workflow is designed to function without requiring an internet connection.

---

## 🎯 Key Features

- 📵 Designed for offline operation
- 🎤 Voice-first emergency interaction
- 🧠 Local AI-based natural language understanding
- 📱 Smartphone-first workflow
- 🧩 Structured emergency information extraction
- 🚨 Deterministic emergency protocol engine
- 🔊 Voice guidance
- 📋 Visual step-by-step instructions
- 🕒 Local emergency timeline
- 🖥️ Exploration of iQOO Office Kit for cross-device interaction

---

## 🧠 How the AI Works

The AI model is not intended to freely generate unrestricted medical advice.

Instead, Sahaayak separates **language understanding** from **emergency decision-making**.

```text
Natural Language
      ↓
Local AI Model
      ↓
Structured Emergency State
      ↓
Protocol Engine
      ↓
Controlled Next-Step Guidance
```

### Example

The user says:

> "My friend fell while trekking. He is not responding, but he is breathing."

The AI may extract:

```json
{
  "incident": "fall",
  "conscious": false,
  "breathing": true,
  "major_bleeding": "unknown"
}
```

The protocol engine then uses this structured information to determine the next relevant question or guidance step.

This approach keeps the AI responsible for understanding natural language while keeping emergency decision flow controlled and predictable.

---

## 🏗️ Proposed Architecture

```text
                    USER
                      │
                      ▼
                 🎤 Voice Input
                      │
                      ▼
            Offline Speech Recognition
                      │
                      ▼
               Emergency Description
                      │
                      ▼
          ┌───────────────────────────┐
          │   Local AI Model (Target) │
          │                           │
          │ Understands user input    │
          │ Extracts emergency data   │
          └─────────────┬─────────────┘
                        │
                        ▼
             Structured Emergency State
                        │
                        ▼
                Protocol Engine
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
        📱 Visual Guidance    🔊 Voice Guidance
              │
              ▼
        Emergency Timeline
```

Detailed architecture: [`docs/architecture.md`](docs/architecture.md)

---

## 🚨 Initial Emergency Scenarios

The first prototype will focus on a limited number of scenarios.

### 1. Unresponsive Person

The system gathers information about:

- Responsiveness
- Breathing status
- Immediate danger

### 2. Severe Bleeding

The system identifies:

- Presence of bleeding
- Whether bleeding appears severe
- Relevant next assessment step

### 3. Fall / Trauma

The system gathers information about:

- Consciousness
- Breathing
- Major bleeding
- Possible injury context

### 4. Snake Bite

This scenario will be included if implementation time permits.

Detailed emergency flow design: [`docs/emergency-protocol.md`](docs/emergency-protocol.md)

---

## 🧰 Proposed Tech Stack

| Component | Proposed Technology |
|---|---|
| Mobile Application | Native Android |
| Programming Language | Kotlin |
| User Interface | Jetpack Compose |
| Speech Input | Offline Speech-to-Text |
| AI | Quantized Open-Source Local Model |
| AI Role | Emergency Context Understanding |
| Emergency Logic | Kotlin Protocol / State Machine |
| Voice Output | On-device Text-to-Speech |
| Local Storage | JSON / Room |
| Target Device | iQOO Smartphone |
| AI Hardware Target | Snapdragon On-Device AI / NPU |
| Cross-Device Integration | iQOO Office Kit |

The final model and inference runtime will be selected based on compatibility and performance testing on the hackathon device.

Detailed stack: [`docs/tech-stack.md`](docs/tech-stack.md)

---

## 📱 Offline-First Design

The proposed core workflow is:

```text
No Internet
     +
User Voice
     ↓
Offline Processing
     ↓
Emergency Assessment
     ↓
Protocol Selection
     ↓
Guidance
```

The application should not depend on a cloud API for its primary emergency workflow.

---

## 🖥️ iQOO Office Kit Usage

iQOO Office Kit will be explored for:

- Screen mirroring during phone-first development
- Remote control using laptop keyboard and trackpad
- File transfer
- Shared clipboard
- Cross-device visualization of emergency information

The core emergency experience remains phone-first.

---

## 🎬 Planned Demo

The final demo will demonstrate the complete offline workflow:

```text
1. Show the iQOO phone
2. Enable Airplane Mode
3. Open Sahaayak
4. Describe an emergency using voice
5. Convert speech locally
6. Process the emergency description locally
7. Extract critical emergency information
8. Ask follow-up questions
9. Enter the relevant emergency protocol
10. Provide visual and voice guidance
11. Display the emergency timeline
```

Detailed demo plan: [`docs/demo-plan.md`](docs/demo-plan.md)

---

## 🚀 Hackathon Execution Plan

### Phase 1 — Foundation
Build the Android application skeleton, UI, navigation, and emergency protocol engine.

### Phase 2 — Functional MVP
Create a complete emergency flow using manual input and deterministic protocol logic.

### Phase 3 — Voice
Integrate microphone input, speech-to-text, and voice output.

### Phase 4 — Local AI
Integrate a compatible on-device model and convert natural language into structured emergency information.

### Phase 5 — Optimization and Demo
Test offline functionality, optimize performance on the iQOO device, use Office Kit where relevant, and prepare the final demonstration.

Detailed plan: [`docs/execution-plan.md`](docs/execution-plan.md)

---

## 👥 Team

| Area | Responsibility |
|---|---|
| Mobile Development | Android application and user interface |
| AI & Voice | Local model, inference, and speech processing |
| Protocol & Integration | Emergency flows, decision engine, testing, and integration |

---

## ⚠️ Disclaimer

Sahaayak is a hackathon prototype created to explore offline emergency guidance technology.

It is not a replacement for professional medical care, trained emergency responders, or official emergency services.

Emergency services should be contacted whenever connectivity becomes available.

---

## 📌 Repository Status

This repository currently contains the proposed system architecture, technical strategy, emergency protocol design, and execution plan.

The working application will be developed during the hackathon.
