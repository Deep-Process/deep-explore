# Step 00: Knowledge Audit

## Purpose

Map what you know and don't know BEFORE exploring options.

**Time:** 10-15 min (Standard), 5 min (Quick)

**Inputs:** User's decision/question, context provided

**Outputs:** Knowledge Map, Research Queue

**Enforcement layers active:** ASSUMPTIONS_DECLARED, EVR, POST-PHASE CHECKLIST, GATE_00

---

## 00.0 Invocation — Depth Selection

**Display this dialog FIRST, before doing anything else. HALT until user responds.**

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                      DEEP EXPLORE V3.0                                     ║
║                      Decision Space Exploration                            ║
╠═══════════════════════════════════════════════════════════════════════════╣
║                                                                            ║
║  Before we begin, choose the exploration depth:                           ║
║                                                                            ║
║  [1] QUICK  (10-20 min)                                                   ║
║      Basic option map, top 2 options, quick readiness check               ║
║      → Urgent, low-stakes, or initial orientation                         ║
║                                                                            ║
║  [2] STANDARD  (45-90 min)                                                ║
║      Full option map (4-6 dims), VERIFIED vs ASSUMED consequences         ║
║      Premortem, bias check, strategic clusters, full report               ║
║      → Important decision, need confidence                                ║
║                                                                            ║
║  [3] DEEP  (2-4 hours)                                                    ║
║      Exhaustive map, all options, multiple iterations                      ║
║      Devil's advocate, black swan hunting, dependency analysis            ║
║      → Critical/irreversible, very high stakes                            ║
║                                                                            ║
║  Choose: [1] / [2] / [3]                                                  ║
║                                                                            ║
╚═══════════════════════════════════════════════════════════════════════════╝
```

**After user selection — execute in this exact order:**
1. Save: `depth = quick | standard | deep`
2. Scan user's decision description for fear signals (see workflow.md FEAR DETECTION)
3. Set: `fear_analysis = on | off`
4. Initialize PROCESS_LOG with depth and fear_analysis settings
5. Continue to 00.1

**ENFORCEMENT:** If depth is not set, ALL subsequent steps are LOCKED. No proceeding.

---

## 00.1 ASSUMPTIONS_DECLARED (MANDATORY)

**Execute BEFORE any extraction. List all interpretive decisions as hypotheses.**

```
ASSUMPTIONS_DECLARED for Phase 0:
┌──────┬──────────────────────────────────────┬──────────────┬────────────┬──────────────────────────────┐
│ ID   │ Assumption                           │ Type         │ Confidence │ Falsification Criterion      │
├──────┼──────────────────────────────────────┼──────────────┼────────────┼──────────────────────────────┤
│ H-001│ "[what we interpret the decision to  │ INTERPRETIVE │ HIGH/MED/  │ "[user clarifies otherwise]" │
│      │  be about]"                          │              │ LOW        │                              │
│ H-002│ "[assumed scope of exploration]"     │ CONTEXTUAL   │            │ "[if scope is different]"    │
│ H-003│ "[domain assumption]"               │ DOMAIN       │            │ "[what disproves]"           │
└──────┴──────────────────────────────────────┴──────────────┴────────────┴──────────────────────────────┘

ENFORCEMENT: If this table is empty, emit:
  RED_FLAG: "Zero assumptions declared — re-examine. Every decision framing
  involves interpretive choices. Declare them."
```

---

## 00.2 EXTRACT: Frame the Decision

**Gather raw decision elements. No interpretation yet.**

```
RAW EXTRACTION:

USER'S WORDS (verbatim quote):
"[exact user input about the decision]"

DECISION ELEMENTS EXTRACTED:
1. [element 1 from user input]
2. [element 2 from user input]
3. [element 3 from user input]

CONTEXT ELEMENTS:
• [context 1]
• [context 2]

FEAR SIGNALS DETECTED: [list any fear/concern language found]

[EXTRACT_COMPLETE]
```

## 00.3 VERIFY: Validate Decision Frame

**Verify extracted elements are accurate and complete.**

```
VERIFICATION:

