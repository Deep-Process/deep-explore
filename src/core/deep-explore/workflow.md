# Deep Explore V3.0 — Execution Program

> This file is an EXECUTION PROGRAM. Every instruction specifies HOW and IN WHAT ORDER.
> For reference documentation, see [reference.md](./reference.md).

---

## PRIORITY DECLARATION

```
PRIORITY ORDER (binding — when in conflict, higher wins):
1. COMPLETENESS — every element covered, no silent omissions
2. DEPTH — thorough analysis of each element
3. ACCURACY — verified over assumed
4. TOKEN_ECONOMY — conciseness

ENFORCEMENT: If agent abbreviates output citing "token limits" or "brevity",
this is a PRIORITY VIOLATION. Re-execute with full output.
```

---

## SELF-CONTAINMENT DECLARATION

```
This process is SELF-CONTAINED:
- All protocols defined in this file or in referenced step/data files
- No external process dependency required
- All enforcement mechanisms defined inline
- All gate conditions specified with pass/fail criteria
- All checklists embedded in step files
```

---

## ENFORCEMENT ARCHITECTURE

```
+------------------------------------------------------------------------------+
|  ENFORCEMENT LAYER STACK (applied to EVERY phase)                            |
+------------------------------------------------------------------------------+
|                                                                              |
|  LAYER 1: ASSUMPTIONS_DECLARED                                               |
|    WHEN: Before any extraction/analysis begins in a phase                    |
|    WHAT: Agent declares all interpretive decisions as hypotheses             |
|    HOW:  Emit ASSUMPTIONS_DECLARED table with ID, type, confidence,          |
|          falsification criterion                                             |
|    ENFORCEMENT: Empty table = RED FLAG → force re-examination                |
|    VIOLATION: Proceeding without declaration = PROTOCOL_VIOLATION → HALT     |
|                                                                              |
|  LAYER 2: EVR SEQUENCE (Extract → Verify → Render)                          |
|    WHEN: During phase execution                                              |
|    WHAT: Strict ordering of data gathering, validation, output               |
|    HOW:  Each sub-phase emits completion tag:                                |
|          [EXTRACT_COMPLETE] → unlocks VERIFY                                 |
|          [VERIFY_COMPLETE] → unlocks RENDER                                  |
|    ENFORCEMENT: RENDER without [VERIFY_COMPLETE] = SEQUENCE_VIOLATION → HALT |
|                                                                              |
|  LAYER 3: COUNTER-CHECKS                                                     |
|    WHEN: After key claims are produced (marked with ★)                       |
|    WHAT: Each key claim challenged with counter-evidence attempt              |
|    HOW:  State claim → state disproof → attempt → record result              |
|    ENFORCEMENT: Missing counter-check log = PROTOCOL_VIOLATION               |
|    MINIMUM: quick=1, standard=2, deep=3 per phase                            |
|                                                                              |
|  LAYER 4: POST-PHASE CHECKLIST                                               |
|    WHEN: After every phase completes                                         |
|    WHAT: Mandatory checklist verifying all phase requirements                 |
|    HOW:  Emit filled checklist with PASS/FAIL per item                       |
|    ENFORCEMENT: Cannot proceed to next phase without checklist               |
|    VIOLATION: Missing checklist = GATE_LOCKED                                |
|                                                                              |
|  LAYER 5: BINDING GATE                                                       |
|    WHEN: At phase exit                                                       |
|    WHAT: Formal conditions that MUST be met to proceed                       |
|    HOW:  Check each condition → PASS/FAIL → gate OPEN/LOCKED                |
|    ENFORCEMENT: LOCKED gate = cannot proceed                                 |
|    ESCAPE: SCOPE_REDUCTION_DECLARATION (formal, logged, user-approved        |
|            for CRITICAL items)                                               |
|                                                                              |
+------------------------------------------------------------------------------+
```

---

## SCOPE_REDUCTION PROTOCOL

```
When agent cannot or chooses not to meet a gate condition:

SCOPE_REDUCTION_DECLARATION:
  gate: [GATE_NN]
  item_skipped: "[specific condition not met]"
  reason: "[honest reason — NOT 'for brevity']"
  impact_assessment: "[what is lost by skipping]"
  completeness_cost: "[how this affects final output]"
  requires_user_approval: [YES for CRITICAL items | NO for advisory items]

IF requires_user_approval = YES:
  → HALT — present declaration to user, wait for approval
  → User may: APPROVE (proceed) | DENY (must complete) | MODIFY (change scope)

IF requires_user_approval = NO:
  → LOG declaration in process log
  → PROCEED with reduced scope

ENFORCEMENT: "Intelligent" omission without SCOPE_REDUCTION_DECLARATION
             = SILENT_OMISSION = CRITICAL PROCESS VIOLATION
```

