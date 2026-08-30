# Hackathon Execution Plan

## Goal

Build a working offline emergency guidance prototype on the iQOO device within the hackathon timeframe.

The development strategy prioritizes a complete working pipeline before advanced optimization.

---

# Phase 1 — Application Foundation

Tasks:

- Create Android project
- Configure Kotlin
- Configure Jetpack Compose
- Build Home Screen
- Build Emergency Assessment Screen
- Build Guidance Screen
- Implement navigation

Success criteria:

The application runs successfully on the iQOO device.

---

# Phase 2 — Functional Emergency MVP

Tasks:

- Create emergency state data model
- Implement protocol engine
- Add fall/trauma scenario
- Add unresponsive person scenario
- Add severe bleeding scenario
- Connect protocol engine to UI

Success criteria:

A complete emergency flow works using manual text or button input.

---

# Phase 3 — Voice Interaction

Tasks:

- Add microphone permission
- Add microphone interface
- Integrate speech-to-text
- Keep text input fallback
- Integrate text-to-speech output

Success criteria:

The user can interact with the application using voice.

---

# Phase 4 — Local AI Integration

Tasks:

- Evaluate compatible local model
- Select inference runtime
- Integrate local inference
- Generate structured emergency information
- Connect AI output to protocol engine

Success criteria:

Natural-language emergency descriptions are converted into structured emergency data locally.

---

# Phase 5 — Device Testing and Optimization

Tasks:

- Test Airplane Mode
- Test microphone
- Test speech recognition
- Test local AI inference
- Test voice output
- Measure response time
- Test memory usage
- Explore available hardware acceleration

Success criteria:

The core workflow runs on the target iQOO device without requiring internet connectivity.

---

# Phase 6 — Office Kit Integration

Tasks:

- Demonstrate phone-first workflow
- Use screen mirroring where useful
- Test remote control workflow
- Explore emergency information visualization on another screen

Success criteria:

Office Kit is meaningfully integrated into the overall project demonstration.

---

# Phase 7 — Final Submission

Tasks:

- Complete end-to-end testing
- Prepare stable demo scenario
- Record demonstration video
- Update GitHub repository
- Prepare final presentation

---

# Development Priority

The project priority is:

```text
1. Working Protocol Flow
        ↓
2. App Running on Phone
        ↓
3. Voice Input and Output
        ↓
4. Offline Processing
        ↓
5. Local AI
        ↓
6. Device Optimization
        ↓
7. UI Polish
```

At every stage, the goal is to keep a working end-to-end prototype.

Advanced features should not break the existing working emergency flow.