DECISION STATEMENT:
"We need to decide: _______________________________________"
VERIFICATION: Does this capture ALL elements from user input? [Y/N]
  IF N → list missing elements, re-extract

STAKES: [ ] HIGH  [ ] MEDIUM  [ ] LOW
VERIFICATION: Based on what evidence? [source]

WHY IT MATTERS:
• Good outcome: ________________________________________
• Bad outcome: _________________________________________
• Not deciding: ________________________________________
VERIFICATION: Are outcomes based on evidence or assumption?
  Evidence: [list] | Assumption: [tag with H-ID from ASSUMPTIONS_DECLARED]

[VERIFY_COMPLETE]
```

## 00.4 RENDER: Knowledge Inventory

**Now produce formatted output (only after verification).**

```
KNOWN FACTS (certain, with evidence):
┌───────────────────────────────────┬─────────────────────────────┐
│ Fact                              │ Source/Evidence              │
├───────────────────────────────────┼─────────────────────────────┤
│                                   │                             │
└───────────────────────────────────┴─────────────────────────────┘

ASSUMPTIONS (believed, not verified):
┌───────────────────────────────────┬─────────────┬───────────────┐
│ Assumption                        │ Confidence  │ Verify?       │
├───────────────────────────────────┼─────────────┼───────────────┤
│                                   │ HIGH/MED/LOW│ Y/N           │
└───────────────────────────────────┴─────────────┴───────────────┘

KNOWN UNKNOWNS (questions you have):
┌───────────────────────────────────┬─────────────┬───────────────┐
│ Question                          │ Importance  │ Can research? │
├───────────────────────────────────┼─────────────┼───────────────┤
│                                   │ HIGH/MED/LOW│ Y/N           │
└───────────────────────────────────┴─────────────┴───────────────┘

[RENDER_COMPLETE]
```

---

## 00.5 Surface Unknown Unknowns

**Knowledge categories:**
- **Known Facts** = Things you know and can verify
- **Assumptions** = Things you believe but haven't verified
- **Known Unknowns** = Questions you know you have
- **Unknown Unknowns** = Blind spots you don't know exist yet

This step targets **Unknown Unknowns** — the most dangerous category.

Load method: `data/method-procedures/E001_Abductive_Reasoning.md`

Use abductive reasoning to discover blind spots:

```
PROMPT 1: DOMAIN EXPERTISE GAP
"What would someone with 10 years experience in [domain] know
that a newcomer typically doesn't?"

PROMPT 2: COMMON MISTAKES
"What are the most common mistakes people make when deciding
about [decision area]?"

PROMPT 3: HIDDEN DEPENDENCIES
"What external factors affect [decision] that aren't obvious?"

PROMPT 4: TECHNICAL CONSTRAINTS
"What technical limitations exist that could eliminate options?"

PROMPT 5: ECOSYSTEM STATE
"What is the current state of [relevant market/technology]?
What has changed recently?"
```

For each prompt: list discoveries and add to Known Unknowns.

**★ KEY_CLAIM: "All significant unknown unknowns have been surfaced."**

**COUNTER-CHECK on ★:**
```
COUNTER-CHECK #1:
  claim: "All significant unknown unknowns have been surfaced"
  disproof: "There exists a critical blind spot not covered by prompts 1-5"
  search_attempt: "[try additional angle: regulatory, cultural, timing, etc.]"
  result: CONFIRMED | WEAKENED | REFUTED
  action: [if WEAKENED/REFUTED: add missing area, re-run prompts]
```

---

## 00.6 Prioritize Research Needs

```
                      IMPACT ON DECISION
                    HIGH              LOW
         ┌─────────────────────┬─────────────────────┐
    HIGH │  P1: MUST RESEARCH  │  P3: IF TIME        │
  EFFORT ├─────────────────────┼─────────────────────┤
    LOW  │  P2: MUST RESEARCH  │  P4: SKIP           │
         └─────────────────────┴─────────────────────┘