---

## ASSUMPTIONS_DECLARED PROTOCOL

```
MANDATORY before any extraction/analysis phase.

ASSUMPTIONS_DECLARED:
┌──────┬──────────────────────────┬──────────────┬────────────┬──────────────────────────┐
│ ID   │ Assumption               │ Type         │ Confidence │ Falsification Criterion  │
├──────┼──────────────────────────┼──────────────┼────────────┼──────────────────────────┤
│ H-001│ "[interpretive decision]" │ INTERPRETIVE │ HIGH/MED/  │ "[what would disprove]"  │
│ H-002│ "[context assumption]"   │ CONTEXTUAL   │ LOW        │ "[what would disprove]"  │
│ H-003│ "[domain assumption]"    │ DOMAIN       │            │ "[what would disprove]"  │
└──────┴──────────────────────────┴──────────────┴────────────┴──────────────────────────┘

TYPE KEY:
• INTERPRETIVE = How we read/understand the user's input
• CONTEXTUAL   = What we assume about the situation/environment
• DOMAIN       = What we assume about the subject matter

ENFORCEMENT:
  IF table is empty → agent MUST justify why zero assumptions exist
  IF table has < 2 entries for standard/deep → RED FLAG → re-examine
  Every H-entry tracked through process — updated when evidence arrives
```

---

## EVR SEQUENCE ENFORCEMENT

```
EVERY phase follows: EXTRACT → VERIFY → RENDER

EXTRACT PHASE:
  Gather raw data, observations, user input, research findings.
  NO interpretation, NO formatting, NO conclusions.
  Output: raw data collection
  Tag: [EXTRACT_COMPLETE]

VERIFY PHASE:
  Validate extracted data against evidence.
  Classify each item: VERIFIED | ASSUMED | CONTRADICTED
  Cross-reference with ASSUMPTIONS_DECLARED.
  Tag: [VERIFY_COMPLETE]

RENDER PHASE:
  Produce formatted output: tables, summaries, maps.
  PRECONDITION: [VERIFY_COMPLETE] tag MUST exist.
  Tag: [RENDER_COMPLETE]

ENFORCEMENT:
  Attempting RENDER without [VERIFY_COMPLETE] =
    SEQUENCE_VIOLATION → HALT → return to VERIFY phase

  Attempting VERIFY without [EXTRACT_COMPLETE] =
    SEQUENCE_VIOLATION → HALT → return to EXTRACT phase
```

---

## COUNTER-CHECK PROTOCOL

```
For each claim marked with ★ (KEY_CLAIM):

COUNTER-CHECK:
  claim: "[the assertion]"
  disproof: "[what evidence would refute this]"
  search_attempt: "[what was tried to find counter-evidence]"
  result: CONFIRMED | WEAKENED | REFUTED
  action: [none | reduce confidence | remove claim]

MINIMUM counter-checks per phase:
  quick:    1
  standard: 2
  deep:     3

ENFORCEMENT:
  Counter-check log MUST appear in phase output.
  Missing log = PROTOCOL_VIOLATION → phase cannot pass gate.
```

---

## POST-PHASE CHECKLIST TEMPLATE

```
PHASE_NN COMPLETION CHECKLIST (MANDATORY):

□ All required outputs produced?           [Y/N — list missing if N]
□ ASSUMPTIONS_DECLARED logged?             [count — min 1]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ Counter-checks performed?                [count — min per depth]
□ Key claims marked with ★?               [count]
□ All ASSUMED items flagged?               [Y/N]
□ Artifacts tagged for downstream use?     [Y/N]

CHECKLIST_STATUS: PASS | FAIL

IF FAIL: Cannot proceed. Fix issues or declare SCOPE_REDUCTION.
```

---

## CRITICAL RULES

