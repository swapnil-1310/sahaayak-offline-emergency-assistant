# Offline AI Strategy

## Objective

The objective is to process emergency descriptions locally on the smartphone without requiring a cloud-based AI API.

The proposed system will evaluate a quantized open-source language model that can run on the available iQOO hardware.

The target model class is approximately 4B–5B parameters, subject to compatibility, memory usage, and inference performance.

---

# Role of the Local Model

The local model will be responsible for:

- Understanding natural language
- Identifying the emergency context
- Extracting important information
- Identifying missing information
- Maintaining short conversational context
- Producing structured emergency data

The model will not be used as an unrestricted emergency advice generator.

---

# Input Example

The user says:

> "My friend slipped while climbing. He is lying on the ground and is not responding properly."

The model receives this as text after speech recognition.

---

# Expected Output

The model should attempt to convert the description into structured information.

Example:

```json
{
  "incident": "fall",
  "conscious": false,
  "breathing": "unknown",
  "major_bleeding": "unknown",
  "environment": "remote trekking area"
}
```

---

# Why Structured Output?

Natural language can be ambiguous.

The rest of the application should not need to repeatedly interpret the user's original sentence.

Therefore:

```text
User Description
       ↓
Local AI
       ↓
Structured Emergency Data
       ↓
Protocol Engine
       ↓
Next Question / Guidance
```

The protocol engine operates using the structured emergency state.

---

# Model Selection Criteria

The final model will be evaluated based on:

- Android compatibility
- On-device inference support
- Snapdragon acceleration compatibility
- Memory requirements
- Inference latency
- Quantization support
- Structured output reliability
- Offline operation
- Integration complexity

---

# Primary Strategy

The preferred approach is:

```text
Quantized Local Model
        ↓
On-device Inference Runtime
        ↓
Structured JSON Output
```

The model is expected to process emergency context locally.

---

# Fallback Strategy

Hackathon development requires a working fallback.

If the primary 4B–5B model cannot be integrated within the available time, the system can fall back to:

```text
Smaller Local Model
        ↓
Structured Extraction
        +
Protocol Engine
```

If required, a limited rule-based extraction layer can also support the predefined emergency scenarios.

The goal is to maintain a functional end-to-end emergency workflow even if advanced AI optimization is incomplete.

---

# Final Principle

```text
Local AI
=
Language Understanding

Protocol Engine
=
Emergency Flow Control
```

This allows the project to combine flexible natural-language interaction with controlled application logic.