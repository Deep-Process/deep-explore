# Step 05: Synthesize

## Purpose

Organize findings into actionable understanding.

**Time:** 10-15 min

**Inputs:** Challenged Option Map, Consequence Map

**Outputs:** Synthesis ready for final report

**Enforcement layers active:** ASSUMPTIONS_DECLARED, EVR, COUNTER-CHECKS, POST-PHASE CHECKLIST, GATE_05

---

## 05.0 ASSUMPTIONS_DECLARED (MANDATORY)

**Execute BEFORE any synthesis begins.**

```
ASSUMPTIONS_DECLARED for Phase 5:
┌──────┬──────────────────────────────────────┬──────────────┬────────────┬──────────────────────────────┐
│ ID   │ Assumption                           │ Type         │ Confidence │ Falsification Criterion      │
├──────┼──────────────────────────────────────┼──────────────┼────────────┼──────────────────────────────┤
│ H-5xx│ "[assumed clustering criteria]"      │ INTERPRETIVE │ HIGH/MED/  │ "[better clustering exists]"  │
│ H-5xx│ "[assumed decision sequence]"        │ DOMAIN       │ LOW        │ "[order is wrong]"           │
│ H-5xx│ "[assumed readiness assessment]"     │ CONTEXTUAL   │            │ "[not ready when said ready]" │
└──────┴──────────────────────────────────────┴──────────────┴────────────┴──────────────────────────────┘
```

---

## 05.1 EXTRACT: Raw Insights Collection

Load method: `data/method-procedures/E003_Minimal_Assertions.md`

**Gather all raw insights from previous phases:**

```
RAW INSIGHTS FROM EXPLORATION:
From Phase 0 (Knowledge Audit):
• [insight 1]
• [insight 2]

From Phase 1 (Research):
• [insight 3]
• [insight 4]

From Phase 2 (Map):
• [insight 5]
• [insight 6]

From Phase 3 (Deepen):
• [insight 7]
• [insight 8]

From Phase 4 (Challenge):
• [insight 9]
• [insight 10]

RAW CLUSTER CANDIDATES:
Options that share characteristics:
• [group 1: options with similar risk profile]
• [group 2: options with similar resource needs]
• [group 3: options with similar philosophy]

[EXTRACT_COMPLETE]
```

---

## 05.2 VERIFY: Validate Synthesis Elements

```
COMPRESSION VERIFICATION:
For each insight, ask: "Can I say this in half the words AND keep accuracy?"

MINIMAL ASSERTIONS (verified):
┌────┬─────────────────────────────────────┬──────────┬────────────────────┐
│ #  │ Assertion                           │ Status   │ Useful for         │
├────┼─────────────────────────────────────┼──────────┼────────────────────┤
│ 1  │ "[compressed principle]"            │ VERIFIED │ [what decision]    │
│ 2  │ "[compressed principle]"            │ ASSUMED  │ [what decision]    │
│ 3  │ "[compressed principle]"            │ VERIFIED │ [what decision]    │
└────┴─────────────────────────────────────┴──────────┴────────────────────┘

CLUSTER VALIDATION:
┌──────────────────┬──────────┬────────────────────────────────────────────┐
│ Cluster          │ Valid?   │ Reason                                     │
├──────────────────┼──────────┼────────────────────────────────────────────┤
│ [cluster A name] │ Y/N      │ Options within feel similar? Across feel   │
│                  │          │ different? 2-5 clusters total?             │
└──────────────────┴──────────┴────────────────────────────────────────────┘

CLUSTERING CRITERIA USED:
□ RISK PROFILE — similar risk/reward balance
□ RESOURCE NEED — similar investment required
□ REVERSIBILITY — similar ability to change later
□ SPEED — similar time to implement/results
□ PHILOSOPHY — similar underlying approach

[VERIFY_COMPLETE]
```

**★ KEY_CLAIM: "Clusters represent genuinely distinct strategic paths, not arbitrary groupings."**

**COUNTER-CHECKS (minimum per depth: quick=1, standard=2, deep=3):**
```
COUNTER-CHECK #N:
  claim: "These clusters capture the distinct strategic options"
  disproof: "An alternative clustering would be more useful or accurate"
  search_attempt: "[try clustering by different dimension, check if clusters
                    overlap too much, check if a cluster is missing]"
  result: CONFIRMED | WEAKENED | REFUTED
  action: [if WEAKENED: revise clustering]
```

---

## 05.3 RENDER: Synthesis Output

### Strategic Clusters

```
CLUSTER A: "[descriptive name]"
├── Configuration: [D1:X + D2:Y + ...]
├── Core philosophy: [underlying approach]
├── Best for: [what situation]
├── Requires: [resources, skills, conditions]
├── Risk profile: [HIGH/MED/LOW]
├── Reversibility: [HIGH/MED/LOW/IRREVERSIBLE]
├── Time to results: [fast/medium/slow]
└── Key trade-off: [what you sacrifice]

CLUSTER B: "[descriptive name]"
├── Configuration: [D1:A + D2:B + ...]
├── Core philosophy: [underlying approach]
├── Best for: [what situation]
├── Requires: [resources, skills, conditions]
├── Risk profile: [HIGH/MED/LOW]
├── Reversibility: [HIGH/MED/LOW/IRREVERSIBLE]
├── Time to results: [fast/medium/slow]
└── Key trade-off: [what you sacrifice]
```