```
+------------------------------------------------------------------------------+
|  EXPLORATION COMMANDMENTS (with enforcement mechanisms)                      |
+------------------------------------------------------------------------------+
|                                                                              |
|  1. ALWAYS START WITH INVOCATION                                             |
|     Step 0 displays depth selection dialog — HALT until user responds.       |
|     ENFORCEMENT: Step 1 file will not load without depth variable set.       |
|                                                                              |
|  2. KNOWLEDGE BEFORE MAPPING                                                 |
|     Never map options in a space you don't understand.                       |
|     Steps 0 + 1 are NOT optional.                                            |
|     ENFORCEMENT: GATE_01 requires knowledge_map artifact. Without it,        |
|     Step 2 is LOCKED.                                                        |
|                                                                              |
|  3. VERIFY BEFORE CLAIMING                                                   |
|     Mark every consequence as VERIFIED or ASSUMED.                           |
|     ENFORCEMENT: Consequence without status tag = UNTAGGED_CLAIM → HALT.     |
|                                                                              |
|  4. RESPECT DEPTH LIMITS                                                     |
|     quick = 1 iteration, no loops                                            |
|     standard = max 3 iterations                                              |
|     deep = until resolved                                                    |
|     ENFORCEMENT: Iteration counter tracked in process log.                   |
|     Exceeding max = AUTO-PROCEED with flags.                                 |
|                                                                              |
|  5. AUTO-DETECT FEAR                                                         |
|     Don't ask about fear analysis — detect from language.                    |
|     ENFORCEMENT: Fear detection scan is step 0.1 — always executes.          |
|                                                                              |
|  6. USER DECIDES, AI EXPLORES                                                |
|     Output is UNDERSTANDING, not recommendation.                             |
|     ENFORCEMENT: If output contains "I recommend" or "you should",           |
|     flag as RECOMMENDATION_VIOLATION → rephrase as trade-off.                |
|                                                                              |
|  7. NO SILENT OMISSIONS                                                      |
|     Every element from scope MUST appear in output.                          |
|     ENFORCEMENT: SCOPE_REDUCTION_DECLARATION required for any omission.      |
|     Silent omission = CRITICAL PROCESS VIOLATION.                            |
|                                                                              |
|  8. EXTRACT → VERIFY → RENDER                                               |
|     Never render before verifying. Never verify before extracting.           |
|     ENFORCEMENT: Tagged sequence with HALT on violation.                     |
|                                                                              |
|  9. ASSUMPTIONS ARE HYPOTHESES                                               |
|     Every interpretive decision logged as hypothesis with ID.                |
|     ENFORCEMENT: ASSUMPTIONS_DECLARED table mandatory before extraction.     |
|                                                                              |
| 10. CHECKLISTS ARE MANDATORY                                                 |
|     Every phase ends with completed checklist.                               |
|     ENFORCEMENT: Missing checklist = gate LOCKED.                            |
|                                                                              |
+------------------------------------------------------------------------------+
```

---

## FEAR DETECTION (automatic)

**Do not ask the user about fear analysis. Detect automatically from language.**

If the user's decision description contains:
- "afraid", "worried", "concerned", "what if it fails"
- "blocked", "I can't decide", "impossible", "paralysis"
- "risk", "I'll lose", "failure", "everyone says it's bad"

**→ Enable `fear_analysis = on`**

This adds:
- Step 0: E008, E011, E012; E009 (if "impossible"); E013
- Step 4: E010, E014, E008 revisit
- Report: Section 8 (Fear Resolution)

**If no fear signals → `fear_analysis = off`**

---

## BINDING GATES REGISTRY

