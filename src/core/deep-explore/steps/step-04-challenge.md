# Step 04: Challenge (Adversarial)

## Purpose

Stress-test the exploration for blind spots and weak thinking.

**Time:** 15-20 min

**Inputs:** Option Map, Consequence Map from Steps 2-3

**Outputs:** Challenged map with strengthened/weakened items

**Enforcement layers active:** ASSUMPTIONS_DECLARED, EVR, COUNTER-CHECKS, POST-PHASE CHECKLIST, GATE_04

---

## 04.0 ASSUMPTIONS_DECLARED (MANDATORY)

**Execute BEFORE any challenge activity.**

```
ASSUMPTIONS_DECLARED for Phase 4:
┌──────┬──────────────────────────────────────┬──────────────┬────────────┬──────────────────────────────┐
│ ID   │ Assumption                           │ Type         │ Confidence │ Falsification Criterion      │
├──────┼──────────────────────────────────────┼──────────────┼────────────┼──────────────────────────────┤
│ H-4xx│ "[assumed completeness of challenge]"│ INTERPRETIVE │ HIGH/MED/  │ "[challenge missed angle]"   │
│ H-4xx│ "[assumed bias awareness]"           │ CONTEXTUAL   │ LOW        │ "[blind spot found]"         │
│ H-4xx│ "[assumed failure modes]"            │ DOMAIN       │            │ "[different failure mode]"   │
└──────┴──────────────────────────────────────┴──────────────┴────────────┴──────────────────────────────┘
```

---

## 04.1 EXTRACT: Falsification Attempts

Load method: `data/method-procedures/E006_Falsification.md`

For each key belief/assumption — extract raw challenge data:

```
BELIEF: "[statement]"

RAW FALSIFICATION DATA:
• What would show this is FALSE? [description]
• Evidence searched: [what was looked for]
• Evidence found: [what was found]
• Contradicting sources: [list]

[EXTRACT_COMPLETE for falsification]
```

## 04.2 EXTRACT: Premortem

Load method: `data/method-procedures/M021_Premortem.md`

**Note:** M021 uses the UNIFIED FAILURE TAXONOMY (shared with E008 from Step 0).

For top 2-3 options, imagine failure:

```
OPTION: [name]

SCENARIO: "It's 12 months later. We chose this. It failed badly."

RAW FAILURE CAUSES:
1. [cause] — initial type classification: [STRUCTURAL/OPERATIONAL/EXTERNAL/COGNITIVE]
2. [cause] — initial type classification: [type]
3. [cause] — initial type classification: [type]

UNIFIED TYPE KEY (same as E008):
• STRUCTURAL = Hard limits → Contingency or reject option
• OPERATIONAL = Constraints → Mitigate before proceeding
• EXTERNAL = Outside control → Monitor + contingency plan
• COGNITIVE = Assumptions → Verify or dismiss

[EXTRACT_COMPLETE for premortem]
```

## 04.3 EXTRACT: Black Swan Hunt

Load method: `data/method-procedures/M022_Black_Swan_Hunt.md`

```
RAW BLACK SWAN INVENTORY:

POSITIVE (upside):
• [event] - would enable: [what]

NEGATIVE (downside):
• [event] - would destroy: [what]

[EXTRACT_COMPLETE for black swans]
```

## 04.4 EXTRACT: Assumption Stress Test

Load method: `data/method-procedures/M023_Assumption_Stress_Test.md`

```
For each key assumption:

ASSUMPTION: "[statement]"
RAW STRESS DATA:
• What would disprove this? [description]
• Who would disagree? [stakeholder]
• What if 50% wrong? [impact]

[EXTRACT_COMPLETE for stress test]
```

---

## 04.5 VERIFY: Challenge Results

```
CHALLENGE VERIFICATION LOG:

FALSIFICATION RESULTS:
┌────┬──────────────────────────┬──────────────┬──────────────────────────┐
│ #  │ Belief                   │ Result       │ Evidence                 │
├────┼──────────────────────────┼──────────────┼──────────────────────────┤
│ 1  │ "[belief]"               │ FALSIFIED    │ evidence: [what found]   │
│    │                          │              │ → REMOVE or MODIFY       │
│ 2  │ "[belief]"               │ SURVIVED     │ attempts: [what tried]   │
│    │                          │              │ → STRENGTHEN confidence  │
│ 3  │ "[belief]"               │ UNTESTABLE   │ reason: [why]            │
│    │                          │              │ → FLAG as assumption     │
└────┴──────────────────────────┴──────────────┴──────────────────────────┘

PREMORTEM RESULTS:
┌────┬──────────────────────┬──────────┬──────────────┬──────────────────┐
│ #  │ Cause                │ Type     │ Preventable? │ Action           │
├────┼──────────────────────┼──────────┼──────────────┼──────────────────┤
│ 1  │ [cause]              │ STRUCT.  │ NO           │ Contingency      │
│ 2  │ [cause]              │ OPER.    │ YES          │ Mitigate         │
│ 3  │ [cause]              │ EXTERNAL │ PARTIAL      │ Monitor          │
│ 4  │ [cause]              │ COGN.    │ YES          │ Verify first     │
└────┴──────────────────────┴──────────┴──────────────┴──────────────────┘

SURVIVABILITY per option:
• Worst case: [description]
• Recoverable? [Y/N]
• Reversibility: [HIGH/MED/LOW/IRREVERSIBLE]
• VERDICT: [PROCEED / PROCEED WITH CAUTION / RECONSIDER / REJECT]

ASSUMPTION STRESS RESULTS:
┌────┬──────────────────────────┬──────────┬──────────────────────────┐
│ #  │ Assumption               │ Result   │ Impact                   │
├────┼──────────────────────────┼──────────┼──────────────────────────┤
│ 1  │ "[assumption]"           │ HOLDS    │ survives challenge       │
│ 2  │ "[assumption]"           │ WEAKENED │ reduce confidence to MED │
│ 3  │ "[assumption]"           │ BROKEN   │ update map — [how]       │
└────┴──────────────────────────┴──────────┴──────────────────────────┘

[VERIFY_COMPLETE]
```

