# Step 01: Research

## Purpose

Fill critical knowledge gaps identified in Step 0 BEFORE mapping options.

**Time:** 15-30 min (Quick), 1-2 hours (Standard)

**Inputs:** Research Queue from Step 0, Knowledge Map

**Outputs:** Research Summary, Updated Knowledge Map

**Enforcement layers active:** ASSUMPTIONS_DECLARED, EVR, COUNTER-CHECKS, POST-PHASE CHECKLIST, GATE_01

---

## 01.0 ASSUMPTIONS_DECLARED (MANDATORY)

**Execute BEFORE any research begins.**

```
ASSUMPTIONS_DECLARED for Phase 1:
┌──────┬──────────────────────────────────────┬──────────────┬────────────┬──────────────────────────────┐
│ ID   │ Assumption                           │ Type         │ Confidence │ Falsification Criterion      │
├──────┼──────────────────────────────────────┼──────────────┼────────────┼──────────────────────────────┤
│ H-1xx│ "[assumed source reliability]"       │ CONTEXTUAL   │ HIGH/MED/  │ "[source found unreliable]"  │
│ H-1xx│ "[assumed domain state]"             │ DOMAIN       │ LOW        │ "[domain changed]"           │
│ H-1xx│ "[interpretive choice about scope]"  │ INTERPRETIVE │            │ "[scope is different]"       │
└──────┴──────────────────────────────────────┴──────────────┴────────────┴──────────────────────────────┘
```

---

## 01.1 EXTRACT: Execute Research Queue

Load: `data/research-methods.md`

**For each item in Research Queue by priority — gather raw data FIRST:**

```
RESEARCH ITEM: [question]
PRIORITY: [P1/P2/P3]
METHOD: [web search / docs / experiment / ask expert]

RAW FINDINGS (uninterpreted):
• [raw finding 1] - source: [url/reference]
• [raw finding 2] - source: [url/reference]
• [raw finding 3] - source: [url/reference]

NEW RAW QUESTIONS DISCOVERED: [list any]

[EXTRACT_COMPLETE for item N]
```

**ENFORCEMENT:** Do NOT interpret findings yet. Do NOT assign confidence. Raw data only.

**Depth adjustment for extraction scope:**
- quick: Extract top 2-3 items only
- standard: Extract all P1 and P2 items
- deep: Extract all items + exploratory research

---

## 01.2 VERIFY: Validate Research Findings

**For each extracted finding, verify against evidence:**

```
VERIFICATION LOG:

ITEM: [question]
┌────┬──────────────────────────┬───────────────┬──────────┬────────────────────┐
│ #  │ Finding                  │ Source        │ Status   │ Confidence         │
├────┼──────────────────────────┼───────────────┼──────────┼────────────────────┤
│ 1  │ [finding]                │ [url/ref]     │ VERIFIED │ HIGH               │
│ 2  │ [finding]                │ [url/ref]     │ ASSUMED  │ MED — reason: ___  │
│ 3  │ [finding]                │ [conflicting] │ CONTRA-  │ LOW — conflict: ___|
│    │                          │               │ DICTED   │                    │
└────┴──────────────────────────┴───────────────┴──────────┴────────────────────┘

CLEAR ANSWER:
→ Move to KNOWN FACTS with source — status: VERIFIED

PARTIAL ANSWER:
→ Record, mark confidence, decide: research more or accept partial?

CONFLICTING INFO:
→ Record ALL positions, note conflict, assess source reliability

NO INFO FOUND:
→ Mark as TRUE UNKNOWN, assess: can we proceed without?

NEW QUESTIONS:
→ Assess priority, add to queue if HIGH, park if LOW

[VERIFY_COMPLETE]
```

**★ KEY_CLAIM for each HIGH-confidence finding.**

**COUNTER-CHECKS (minimum per depth: quick=1, standard=2, deep=3):**
```
COUNTER-CHECK #N:
  claim: "[research finding stated as fact]"
  disproof: "[what evidence would show this is wrong]"
  search_attempt: "[what was tried]"
  result: CONFIRMED | WEAKENED | REFUTED
  action: [none | reduce confidence | investigate further]
```

---

## 01.3 RENDER: Update Knowledge Map

**Only after verification is complete — produce formatted output:**

```
KNOWLEDGE MAP UPDATE:

MOVE TO KNOWN FACTS:
+ [finding] - source: [reference] - status: VERIFIED

UPDATE ASSUMPTIONS:
~ [assumption] - confidence now: [new level] - reason: [H-ID updated]

REMOVE FROM UNKNOWNS:
- [question] - answered by: [reference]

ADD TO UNKNOWNS:
+ [new question] - priority: [P1-P4]

[RENDER_COMPLETE]
```

---

## POST-PHASE CHECKLIST (MANDATORY)

```
PHASE_01 COMPLETION CHECKLIST:

□ ASSUMPTIONS_DECLARED logged?             [count: ___]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ Research items executed?                 [count: ___ of ___ planned]
  - P1 items completed: [count]
  - P2 items completed: [count]
□ Findings verified with sources?          [Y/N]
□ Each finding tagged VERIFIED/ASSUMED?    [Y/N]
□ Counter-checks performed?               [count: ___ (min: ___)]
□ Knowledge map updated?                  [Y/N]
□ New questions added to queue?           [count: ___]

CHECKLIST_STATUS: PASS | FAIL
IF FAIL: Fix before proceeding.
```

---

## GATE_01: RESEARCH EXIT

```
GATE_01 BINDING CHECK:

□ Research queue executed by priority       — [PASS/FAIL] — CRITICAL
□ Findings recorded with sources            — [PASS/FAIL] — CRITICAL
□ Knowledge map updated                     — [PASS/FAIL] — REQUIRED
□ Counter-checks on key findings            — [PASS/FAIL] — REQUIRED
  (min: quick=1, standard=2, deep=3)
□ Post-phase checklist PASSED               — [PASS/FAIL] — CRITICAL

GATE_01 STATUS: OPEN | LOCKED
```

---

## Output: Research Summary

```
╔═══════════════════════════════════════════════════════════════╗
║  RESEARCH SUMMARY                                              ║
╠═══════════════════════════════════════════════════════════════╣
║                                                                ║
║  Items Researched:      [count]                                ║
║                                                                ║
║  KEY LEARNINGS:                                                 ║
║  • [learning 1] - impact: ___ - status: VERIFIED/ASSUMED       ║
║  • [learning 2] - impact: ___ - status: VERIFIED/ASSUMED       ║
║                                                                ║
║  Verified (HIGH confidence):    [count]                        ║
║  Partial (MED confidence):      [count]                        ║
║  Unknown (cannot determine):    [count]                        ║
║                                                                ║
║  New Questions Discovered:      [count]                        ║
║  Flagged for Expert:            [count]                        ║
║  Counter-checks performed:      [count]                        ║
║                                                                ║
╚═══════════════════════════════════════════════════════════════╝
```

---

## Iteration Tracking

```
ITERATION CHECK:
Current iteration: [N] of max [quick:1 / standard:3 / deep:10]

□ If max iterations reached AND critical unknowns remain:
  → Proceed anyway, flag unknowns as TRUE UNCERTAINTY
  → Or ABORT if unknowns are decision-critical
```

---

## Transition

- **If GATE_01 = OPEN and critical unknowns addressed** → Proceed to Step 2
- **If more research needed AND iterations remaining** → Stay in Step 1
- **If more research needed BUT max iterations reached** → Proceed with unknowns flagged
- **If framing changed** → Return to Step 0
- **If research reveals decision should not be made** → ABORT (return to Step 0)
