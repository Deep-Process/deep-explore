# Step 06: Output

## Purpose

Deliver complete exploration report.

**Time:** 5-10 min

**Inputs:** All outputs from Steps 0-5

**Outputs:** EXPLORATION REPORT

**Enforcement layers active:** ASSUMPTIONS_DECLARED, EVR, POST-PHASE CHECKLIST, GATE_06

---

## 06.0 ASSUMPTIONS_DECLARED (MANDATORY)

**Execute BEFORE report generation.**

```
ASSUMPTIONS_DECLARED for Phase 6:
┌──────┬──────────────────────────────────────┬──────────────┬────────────┬──────────────────────────────┐
│ ID   │ Assumption                           │ Type         │ Confidence │ Falsification Criterion      │
├──────┼──────────────────────────────────────┼──────────────┼────────────┼──────────────────────────────┤
│ H-6xx│ "[assumed report completeness]"      │ INTERPRETIVE │ HIGH/MED/  │ "[section missing content]"  │
│ H-6xx│ "[assumed score accuracy]"           │ CONTEXTUAL   │ LOW        │ "[scoring error found]"      │
└──────┴──────────────────────────────────────┴──────────────┴────────────┴──────────────────────────────┘
```

---

## 06.1 EXTRACT: Gather All Phase Outputs

**Collect outputs from every phase — verify each exists:**

```
PHASE OUTPUT INVENTORY:

□ Phase 0: Knowledge Map                    [EXISTS/MISSING]
□ Phase 0: Research Queue                   [EXISTS/MISSING]
□ Phase 0: Fear Map (if fear_analysis=on)   [EXISTS/MISSING/N/A]
□ Phase 1: Research Summary                 [EXISTS/MISSING]
□ Phase 1: Updated Knowledge Map            [EXISTS/MISSING]
□ Phase 2: Option Map (Morphological Box)   [EXISTS/MISSING]
□ Phase 3: Consequence Map                  [EXISTS/MISSING]
□ Phase 3: Reversibility Assessment         [EXISTS/MISSING]
□ Phase 3: Dependency Graph                 [EXISTS/MISSING]
□ Phase 4: Challenge Results                [EXISTS/MISSING]
□ Phase 4: Fear Resolution (if on)          [EXISTS/MISSING/N/A]
□ Phase 5: Minimal Assertions               [EXISTS/MISSING]
□ Phase 5: Strategic Clusters               [EXISTS/MISSING]
□ Phase 5: Decision Sequence                [EXISTS/MISSING]
□ Phase 5: Readiness Assessment             [EXISTS/MISSING]

MISSING ITEMS: [count]
IF count > 0: Flag each missing item.
  CRITICAL items → HALT → go back and produce
  REQUIRED items → SCOPE_REDUCTION_DECLARATION

SCOPE_REDUCTION LOG (all accumulated):
[list all SCOPE_REDUCTION_DECLARATIONs from all phases]

[EXTRACT_COMPLETE]
```

---

## 06.2 VERIFY: Coverage Score Calculation

Load: `data/coverage-scoring.yaml`

```
COVERAGE CALCULATION (V3.0):

DISCOVERY (with caps):
Dimensions discovered:     min([N], 8) × 1.5 = [score]
Options enumerated:        min([N], 20) × 0.5 = [score]

VERIFICATION (high value):
Consequences VERIFIED:     [N] × 2.0 = [score]
Consequences ASSUMED:      [N] × 0.2 = [score]
Assumptions tested:        [N] × 1.5 = [score]
Assumptions falsified:     [N] × 2.0 = [score]

ANALYSIS:
Unknown unknowns surfaced: [N] × 1.5 = [score]
Boundaries identified:     [N] × 1.0 = [score]
Causal relationships:      [N] × 1.0 = [score]

CHALLENGE:
Premortem causes:          [N] × 0.5 = [score]
Black swans identified:    [N] × 0.5 = [score]
Biases checked:            [N] × 0.3 = [score]
Beliefs stress tested:     [N] × 0.5 = [score]

V3.0 ENFORCEMENT BONUSES:
Gates passed clean:        [N] × 1.0 = [score]
Counter-checks performed:  [N] × 0.5 = [score]
ASSUMED→VERIFIED upgrades: [N] × 1.5 = [score]

IF fear_analysis=on:
Fears classified:          [N] × 0.5 = [score]
False walls identified:    [N] × 1.5 = [score]
True walls confirmed:      [N] × 1.5 = [score]
Controllable concerns:     [N] × 0.5 = [score]
Success paths discovered:  [N] × 2.0 = [score]
Comparables analyzed:      [N] × 0.5 = [score]

RAW SCORE: [sum]
```

```
QUALITY GATE CHECK:

┌────────────────────────────┬────────┬──────────┬────────┐
│ Requirement                │ Quick  │ Standard │ Deep   │
├────────────────────────────┼────────┼──────────┼────────┤
│ Dimensions (min)           │ 3      │ 4        │ 5      │
│ Options (min)              │ 6      │ 12       │ 15     │
│ Verified consequences (min)│ 2      │ 5        │ 10     │
│ Assumptions tested (min)   │ 1      │ 3        │ 5      │
│ Verification ratio (min)   │ -      │ 30%      │ 50%    │
│ Premortem causes (min)     │ -      │ 3        │ 5      │
│ Biases checked (min)       │ -      │ -        │ 5      │
│ Counter-checks total (min) │ 6      │ 12       │ 18     │
└────────────────────────────┴────────┴──────────┴────────┘

VERIFICATION RATIO = verified / (verified + assumed) × 100%
Your ratio: [N]% — Required: [M]% — [PASS / FAIL]

QUALITY GATE: [PASSED / FAILED — reason]
```