**★ KEY_CLAIM: "Challenge was genuine — not a rubber stamp."**

**COUNTER-CHECKS (minimum per depth: quick=1, standard=2, deep=3):**
```
COUNTER-CHECK #N:
  claim: "The challenge phase was thorough — no major angle was missed"
  disproof: "A critical failure mode, bias, or assumption was not examined"
  search_attempt: "[check: regulatory risk, team dynamics, market shift,
                    technology obsolescence, second-order effects]"
  result: CONFIRMED | WEAKENED | REFUTED
  action: [if WEAKENED: add missing challenge area]
```

---

## 04.6 VERIFY: Bias Check

Run through comprehensive checklist. For each bias detected, apply remediation.

```
┌──────────────────────────────────────────────────────────────────────────┐
│  COGNITIVE BIAS CHECKLIST                                                 │
├──────────────────────────────────────────────────────────────────────────┤
│                                                                           │
│  INFORMATION PROCESSING BIASES                                            │
│  □ CONFIRMATION BIAS                                                      │
│    Detection: "Did I seek out contradicting evidence?"                    │
│    Remediation: Force-search for 3 sources that disagree                 │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ AVAILABILITY BIAS                                                      │
│    Detection: "Am I overweighting recent or vivid examples?"             │
│    Remediation: Check base rates, find statistical evidence              │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ ANCHORING                                                              │
│    Detection: "Did the first number/option overly influence me?"         │
│    Remediation: Generate estimate BEFORE seeing anchors                  │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ FRAMING EFFECT                                                         │
│    Detection: "Would I decide differently if framed as loss vs gain?"    │
│    Remediation: Reframe each option in opposite terms                    │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  DECISION-MAKING BIASES                                                   │
│  □ SUNK COST FALLACY                                                      │
│    Detection: "Am I continuing because of past investment?"              │
│    Remediation: Imagine starting fresh today — same choice?              │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ STATUS QUO BIAS                                                        │
│    Detection: "Am I favoring 'do nothing' without justification?"        │
│    Remediation: List costs of NOT changing                               │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ LOSS AVERSION                                                          │
│    Detection: "Am I overweighting potential losses vs gains?"            │
│    Remediation: Calculate expected value, not worst case                 │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ PLANNING FALLACY                                                       │
│    Detection: "Am I underestimating time/cost/difficulty?"               │
│    Remediation: Use reference class forecasting                          │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  SOCIAL & EMOTIONAL BIASES                                                │
│  □ OPTIMISM BIAS                                                          │
│    Detection: "Am I assuming things will go better than typical?"        │
│    Remediation: "What if I'm wrong?" and plan for it                     │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ OVERCONFIDENCE                                                         │
│    Detection: "How certain am I, and is that justified?"                 │
│    Remediation: Track past predictions, calibrate                        │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ AUTHORITY BIAS                                                         │
│    Detection: "Am I believing X because expert said so?"                 │
│    Remediation: Check expert's track record, seek opposing experts       │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ GROUPTHINK                                                             │
│    Detection: "Is everyone agreeing too easily?"                         │
│    Remediation: Assign devil's advocate, seek outside opinion            │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
│  □ SURVIVORSHIP BIAS                                                      │
│    Detection: "Am I only seeing successes, not failures?"                │
│    Remediation: Actively search for failure cases                        │
│    Impact on map: [ ] None [ ] Minor [ ] Significant [ ] Critical        │
│                                                                           │
└──────────────────────────────────────────────────────────────────────────┘

BIAS CHECK SUMMARY:
┌────────────────────────┬──────────┬────────────────────────────────────┐
│ Bias Detected          │ Impact   │ Remediation Applied                │
├────────────────────────┼──────────┼────────────────────────────────────┤
│                        │          │                                    │
└────────────────────────┴──────────┴────────────────────────────────────┘
TOTAL BIASES CHECKED: [count]
SIGNIFICANT/CRITICAL: [count] → Must update map
```

