# System Architecture

## Overview

Sahaayak is designed as a layered offline emergency assistance system.

Each layer has a specific responsibility. This separation makes the system easier to develop, test, and improve during the hackathon.

```text
USER
 │
 ▼
Voice Input
 │
 ▼
Offline Speech-to-Text
 │
 ▼
Emergency Description
 │
 ▼
Local AI Understanding
 │
 ▼
Structured Emergency State
 │
 ▼
Emergency Protocol Engine
 │
 ├─────────────────┐
 ▼                 ▼
Visual Guidance   Voice Guidance
 │                 │
 └────────┬────────┘
          ▼
   Emergency Timeline
```

---

# 1. Voice Input Layer

The user interacts with Sahaayak primarily through the smartphone microphone.

Example:

> "My friend fell while trekking and he is not responding."

The application captures the voice input directly on the phone.

The user interface will also include a text input fallback.

---

# 2. Offline Speech Recognition Layer

The speech recognition layer converts the user's voice into text.

```text
Audio Input
     ↓
Offline Speech Recognition
     ↓
Text
```

The target requirement is that the speech recognition component should work without depending on an active internet connection.

---

# 3. Local AI Understanding Layer

The local AI model processes the emergency description.

Its responsibilities include:

- Understanding natural language
- Identifying the possible emergency type
- Extracting important context
- Identifying missing information
- Producing structured output

Example input:

> "My friend slipped while climbing. He is lying on the ground and is not responding."

Example structured interpretation:

```text
Incident: Fall
Conscious: No
Breathing: Unknown
Bleeding: Unknown
Environment: Remote trekking area
```

The AI is not responsible for freely generating emergency treatment instructions.

---

# 4. Structured Emergency State

The extracted information is stored as structured data.

Example:

```json
{
  "incident": "fall",
  "conscious": false,
  "breathing": "unknown",
  "major_bleeding": "unknown",
  "environment": "remote"
}
```

Using structured data allows the emergency decision system to work independently from the raw user conversation.

---

# 5. Emergency Protocol Engine

The protocol engine is responsible for controlling the emergency flow.

It determines:

- Which question should be asked next
- Which emergency state is active
- Which guidance should be displayed
- When the flow should move to another protocol

Example:

```text
IF person is unresponsive
        ↓
Check breathing
        ↓
IF breathing is confirmed
        ↓
Continue appropriate protocol
```

This layer is deterministic and does not depend on the AI generating new instructions.

---

# 6. Visual Guidance Layer

The application displays one clear action at a time.

The interface will prioritize:

- Large text
- High readability
- Clear question prompts
- Minimal interaction complexity
- High contrast emergency UI

---

# 7. Voice Guidance Layer

The same guidance displayed on the screen can also be spoken through the phone speaker.

This enables a more hands-free interaction model.

```text
Protocol Engine
       ↓
Instruction
       ↓
Text-to-Speech
       ↓
Phone Speaker
```

---

# 8. Emergency Timeline

Important events can be stored locally.

Example:

```text
12:04 — Emergency session started
12:05 — Fall detected
12:06 — Person reported unresponsive
12:07 — Breathing status confirmed
12:08 — Guidance flow started
```

The timeline can potentially be used to provide a quick summary when professional help becomes available.

---

# Design Principle

The core principle behind the architecture is:

```text
AI = Understand the user

Protocol Engine = Control the emergency flow

Voice/UI = Deliver the guidance
```

This separation reduces dependence on unrestricted AI output while allowing flexible natural-language interaction.ss