### Cluster Comparison Matrix

```
┌─────────────────┬───────────────┬───────────────┬───────────────┐
│ Criterion       │ Cluster A     │ Cluster B     │ Cluster C     │
├─────────────────┼───────────────┼───────────────┼───────────────┤
│ Risk            │ HIGH/MED/LOW  │ HIGH/MED/LOW  │ HIGH/MED/LOW  │
│ Investment      │ $$$           │ $$            │ $             │
│ Time to results │ fast/med/slow │ fast/med/slow │ fast/med/slow │
│ Reversibility   │ HIGH/MED/LOW  │ HIGH/MED/LOW  │ HIGH/MED/LOW  │
│ Upside          │ HIGH/MED/LOW  │ HIGH/MED/LOW  │ HIGH/MED/LOW  │
│ Complexity      │ HIGH/MED/LOW  │ HIGH/MED/LOW  │ HIGH/MED/LOW  │
└─────────────────┴───────────────┴───────────────┴───────────────┘

BEST CLUSTER FOR:
• Maximize upside: Cluster ___
• Minimize risk: Cluster ___
• Move fast: Cluster ___
• Preserve optionality: Cluster ___
```

### Independent Decisions

```
INDEPENDENT DECISIONS (not tied to cluster choice):
• [decision] — can be made regardless of cluster
• [decision] — orthogonal to main choice
```

### Decision Sequence

```
1. DECIDE FIRST (prerequisite):
   • [decision] — because: [why first]

2. DECIDE NEXT (after #1):
   • [decision] — depends on: [what]

3. CAN WAIT (preserve optionality):
   • [decision] — can delay until: [trigger]

4. WILL EMERGE (don't force):
   • [decision] — will become clear when: [condition]
```

### Decision Readiness Assessment

```
┌─────────────────────┬────────────┬────────────────────────────┐
│ Decision            │ Readiness  │ What would help            │
├─────────────────────┼────────────┼────────────────────────────┤
│ [decision 1]        │ READY      │ -                          │
│ [decision 2]        │ ALMOST     │ [verify X]                 │
│ [decision 3]        │ NOT READY  │ [research Y]               │
└─────────────────────┴────────────┴────────────────────────────┘
```

### Remaining Information Gaps

Load method: `data/method-procedures/E007_Information_Questions.md`

```
HIGHEST-VALUE QUESTIONS:
"Which information would change my decision the most?"
• [question 1] — impact: [HIGH/MED]
• [question 2] — impact: [HIGH/MED]

IGNORED OBVIOUS:
"What is everyone ignoring because it seems obvious?"
• [observation]
```

```
[RENDER_COMPLETE]
```

---

## POST-PHASE CHECKLIST (MANDATORY)

```
PHASE_05 COMPLETION CHECKLIST:

□ ASSUMPTIONS_DECLARED logged?             [count: ___]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ Minimal assertions produced?             [Y/N, count: ___]
□ Strategic clusters identified?           [Y/N, count: ___]
□ Clusters validated (2-5, distinct)?      [Y/N]
□ Comparison matrix built?                 [Y/N]
□ Decision sequence defined?               [Y/N]
□ Readiness assessed per decision?         [Y/N]
□ Remaining gaps identified?               [Y/N]
□ Counter-checks performed?               [count: ___ (min: ___)]

CHECKLIST_STATUS: PASS | FAIL
IF FAIL: Fix before proceeding.
```

---

## GATE_05: SYNTHESIZE EXIT

```
GATE_05 BINDING CHECK:

□ Minimal assertions produced              — [PASS/FAIL] — CRITICAL
□ Strategic clusters identified            — [PASS/FAIL] — CRITICAL
□ Decision sequence defined                — [PASS/FAIL] — REQUIRED
□ Readiness assessed                       — [PASS/FAIL] — REQUIRED
□ Counter-checks performed                 — [PASS/FAIL] — REQUIRED
□ Post-phase checklist PASSED              — [PASS/FAIL] — CRITICAL

GATE_05 STATUS: OPEN | LOCKED
```

---

## Output: Synthesis Summary

```
╔═══════════════════════════════════════════════════════════════╗
║  SYNTHESIS SUMMARY                                             ║
╠═══════════════════════════════════════════════════════════════╣
║                                                                ║
║  MINIMAL ASSERTIONS: [count]                                   ║
║  STRATEGIC CLUSTERS: [count]                                   ║
║                                                                ║
║  DECISION READINESS:                                           ║
║  • Ready:     [count]                                          ║
║  • Almost:    [count]                                          ║
║  • Not Ready: [count]                                          ║
║                                                                ║
║  REMAINING GAPS: [count]                                       ║
║  COUNTER-CHECKS: [count]                                       ║
║                                                                ║
╚═══════════════════════════════════════════════════════════════╝
```

---

## Transition

- **If GATE_05 = OPEN** → Proceed to Step 6 (always — synthesis is complete)
