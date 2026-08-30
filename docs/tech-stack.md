# Proposed Technology Stack

## 1. Mobile Application

### Native Android

The core application will be developed as a native Android application.

The primary reason is direct access to:

- Microphone
- Audio output
- Local storage
- Android AI runtimes
- Device hardware capabilities

---

## 2. Programming Language

### Kotlin

Kotlin will be used for the Android application logic.

Responsibilities include:

- Application logic
- Navigation
- Emergency state management
- Protocol engine
- Device integration

---

## 3. User Interface

### Jetpack Compose

Jetpack Compose will be used for the application interface.

The emergency UI will prioritize:

- Large readable text
- Clear buttons
- Minimal interaction complexity
- Step-by-step guidance

---

## 4. Speech Input

An offline speech-to-text solution will convert the user's voice into text.

Requirements:

- Offline functionality
- Android compatibility
- Low latency
- Practical accuracy
- Local processing

A text input fallback will remain available.

---

## 5. Local AI

A quantized open-source language model will be evaluated for local inference.

Target role:

```text
Natural Language
      ↓
Emergency Context Understanding
      ↓
Structured Emergency Data
```

Target model size:

Approximately 4B–5B parameters, subject to device testing.

---

## 6. Inference Runtime

The final inference runtime will be selected based on:

- Android compatibility
- Model compatibility
- Local performance
- Snapdragon acceleration support
- Integration complexity

The project will prioritize a reliable implementation over an unnecessarily large model.

---

## 7. Emergency Protocol Engine

A Kotlin-based deterministic state machine will control the emergency flow.

Responsibilities:

- Maintain emergency state
- Ask relevant questions
- Select the next flow
- Trigger guidance
- Record important events

---

## 8. Voice Output

On-device text-to-speech will provide spoken guidance.

```text
Protocol Engine
       ↓
Guidance Text
       ↓
Text-to-Speech
       ↓
Phone Speaker
```

---

## 9. Local Storage

Local storage options include:

- JSON files for protocol data
- Room database for emergency timeline and session data

---

## 10. Target Hardware

The target device is the iQOO smartphone provided during the hackathon.

The project will explore available Snapdragon on-device AI acceleration where compatible with the selected model and runtime.

---

## 11. Cross-Device Workflow

iQOO Office Kit will be explored for:

- Screen mirroring
- Remote control
- Shared clipboard
- File transfer
- Emergency information visualization

The core emergency workflow remains phone-first and offline.
