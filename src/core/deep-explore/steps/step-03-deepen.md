# Step 03: Deepen

## Purpose

Understand consequences at multiple abstraction levels.

**Time:** 20-40 min

**Inputs:** Option Map from Step 2

**Outputs:** Consequence Map with VERIFIED/ASSUMED status

**Enforcement layers active:** ASSUMPTIONS_DECLARED, EVR, COUNTER-CHECKS, POST-PHASE CHECKLIST, GATE_03

---

## 03.0 ASSUMPTIONS_DECLARED (MANDATORY)

**Execute BEFORE any consequence analysis.**

```
ASSUMPTIONS_DECLARED for Phase 3:
┌──────┬──────────────────────────────────────┬──────────────┬────────────┬──────────────────────────────┐
│ ID   │ Assumption                           │ Type         │ Confidence │ Falsification Criterion      │
├──────┼──────────────────────────────────────┼──────────────┼────────────┼──────────────────────────────┤
│ H-3xx│ "[assumed causal relationships]"     │ DOMAIN       │ HIGH/MED/  │ "[causation doesn't hold]"   │
│ H-3xx│ "[assumed consequence scope]"        │ INTERPRETIVE │ LOW        │ "[scope is wider/narrower]"  │
│ H-3xx│ "[assumed reversibility]"            │ CONTEXTUAL   │            │ "[option is less reversible]" │
└──────┴──────────────────────────────────────┴──────────────┴────────────┴──────────────────────────────┘
```

---

## 03.1 EXTRACT: Abstraction Navigation

For key options, explore multiple levels — gather raw observations:

```
OPTION: [name]

ZOOM OUT (WHY) — raw observations:
• "[why this option exists]"
• "[higher goal it serves]"
• "[whether it addresses the right problem]"

CURRENT (WHAT) — raw observations:
• "[what this option is]"
• "[observable trade-offs]"

DRILL DOWN (HOW) — raw observations:
• "[how implementation would work]"
• "[skills/resources needed]"
• "[what could go wrong]"

DRILL DEEPER (DETAILS) — raw observations:
• "[specific tools/technologies]"
• "[integrations needed]"
• "[learning curve]"
```

## 03.2 EXTRACT: Apply Foundational Methods

Load method: `data/method-procedures/E002_Counterfactual_Thinking.md`

For key options, extract:
- "What would NOT happen if this option didn't exist?"
- "Which elements are NECESSARY vs NICE-TO-HAVE?"

Load method: `data/method-procedures/E004_Boundary_Analysis.md`

For key options, extract:
- "Where does this option stop working?"
- "What are the limits?"

Load method: `data/method-procedures/E005_Causal_Models.md`

Build causal model — extract raw relationships:
- "What influences what?"
- "Where are the leverage points?"

```
RAW CAUSAL RELATIONSHIPS:
• [A] → influences → [B] — direction: [positive/negative]
• [C] → depends on → [D] — type: [direct/indirect]

[EXTRACT_COMPLETE]
```

---

## 03.3 VERIFY: Consequence Verification

Load method: `data/method-procedures/M011_Consequence_Analysis.md`

**For each significant option — verify each consequence:**

```
CONSEQUENCE VERIFICATION LOG:

OPTION: [description]

IMMEDIATE CONSEQUENCES:
┌────┬──────────────────┬──────────┬──────────────────────────────┐
│ #  │ Consequence      │ Status   │ Evidence / Reason            │
├────┼──────────────────┼──────────┼──────────────────────────────┤
│ 1  │ Gain: [what]     │ VERIFIED │ Source: [evidence]           │
│ 2  │ Cost: [what]     │ ASSUMED  │ Reason not verified: [why]   │
│ 3  │ Risk: [what]     │ VERIFIED │ Source: [evidence]           │
└────┴──────────────────┴──────────┴──────────────────────────────┘

DOWNSTREAM CONSEQUENCES:
┌────┬──────────────────┬──────────┬──────────────────────────────┐
│ #  │ Consequence      │ Status   │ Evidence / Reason            │
├────┼──────────────────┼──────────┼──────────────────────────────┤
│ 4  │ Opens: [what]    │ ASSUMED  │ Reason: [why not verified]   │
│ 5  │ Closes: [what]   │ VERIFIED │ Source: [evidence]           │
│ 6  │ Requires: [what] │ VERIFIED │ Source: [evidence]           │
└────┴──────────────────┴──────────┴──────────────────────────────┘

ENFORCEMENT: Every consequence MUST have status tag.
  Untagged consequence = UNTAGGED_CLAIM → HALT → tag it.

VERIFICATION REQUIREMENT:
  Critical ASSUMED consequences → flag for Step 1 return or accept as risk.

[VERIFY_COMPLETE]
```

**★ KEY_CLAIM: Each verified consequence is genuinely verified (not rubber-stamped).**