RESEARCH QUEUE:
1. [unknown] - priority: P1/P2 - method: ___
2. [unknown] - priority: P1/P2 - method: ___
3. ...
```

---

## 00.7 Fear Analysis (when fear_analysis=on)

**Triggered when:** User expresses uncertainty, fear, or sees blockers.

Load method: `data/method-procedures/E008_Failure_Reason_Exploration.md`

**Note:** E008 uses the UNIFIED FAILURE TAXONOMY (shared with M021 Premortem in Step 4).

```
FEAR INVENTORY:
"What am I afraid will go wrong?"

┌───────────────────────────────┬─────────────┬───────────────────┐
│ Fear                          │ Type        │ Status            │
├───────────────────────────────┼─────────────┼───────────────────┤
│                               │ STRUCTURAL  │ BLOCKER/OK        │
│                               │ OPERATIONAL │ ADDRESSABLE       │
│                               │ EXTERNAL    │ MONITOR           │
│                               │ COGNITIVE   │ VERIFY/DISMISS    │
└───────────────────────────────┴─────────────┴───────────────────┘

UNIFIED TYPE KEY (used by E008 and M021):
• STRUCTURAL = Hard limits (physics, law, economics) → cannot work around
• OPERATIONAL = Constraints (resources, skills, time) → can potentially address
• EXTERNAL = Outside control (market, technology, stakeholders) → monitor + contingency
• COGNITIVE = Assumptions (untested beliefs, biases) → verify or dismiss
```

Load method: `data/method-procedures/E011_Control_Influence_Analysis.md`

```
CONTROL ANALYSIS:
┌───────────────────────────────┬─────────────┬───────────────────┐
│ Concern                       │ Zone        │ Response          │
├───────────────────────────────┼─────────────┼───────────────────┤
│                               │ CTRL/INF/NO │ [action]          │
└───────────────────────────────┴─────────────┴───────────────────┘
```

Load method: `data/method-procedures/E012_Fundamental_Block_Analysis.md`

```
BLOCKER ANALYSIS:
┌───────────────────────────────┬─────────────┬───────────────────┐
│ Suspected Wall                │ Status      │ Workaround        │
├───────────────────────────────┼─────────────┼───────────────────┤
│                               │ TRUE/FALSE/ │                   │
│                               │ MOVEABLE    │                   │
└───────────────────────────────┴─────────────┴───────────────────┘
```

Load method: `data/method-procedures/E009_Reverse_Abduction.md` (if user sees "impossible")

```
IF USER THINKS SOMETHING IS IMPOSSIBLE:
"If this worked, what would need to be true?"

REQUIRED CONDITIONS FOR SUCCESS:
1. ___
2. ___
Which conditions are actually achievable? [list]
```

Load method: `data/method-procedures/E013_Contrast_Exploration.md`

```
CONTRAST ANALYSIS:
┌───────────────────────────────┬─────────────┬───────────────────┐
│ Comparable                    │ Outcome     │ Key Lesson        │
├───────────────────────────────┼─────────────┼───────────────────┤
│                               │ SUCCESS/FAIL│                   │
└───────────────────────────────┴─────────────┴───────────────────┘
```

**Add fear-related items to Research Queue.**

---

## POST-PHASE CHECKLIST (MANDATORY)

```
PHASE_00 COMPLETION CHECKLIST:

□ Depth selected and saved?                [Y/N]
□ Fear detection scan completed?           [Y/N]
□ ASSUMPTIONS_DECLARED logged?             [count: ___]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ Decision framed in one sentence?         [Y/N]
□ Stakes assessed?                         [Y/N]
□ Knowledge inventory complete?            [Y/N]
  - Known Facts: [count]
  - Assumptions: [count]
  - Known Unknowns: [count]
  - Discovered Unknowns: [count]
□ Counter-check performed on ★ claims?     [count: ___]
□ Research queue generated?                [Y/N, count: ___]
□ Fear analysis completed (if on)?         [Y/N or N/A]

CHECKLIST_STATUS: PASS | FAIL
IF FAIL: Fix before proceeding.
```

---

## GATE_00: KNOWLEDGE AUDIT EXIT

```
GATE_00 BINDING CHECK:

□ Decision framed (one sentence)           — [PASS/FAIL] — CRITICAL
□ Stakes assessed (HIGH/MEDIUM/LOW)        — [PASS/FAIL] — REQUIRED
□ Knowledge inventory complete             — [PASS/FAIL] — CRITICAL
□ Research queue generated                 — [PASS/FAIL] — REQUIRED
□ ASSUMPTIONS_DECLARED logged (min 1)      — [PASS/FAIL] — CRITICAL
□ Post-phase checklist PASSED              — [PASS/FAIL] — CRITICAL

GATE_00 STATUS: OPEN | LOCKED

IF LOCKED and item is CRITICAL:
  → Fix the failing condition
  → OR emit SCOPE_REDUCTION_DECLARATION (requires user approval)

IF LOCKED and item is REQUIRED:
  → Fix OR emit SCOPE_REDUCTION_DECLARATION (logged, no user approval needed)
```

---

## Output: Knowledge Map

```
╔═══════════════════════════════════════════════════════════════╗
║  KNOWLEDGE MAP                                                 ║
╠═══════════════════════════════════════════════════════════════╣
║                                                                ║
║  DECISION: ________________________________________           ║
║  STAKES: [ ] HIGH  [ ] MEDIUM  [ ] LOW                        ║
║                                                                ║
║  Known Facts:           [count]                                ║
║  Assumptions:           [count] (need verify: [count])        ║
║  Known Unknowns:        [count]                                ║
║  Discovered Unknowns:   [count]                                ║
║                                                                ║
║  Research Queue:        [count] items                          ║
║  Assumptions Declared:  [count] hypotheses                     ║
║                                                                ║
╚═══════════════════════════════════════════════════════════════╝
```

## Output: Fear Map (when fear_analysis=on)

```
╔═══════════════════════════════════════════════════════════════╗
║  FEAR MAP                                                      ║
╠═══════════════════════════════════════════════════════════════╣
║                                                                ║
║  FEARS INVENTORIED: [count]                                   ║
║    • Structural: [count]                                       ║
║    • Operational: [count]                                      ║
║    • Cognitive: [count]                                        ║
║                                                                ║
║  CONTROL ANALYSIS:                                             ║
║    • Controllable: [count]                                     ║
║    • Influenceable: [count]                                    ║
║    • No control: [count]                                       ║
║                                                                ║
║  BLOCKERS ANALYZED: [count]                                   ║
║    • True walls: [count]                                       ║
║    • False walls: [count]                                      ║
║    • Moveable walls: [count]                                   ║
║                                                                ║
║  FEAR-RELATED RESEARCH: [count] items added to queue          ║
║                                                                ║
╚═══════════════════════════════════════════════════════════════╝
```

---

## Transition

- **If GATE_00 = OPEN and research queue has items** → Proceed to Step 1
- **If GATE_00 = OPEN and research queue is empty** → Skip to Step 2 (requires SCOPE_REDUCTION_DECLARATION)
- **If frame unclear after 3 attempts** → Escalate or ABORT
- **If GATE_00 = LOCKED** → Fix failing conditions or declare SCOPE_REDUCTION

---

## ABORT: When NOT to Decide

```
□ PREMATURE: Critical information unavailable
  → Output: "Wait until [condition] before deciding"

□ WRONG QUESTION: The framed decision is not the real problem
  → Output: "Reframe to [better question] instead"

□ EXTERNAL DEPENDENCY: Decision depends on someone else first
  → Output: "Blocked by [dependency], escalate to [who]"

□ NO VIABLE OPTIONS: All options have unacceptable consequences
  → Output: "No good options exist, consider [alternatives]"
```

## Escalation: When Stuck in Step 0

If frame remains unclear after 3 attempts:
1. **Simplify**: Break into smaller sub-decisions
2. **Consult**: Ask user for clarification
3. **Pivot**: Try different framing angle
4. **Abort**: If still unclear, decision may be premature