---

## 04.7 Fear Resolution (when fear_analysis=on)

### Design Minimal Tests

Load method: `data/method-procedures/E010_Cognitive_MVP.md`

```
FOR EACH UNRESOLVED FEAR:

FEAR: "[what user is afraid of]"
STATUS: [still uncertain after research]

MINIMAL TEST:
"What's the SMALLEST thing I can do to learn if this fear is valid?"

PROBE DESIGN:
• Action: [minimal action]
• Effort: [LOW/MED/HIGH]
• Learning if succeeds: ___
• Learning if fails: ___

→ Failure becomes DATA, not defeat
```

### Growth Assessment

Load method: `data/method-procedures/E014_Growth_Test.md`

```
FOR EACH MAJOR OPTION:

GROWTH TEST:
┌────────────────────────────┬────────┬────────────────────┐
│ Growth Type                │ Y/N    │ What specifically   │
├────────────────────────────┼────────┼────────────────────┤
│ New learning forced        │        │                     │
│ New skill developed        │        │                     │
│ New experience gained      │        │                     │
│ Network/access expanded    │        │                     │
│ Thinking changed           │        │                     │
└────────────────────────────┴────────┴────────────────────┘

VERDICT:
[ ] HIGH GROWTH - worth doing even if "fails"
[ ] GAMBLING - reconsider
[ ] NEEDS REDESIGN - add learning component
```

### Fear Map Resolution

```
FEAR MAP UPDATE:
┌────────────────────────────────┬────────────────────────────────┐
│ Fear from Step 0               │ Resolution Status              │
├────────────────────────────────┼────────────────────────────────┤
│ [fear 1]                       │ RESOLVED/ADDRESSED/REMAINS     │
│ [fear 2]                       │ RESOLVED/ADDRESSED/REMAINS     │
└────────────────────────────────┴────────────────────────────────┘

RESOLUTION KEY:
• RESOLVED = Evidence shows fear was unfounded
• ADDRESSED = Mitigation plan exists
• REMAINS = True risk, accepted or pivoted
```

---

## 04.8 RENDER: Challenge Results

```
╔═══════════════════════════════════════════════════════════════╗
║  CHALLENGE RESULTS                                             ║
╠═══════════════════════════════════════════════════════════════╣
║                                                                ║
║  Beliefs Tested:        [count]                                ║
║  • Falsified:           [count]                                ║
║  • Survived:            [count]                                ║
║  • Modified:            [count]                                ║
║                                                                ║
║  Premortem Causes:      [count]                                ║
║  Black Swans Found:     [count]                                ║
║  Assumptions Stressed:  [count]                                ║
║  Biases Detected:       [count]                                ║
║  Counter-checks Done:   [count]                                ║
║                                                                ║
║  MAP UPDATES:                                                   ║
║  • [what changed based on challenge]                           ║
║                                                                ║
╚═══════════════════════════════════════════════════════════════╝

[RENDER_COMPLETE]
```

---

## POST-PHASE CHECKLIST (MANDATORY)

```
PHASE_04 COMPLETION CHECKLIST:

□ ASSUMPTIONS_DECLARED logged?             [count: ___]
□ EVR sequence respected?                  [Y/N — EXTRACT→VERIFY→RENDER]
□ Falsification attempted on key beliefs?  [Y/N, count: ___]
□ Premortem completed for top options?     [Y/N, count: ___]
□ Black swan hunt performed?               [Y/N]
□ Assumptions stress-tested?               [Y/N, count: ___]
□ Bias checklist completed?                [Y/N, biases checked: ___]
□ Counter-checks performed?               [count: ___ (min: ___)]
□ Map updated with challenge findings?     [Y/N]
□ Fear resolution done (if on)?            [Y/N or N/A]

CHECKLIST_STATUS: PASS | FAIL
IF FAIL: Fix before proceeding.
```

---

## GATE_04: CHALLENGE EXIT

```
GATE_04 BINDING CHECK:

□ Key beliefs falsification-tested         — [PASS/FAIL] — CRITICAL
□ Premortem completed for top options      — [PASS/FAIL] — CRITICAL
□ Assumption stress test done              — [PASS/FAIL] — REQUIRED
□ Bias checklist completed                 — [PASS/FAIL] — REQUIRED (standard/deep)
□ Counter-checks on challenge findings     — [PASS/FAIL] — REQUIRED
□ Post-phase checklist PASSED              — [PASS/FAIL] — CRITICAL

GATE_04 STATUS: OPEN | LOCKED
```

---

## Transition

- **If GATE_04 = OPEN and challenge passed** → Proceed to Step 5
- **If challenge reveals FUNDAMENTAL reframe needed** → Return to Step 0 (rare)
- **If challenge reveals ALL options fatally flawed** → ABORT exploration

**Note:** Challenge normally leads forward. Backward transition requires:
- Discovery that core problem was misunderstood
- Evidence that continuing would waste effort
- User agreement to restart