```
GATE_00: KNOWLEDGE AUDIT EXIT
  CONDITIONS:
  □ Decision framed (one sentence)           — CRITICAL
  □ Stakes assessed (HIGH/MEDIUM/LOW)        — REQUIRED
  □ Knowledge inventory complete             — CRITICAL
  □ Research queue generated                 — REQUIRED
  □ ASSUMPTIONS_DECLARED logged              — CRITICAL
  □ Post-phase checklist PASSED              — CRITICAL
  UNLOCK: All CRITICAL items PASS → proceed to Step 1

GATE_01: RESEARCH EXIT
  CONDITIONS:
  □ Research queue executed by priority       — CRITICAL
  □ Findings recorded with sources           — CRITICAL
  □ Knowledge map updated                    — REQUIRED
  □ Counter-checks on key findings           — REQUIRED
  □ Post-phase checklist PASSED              — CRITICAL
  UNLOCK: All CRITICAL items PASS → proceed to Step 2

GATE_02: MAP EXIT
  CONDITIONS:
  □ Dimensions discovered (min per depth)    — CRITICAL
  □ Options enumerated (min per depth)       — CRITICAL
  □ Constraints mapped                       — REQUIRED
  □ Morphological box built                  — CRITICAL
  □ Post-phase checklist PASSED              — CRITICAL
  UNLOCK: All CRITICAL items PASS → proceed to Step 3

GATE_03: DEEPEN EXIT
  CONDITIONS:
  □ Consequences analyzed per option          — CRITICAL
  □ Each consequence tagged VERIFIED/ASSUMED  — CRITICAL
  □ Reversibility assessed                   — REQUIRED
  □ Dependencies mapped                      — REQUIRED
  □ Counter-checks on key consequences       — REQUIRED
  □ Post-phase checklist PASSED              — CRITICAL
  UNLOCK: All CRITICAL items PASS → proceed to Step 4

GATE_04: CHALLENGE EXIT
  CONDITIONS:
  □ Key beliefs falsification-tested         — CRITICAL
  □ Premortem completed for top options      — CRITICAL
  □ Assumption stress test done              — REQUIRED
  □ Bias checklist completed                 — REQUIRED (standard/deep)
  □ Counter-checks on challenge findings     — REQUIRED
  □ Post-phase checklist PASSED              — CRITICAL
  UNLOCK: All CRITICAL items PASS → proceed to Step 5

GATE_05: SYNTHESIZE EXIT
  CONDITIONS:
  □ Minimal assertions produced              — CRITICAL
  □ Strategic clusters identified            — CRITICAL
  □ Decision sequence defined                — REQUIRED
  □ Readiness assessed                       — REQUIRED
  □ Post-phase checklist PASSED              — CRITICAL
  UNLOCK: All CRITICAL items PASS → proceed to Step 6

GATE_06: OUTPUT EXIT
  CONDITIONS:
  □ All report sections filled               — CRITICAL
  □ Coverage score calculated                — CRITICAL
  □ Quality gate checked                     — CRITICAL
  □ Process log complete                     — REQUIRED
  □ All SCOPE_REDUCTION_DECLARATIONs listed  — CRITICAL
  □ Post-phase checklist PASSED              — CRITICAL
  UNLOCK: Report is final deliverable
```

---

## STEP SEQUENCE

Execute based on depth. Load one step file at a time.

```
Phase 0: KNOWLEDGE AUDIT                             [All Depths]
  Step 0   steps/step-00-knowledge-audit.md
           ASSUMPTIONS_DECLARED → EXTRACT knowledge → VERIFY inventory
           → RENDER knowledge map. Display invocation dialog.
           GATE_00 at exit.

Phase 1: RESEARCH                                    [All Depths]
  Step 1   steps/step-01-research.md
           ASSUMPTIONS_DECLARED → EXTRACT research findings → VERIFY sources
           → RENDER research summary. Execute queue by priority.
           GATE_01 at exit.

Phase 2: MAP (Divergent)                             [All Depths]
  Step 2   steps/step-02-map.md
           ASSUMPTIONS_DECLARED → EXTRACT dimensions/options → VERIFY independence
           → RENDER morphological box. M001, M002, M003.
           GATE_02 at exit.

Phase 3: DEEPEN                                      [All Depths]
  Step 3   steps/step-03-deepen.md
           ASSUMPTIONS_DECLARED → EXTRACT consequences → VERIFY each
           → RENDER consequence map. E002, E004, E005, M011, M012, M013.
           GATE_03 at exit.

Phase 4: CHALLENGE (Adversarial)                     [All Depths]
  Step 4   steps/step-04-challenge.md
           ASSUMPTIONS_DECLARED → EXTRACT challenges → VERIFY findings
           → RENDER challenge results. E006, M021, M022, M023, Bias check.
           Fear resolution if fear_analysis=on.
           GATE_04 at exit.

Phase 5: SYNTHESIZE                                  [All Depths]
  Step 5   steps/step-05-synthesize.md
           ASSUMPTIONS_DECLARED → EXTRACT patterns → VERIFY clusters
           → RENDER synthesis. E003, E007, clustering, sequencing.
           GATE_05 at exit.

Phase 6: OUTPUT                                      [All Depths]
  Step 6   steps/step-06-output.md
           ASSUMPTIONS_DECLARED → EXTRACT all phase outputs → VERIFY coverage
           → RENDER report. Template, scoring, quality gate.
           GATE_06 at exit.
```

