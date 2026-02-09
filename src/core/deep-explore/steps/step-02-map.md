# Step 02: Map (Divergent)

## Purpose

Now that we understand the space, map the options systematically.

**Time:** 15-30 min

**Inputs:** Knowledge Map, Research Summary

**Outputs:** Option Map (Morphological Box)

**Enforcement layers active:** ASSUMPTIONS_DECLARED, EVR, COUNTER-CHECKS, POST-PHASE CHECKLIST, GATE_02

---

## 02.0 ASSUMPTIONS_DECLARED (MANDATORY)

**Execute BEFORE any dimension discovery.**

```
ASSUMPTIONS_DECLARED for Phase 2:
┌──────┬──────────────────────────────────────┬──────────────┬────────────┬──────────────────────────────┐
│ ID   │ Assumption                           │ Type         │ Confidence │ Falsification Criterion      │
├──────┼──────────────────────────────────────┼──────────────┼────────────┼──────────────────────────────┤
│ H-2xx│ "[assumed completeness of dimensions]"│ INTERPRETIVE │ HIGH/MED/  │ "[dimension missing]"        │
│ H-2xx│ "[assumed independence of axes]"     │ DOMAIN       │ LOW        │ "[axes are coupled]"         │
│ H-2xx│ "[assumed constraint validity]"      │ CONTEXTUAL   │            │ "[constraint doesn't hold]"  │
└──────┴──────────────────────────────────────┴──────────────┴────────────┴──────────────────────────────┘
```

---

## 02.1 EXTRACT: Dimension Discovery

Load method: `data/method-procedures/M001_Dimension_Discovery.md`

A DIMENSION is an axis of choice — a category where you must pick one option.

```
RAW DIMENSION EXTRACTION:

DISCOVERY QUESTIONS:
• "What choices emerged from our research?"
• "What are the fundamental axes?"
• "What would an expert add?"

DIMENSIONS FOUND (raw, unvalidated):
1. [dimension name] - source: [where identified]
2. [dimension name] - source: [where identified]
3. [dimension name] - source: [where identified]
...

[EXTRACT_COMPLETE for dimensions]
```

## 02.2 EXTRACT: Option Enumeration

Load method: `data/method-procedures/M002_Option_Enumeration.md`

For each dimension, list ALL options:

```
DIMENSION: [name]
RAW OPTIONS:
├── Option A: [description] - source: [where from?]
├── Option B: [description] - source: [where from?]
├── Option C: [description] - source: [where from?]
└── [Missing options? Apply expansion prompts]

EXPANSION PROMPTS:
• "What would a contrarian choose?"
• "What's the unconventional choice?"
• "What if we combined options?"
• "What's the 'do nothing' option?"

[EXTRACT_COMPLETE for options]
```

## 02.3 EXTRACT: Constraint Mapping

Load method: `data/method-procedures/M003_Constraint_Mapping.md`

```
RAW CONSTRAINTS:
• [constraint 1] - type: HARD/SOFT - source: [evidence]
• [constraint 2] - type: HARD/SOFT - source: [evidence]

[EXTRACT_COMPLETE for constraints]
```

---

## 02.4 VERIFY: Validate Map Elements

```
VERIFICATION LOG:

DIMENSION VALIDATION:
┌────┬──────────────┬──────────────┬──────────┬─────────────────────────┐
│ #  │ Dimension    │ Type         │ Status   │ Notes                   │
├────┼──────────────┼──────────────┼──────────┼─────────────────────────┤
│ 1  │ [name]       │ INDEPENDENT  │ VERIFIED │ truly independent axis  │
│ 2  │ [name]       │ DEPENDENT    │ ASSUMED  │ may correlate with D1   │
└────┴──────────────┴──────────────┴──────────┴─────────────────────────┘

QUALITY CHECKS:
□ At least [3/4/5 per depth] dimensions?        [Y/N]
□ Each dimension has at least 2 options?         [Y/N]
□ Dimensions are truly independent?              [Y/N]
□ No obvious dimension missing?                  [Y/N]

CONSTRAINT VALIDATION:
┌────┬──────────────────────────────┬──────────┬───────────────┐
│ #  │ Constraint                   │ Status   │ Confidence    │
├────┼──────────────────────────────┼──────────┼───────────────┤
│ 1  │ [D1:A + D2:B impossible]     │ VERIFIED │ HIGH          │
│ 2  │ [D1:C + D3:A difficult]      │ ASSUMED  │ MED           │
└────┴──────────────────────────────┴──────────┴───────────────┘

[VERIFY_COMPLETE]
```