```
THRESHOLDS (by depth):

Quick:    C ≥ 15 COMPREHENSIVE | C ≥ 10 ADEQUATE | C ≥ 5 PARTIAL
Standard: C ≥ 35 COMPREHENSIVE | C ≥ 22 ADEQUATE | C ≥ 12 PARTIAL
Deep:     C ≥ 50 COMPREHENSIVE | C ≥ 35 ADEQUATE | C ≥ 20 PARTIAL

NOTE: Quality gate failure caps level regardless of score.
When fear_analysis=on, thresholds increase by +5.

[VERIFY_COMPLETE]
```

---

## 06.3 RENDER: Generate Report

Load template: `data/exploration-report-template.md`

```
SECTION 1: WHAT WE LEARNED
□ Key discoveries (from Step 1)
□ Surprises
□ Changed assumptions

SECTION 2: WHAT WE STILL DON'T KNOW
□ Critical unknowns (flagged in Step 1)
□ True uncertainties (from Step 4)
□ Parked questions
□ Flagged for expert

SECTION 3: OPTION MAP
□ Dimensions and options (from Step 2)
□ Constraints
□ Valid combinations

SECTION 4: STRATEGIC CLUSTERS
□ Clusters (from Step 5)
□ Best-for scenarios
□ Trade-offs

SECTION 5: CONSEQUENCE MAP
□ Consequences per cluster (from Step 3)
□ Mark VERIFIED vs ASSUMED
□ Risks

SECTION 6: DECISION READINESS
□ Sequence (from Step 5)
□ Readiness per decision
□ What would help

SECTION 7: SUGGESTED NEXT STEPS
□ If want more clarity
□ If ready to decide
□ If want to explore deeper

SECTION 8: FEAR RESOLUTION (when fear_analysis=on)
□ Original fears (from Step 0)
□ Resolution status (RESOLVED/ADDRESSED/REMAINS)
□ Minimal tests designed (from Step 4)
□ Growth assessment
□ What user controls vs accepts
□ False walls cleared
□ True walls confirmed

SECTION 9: PROCESS INTEGRITY (V3.0 addition)
□ All SCOPE_REDUCTION_DECLARATIONs listed
□ All ASSUMPTIONS_DECLARED with final status
□ Gate pass/fail summary
□ Counter-check summary
□ EVR sequence compliance per phase
```

```
ENFORCEMENT: Each section MUST have content.
If a section has no content:
  → IF section is applicable: Flag MISSING_CONTENT → go back and produce
  → IF section is not applicable (e.g., Section 8 when fear_analysis=off):
    Mark "N/A — [reason]"

[RENDER_COMPLETE]
```

---

## POST-PHASE CHECKLIST (MANDATORY)

```
PHASE_06 COMPLETION CHECKLIST:

□ ASSUMPTIONS_DECLARED logged?             [count: ___]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ All phase outputs collected?             [Y/N — missing: ___]
□ All report sections filled?              [Y/N — empty: ___]
□ Coverage score calculated?               [Y/N — score: ___]
□ Quality gate checked?                    [Y/N — result: ___]
□ Process integrity section complete?      [Y/N]
□ All SCOPE_REDUCTION_DECLARATIONs listed? [Y/N — count: ___]
□ Process log finalized?                   [Y/N]

CHECKLIST_STATUS: PASS | FAIL
IF FAIL: Fix before finalizing.
```

---

## GATE_06: OUTPUT EXIT

```
GATE_06 BINDING CHECK:

□ All report sections filled               — [PASS/FAIL] — CRITICAL
□ Coverage score calculated                 — [PASS/FAIL] — CRITICAL
□ Quality gate checked                      — [PASS/FAIL] — CRITICAL
□ Process log complete                      — [PASS/FAIL] — REQUIRED
□ All SCOPE_REDUCTION_DECLARATIONs listed   — [PASS/FAIL] — CRITICAL
□ Post-phase checklist PASSED               — [PASS/FAIL] — CRITICAL

GATE_06 STATUS: OPEN | LOCKED
```

---

## Final Output

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                      DEEP EXPLORE V3.0 REPORT                              ║
╠═══════════════════════════════════════════════════════════════════════════╣
║                                                                            ║
║  DECISION: [from Step 0]                                                   ║
║  DATE: [today]                                                             ║
║  CONFIG: depth=[quick|standard|deep] fear_analysis=[on|off]                ║
║  COVERAGE: [score] — [level]                                               ║
║  QUALITY GATE: [PASSED/FAILED]                                             ║
║                                                                            ║
║  PROCESS INTEGRITY:                                                        ║
║  ├── Gates passed: [N]/7                                                   ║
║  ├── Scope reductions: [N]                                                 ║
║  ├── Counter-checks: [N]                                                   ║
║  ├── Assumptions declared: [N]                                             ║
║  └── EVR compliance: [N]/7 phases                                          ║
║                                                                            ║
╠═══════════════════════════════════════════════════════════════════════════╣
║                                                                            ║
║  [SECTIONS 1-9 content]                                                    ║
║                                                                            ║
╚═══════════════════════════════════════════════════════════════════════════╝
```

---

## Exploration Complete

The report is the final deliverable.

User now has:
- Understanding of what they learned
- Clarity on what they don't know
- Map of options with consequences
- Assessment of decision readiness
- Guidance on next steps
- **Process integrity evidence (V3.0)**

**When fear_analysis=on, user also has:**
- Resolution status for each original fear
- Minimal tests designed to learn (failure = data)
- Clear separation of controllable vs uncontrollable
- False walls cleared (proceed with confidence)
- True walls confirmed (save wasted effort)
- Growth assessment for each option