---

## DECISION POINTS

| After Step | Condition | Action |
|------------|-----------|--------|
| Step 0 | Research queue defined | PROCEED → Step 1 |
| Step 0 | Research queue empty | SKIP → Step 2 (requires SCOPE_REDUCTION_DECLARATION) |
| Step 0 | Frame unclear (3 attempts) | Escalate or ABORT |
| Step 1 | Critical unknowns addressed | PROCEED → Step 2 |
| Step 1 | More research needed, iterations remaining | STAY in Step 1 |
| Step 1 | Max iterations reached | PROCEED → Step 2 (with flags) |
| Step 2 | New unknowns found, iterations remaining | RETURN → Step 1 |
| Step 2 | Map complete | PROCEED → Step 3 |
| Step 3 | Consequences unverified, iterations remaining | RETURN → Step 1 |
| Step 3 | Consequences verified | PROCEED → Step 4 |
| Step 4 | Challenge passed | PROCEED → Step 5 |
| Step 4 | Fundamental reframe needed | RETURN → Step 0 (rare) |
| Step 5 | Always | PROCEED → Step 6 |
| Step 6 | Report complete | Workflow complete |

---

## SCORING QUICK REFERENCE

```
Dimension discovered: +1.5 (cap 8)    Consequence VERIFIED: +2.0
Option enumerated: +0.5 (cap 20)      Consequence ASSUMED: +0.2
Assumption tested: +1.5               Assumption falsified: +2.0
Unknown Unknown surfaced: +1.5        Boundary identified: +1.0
Premortem cause: +0.5                 Black swan: +0.5
Bias checked: +0.3                    Belief stress tested: +0.5

V3.0 ENFORCEMENT BONUSES:
Gate passed without SCOPE_REDUCTION: +1.0 per gate
Counter-check performed: +0.5
ASSUMED item later VERIFIED: +1.5 (upgrade bonus)

Thresholds:
  quick:    C>=15 COMPREHENSIVE | C>=10 ADEQUATE | C>=5 PARTIAL
  standard: C>=35 COMPREHENSIVE | C>=22 ADEQUATE | C>=12 PARTIAL
  deep:     C>=50 COMPREHENSIVE | C>=35 ADEQUATE | C>=20 PARTIAL

Quality gates MUST pass — failing caps level regardless of score.
When fear_analysis=on, thresholds increase by +5.
```

---

## PROCESS LOG FORMAT

```
Every execution MUST maintain a process log:

PROCESS_LOG:
  depth: [quick|standard|deep]
  fear_analysis: [on|off]
  started: [timestamp]

  phases:
    - phase: 0
      assumptions_declared: [count]
      evr_sequence: [EXTRACT→VERIFY→RENDER or violation noted]
      counter_checks: [count]
      checklist_status: [PASS|FAIL]
      gate_status: [OPEN|LOCKED]
      scope_reductions: [count, details]
      key_artifacts: [list]

    - phase: 1
      [same structure]
    ...

  total_scope_reductions: [count]
  total_counter_checks: [count]
  final_coverage_score: [N]
  final_level: [COMPREHENSIVE|ADEQUATE|PARTIAL|INSUFFICIENT]
```

---

## For detailed documentation see: [reference.md](./reference.md)

Topics covered in reference.md:
- When to use / When not to use Deep Explore
- Core philosophy and principles
- Invocation dialog (depth selection)
- Depth levels (detailed)
- Foundational methods (E001-E014)
- Process methods (M001-M054)
- Execution flow diagram
- Detailed execution path
- Scoring system (full tables)
- Quality gates (full tables)
- Fear analysis scoring
- Enforcement architecture details
- Directory structure
- Method naming convention
- Version history

---

## VERSION HISTORY

- **V3.0** — Enforcement architecture: binding gates, EVR sequence, ASSUMPTIONS_DECLARED, post-phase checklists, counter-checks, SCOPE_REDUCTION protocol, COMPLETENESS > TOKEN_ECONOMY priority. Based on Deep Explore V2.2.
- **V2.2** — Self-contained execution: lean workflow.md + reference.md, invocation dialog in step-00
- **V2.1.1** — Quality over quantity scoring, verification emphasis
