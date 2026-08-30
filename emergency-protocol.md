# Emergency Protocol Strategy

## Objective

Sahaayak is designed to use structured emergency flows.

The local AI understands what the user is describing, while the protocol engine controls the sequence of questions and guidance.

```text
User Input
    ↓
AI Understanding
    ↓
Emergency State
    ↓
Protocol Selection
    ↓
Next Question / Guidance
```

---

# Scenario 1 — Unresponsive Person

Initial flow:

```text
Person appears unresponsive
          │
          ▼
Check responsiveness
          │
          ▼
Check breathing status
          │
     ┌────┴────┐
     │         │
Breathing   Not Confirmed
     │         │
     ▼         ▼
Continue    Continue
appropriate assessment
flow
```

Information collected:

- Is the person responding?
- Is the person breathing?
- Is there immediate danger?
- Is professional help available?

---

# Scenario 2 — Severe Bleeding

Initial flow:

```text
Bleeding Reported
       │
       ▼
Assess Severity
       │
       ▼
Determine Whether Bleeding Is Continuing
       │
       ▼
Enter Relevant Guidance Flow
       │
       ▼
Monitor Situation
```

Information collected:

- Location of bleeding
- Severity
- Whether bleeding is continuing
- Whether the person is conscious

---

# Scenario 3 — Fall / Trauma

Initial flow:

```text
Fall Reported
      │
      ▼
Check Responsiveness
      │
      ▼
Check Breathing
      │
      ▼
Check Major Bleeding
      │
      ▼
Continue Relevant Trauma Assessment
```

Information collected:

- Was there a fall or impact?
- Is the person responsive?
- Is the person breathing?
- Is major bleeding present?
- Is the environment safe?

---

# Scenario 4 — Snake Bite

Optional flow:

```text
Possible Snake Bite
       │
       ▼
Confirm Possible Bite
       │
       ▼
Assess Symptoms
       │
       ▼
Collect Time of Incident
       │
       ▼
Enter Snake Bite Guidance Flow
```

This scenario will be implemented only if sufficient hackathon time is available.

---

# Protocol State Model

Each emergency scenario can be represented as a state machine.

Example:

```text
STATE: FALL_DETECTED

Question:
"Is the person responding?"

Possible Responses:
YES
NO
UNKNOWN
```

The selected response determines the next state.

Example:

```text
FALL_DETECTED
       ↓
ASK_RESPONSIVENESS
       ↓
UNRESPONSIVE
       ↓
ASK_BREATHING
       ↓
NEXT_PROTOCOL_STATE
```

---

# Core Design Principle

```text
AI
│
└── Understands the user's language

Protocol Engine
│
└── Controls the emergency flow
```

The application should avoid allowing the language model to independently decide the complete emergency procedure.