**COUNTER-CHECKS (minimum per depth: quick=1, standard=2, deep=3):**
```
COUNTER-CHECK #N:
  claim: "[verified consequence]"
  disproof: "[what would show this consequence doesn't follow]"
  search_attempt: "[alternative causal path, edge case, exception]"
  result: CONFIRMED | WEAKENED | REFUTED
  action: [none | downgrade to ASSUMED | remove consequence]
```

---

## 03.4 VERIFY: Reversibility Check

Load method: `data/method-procedures/M012_Reversibility_Check.md`

```
REVERSIBILITY ASSESSMENT:
┌──────────────┬──────────────┬────────────────────────────────┐
│ Option       │ Reversibility│ Point of No Return             │
├──────────────┼──────────────┼────────────────────────────────┤
│ [option A]   │ HIGH/MED/LOW/│ [when it becomes hard to undo] │
│              │ IRREVERSIBLE │                                │
└──────────────┴──────────────┴────────────────────────────────┘

HIGH = Can change with minimal cost
MEDIUM = Can change with significant cost
LOW = Very difficult to change
IRREVERSIBLE = Cannot undo
```

## 03.5 VERIFY: Dependency Analysis

Load method: `data/method-procedures/M013_Dependency_Analysis.md`

```
DECISION DEPENDENCIES:
├── [Decision A] blocks [Decision B]
├── [Decision C] requires [Decision A] first
└── [Decision D] can be made independently

EXTERNAL DEPENDENCIES:
• [dependency] - controlled by: [who] - status: [VERIFIED/ASSUMED]
```

---

## 03.6 RENDER: Consequence Map

**Only after all verification complete.**

```
╔═══════════════════════════════════════════════════════════════╗
║  CONSEQUENCE MAP                                               ║
╠═══════════════════════════════════════════════════════════════╣
║                                                                ║
║  OPTION: [name]                                                ║
║  ├── ✓ [verified consequence] — source: [ref]                 ║
║  ├── ? [assumed consequence] — confidence: [level]             ║
║  ├── ✗ [risk] — probability: [est]                             ║
║  └── Reversibility: [level]                                    ║
║                                                                ║
║  VERIFICATION RATIO: [verified/(verified+assumed)] = [N]%      ║
║                                                                ║
╚═══════════════════════════════════════════════════════════════╝

[RENDER_COMPLETE]
```

---

## POST-PHASE CHECKLIST (MANDATORY)

```
PHASE_03 COMPLETION CHECKLIST:

□ ASSUMPTIONS_DECLARED logged?             [count: ___]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ Abstraction levels explored?             [Y/N — WHY/WHAT/HOW/DETAILS]
□ Counterfactual thinking applied?         [Y/N]
□ Boundary analysis applied?               [Y/N]
□ Causal model built?                      [Y/N]
□ Consequences analyzed per option?        [count: ___]
□ Each consequence tagged VERIFIED/ASSUMED?[Y/N — untagged count: ___]
□ Reversibility assessed per option?       [Y/N]
□ Dependencies mapped?                     [Y/N]
□ Counter-checks performed?               [count: ___ (min: ___)]
□ Verification ratio calculated?           [Y/N — ratio: ___%]

CHECKLIST_STATUS: PASS | FAIL
IF FAIL: Fix before proceeding.
```

---

## GATE_03: DEEPEN EXIT

```
GATE_03 BINDING CHECK:

□ Consequences analyzed per option          — [PASS/FAIL] — CRITICAL
□ Each consequence tagged VERIFIED/ASSUMED  — [PASS/FAIL] — CRITICAL
□ Reversibility assessed                    — [PASS/FAIL] — REQUIRED
□ Dependencies mapped                       — [PASS/FAIL] — REQUIRED
□ Counter-checks on key consequences        — [PASS/FAIL] — REQUIRED
□ Post-phase checklist PASSED               — [PASS/FAIL] — CRITICAL

GATE_03 STATUS: OPEN | LOCKED
```

---

## Feedback Loop Check

```
□ Did deepening reveal consequences we can't assess?
  → YES: Return to Step 1 (if iterations remaining)

□ Are critical consequences still ASSUMED?
  → YES: Return to Step 1 to verify (if iterations remaining)

□ Did we discover the problem is different?
  → YES: Return to Step 0

□ Are ALL options' consequences unacceptable?
  → YES: Consider ABORT
```

## Iteration Tracking

```
VERIFICATION LOOP COUNT: [N]

□ If returning to Step 1 more than [quick:1 / standard:2 / deep:3] times:
  → STOP: Proceed with ASSUMED consequences marked as risks
```

---

## Transition

- **If GATE_03 = OPEN and consequences verified** → Proceed to Step 4
- **If verification needed AND iterations remaining** → Return to Step 1
- **If verification needed BUT max loops reached** → Proceed with assumptions flagged
- **If reframe needed** → Return to Step 0
- **If all consequences unacceptable** → Consider ABORT