**★ KEY_CLAIM: "The morphological box captures the complete decision space."**

**COUNTER-CHECKS (minimum per depth: quick=1, standard=2, deep=3):**
```
COUNTER-CHECK #N:
  claim: "The morphological box is complete — no major dimension is missing"
  disproof: "An expert or user would immediately identify a missing axis"
  search_attempt: "[consider: timing, funding, team, technology, market, legal, etc.]"
  result: CONFIRMED | WEAKENED | REFUTED
  action: [if WEAKENED: add missing dimension, re-verify]
```

---

## 02.5 RENDER: Build Morphological Box

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                         MORPHOLOGICAL BOX                                  ║
╠═══════════════════════════════════════════════════════════════════════════╣
║                                                                            ║
║  DIMENSION 1: [Name] — status: [VERIFIED/ASSUMED]                         ║
║  ├── Option A: [description]                                               ║
║  ├── Option B: [description]                                               ║
║  └── Option C: [description]                                               ║
║                                                                            ║
║  DIMENSION 2: [Name] — status: [VERIFIED/ASSUMED]                         ║
║  ├── Option A: [description]                                               ║
║  └── Option B: [description]                                               ║
║                                                                            ║
║  CONSTRAINTS:                                                              ║
║  • [constraint 1] - confidence: [level] - status: [VERIFIED/ASSUMED]      ║
║                                                                            ║
║  VALID COMBINATIONS: [N] of [total]                                        ║
║                                                                            ║
╚═══════════════════════════════════════════════════════════════════════════╝

[RENDER_COMPLETE]
```

---

## POST-PHASE CHECKLIST (MANDATORY)

```
PHASE_02 COMPLETION CHECKLIST:

□ ASSUMPTIONS_DECLARED logged?             [count: ___]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ Dimensions discovered?                   [count: ___ (min: ___)]
□ Options enumerated?                      [count: ___ (min: ___)]
□ Each dimension verified for independence?[Y/N]
□ Constraints mapped?                      [Y/N]
□ Constraints tagged VERIFIED/ASSUMED?     [Y/N]
□ Morphological box rendered?              [Y/N]
□ Counter-checks performed?               [count: ___ (min: ___)]
□ Expansion prompts applied?              [Y/N]

CHECKLIST_STATUS: PASS | FAIL
IF FAIL: Fix before proceeding.
```

---

## GATE_02: MAP EXIT

```
GATE_02 BINDING CHECK:

□ Dimensions discovered (min per depth)     — [PASS/FAIL] — CRITICAL
□ Options enumerated (min per depth)        — [PASS/FAIL] — CRITICAL
□ Constraints mapped                        — [PASS/FAIL] — REQUIRED
□ Morphological box built                   — [PASS/FAIL] — CRITICAL
□ Counter-checks performed                  — [PASS/FAIL] — REQUIRED
□ Post-phase checklist PASSED               — [PASS/FAIL] — CRITICAL

GATE_02 STATUS: OPEN | LOCKED
```

---

## Feedback Loop Check

```
□ Did mapping reveal new unknowns?
  → YES: Return to Step 1 (if iterations remaining)

□ Did mapping reveal we misunderstood the problem?
  → YES: Return to Step 0

□ Is the map suspiciously simple?
  → YES: Challenge — are we missing dimensions?

□ Are ALL options unacceptable?
  → YES: Consider ABORT — no viable decision exists
```

## Iteration Tracking

```
LOOP COUNT: Step 1 ↔ Step 2 iterations: [N]

□ If looping more than [quick:1 / standard:3 / deep:5] times:
  → STOP: Either proceed with current map or ABORT
```

---

## Transition

- **If GATE_02 = OPEN and map is complete** → Proceed to Step 3
- **If knowledge gaps found AND iterations remaining** → Return to Step 1
- **If knowledge gaps found BUT max loops reached** → Proceed with gaps flagged
- **If framing wrong** → Return to Step 0
- **If no viable options exist** → Consider ABORT
