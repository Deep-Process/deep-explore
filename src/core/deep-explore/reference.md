# Deep Explore V3.0 — Reference Documentation

> **This is reference documentation.** For execution, see [workflow.md](./workflow.md).

---

## WHEN TO USE DEEP EXPLORE

**Use Deep Explore when you need to:**
- Make a decision with multiple options and unclear consequences
- Understand a complex problem space before committing
- Explore strategic choices (career, business, technology)
- Reduce uncertainty through structured analysis

**Do NOT use Deep Explore when:**
- You need to verify an existing artifact → use **Deep Verify**
- You need to assess risks of a known plan → use **Deep Risk**
- The decision is trivial or already made
- You need to execute, not explore

**Related Processes:**
| Process | Purpose | Output |
|---------|---------|--------|
| **Deep Explore** | Explore decision space | Understanding + Option Map |
| **Deep Verify** | Verify artifact correctness | Verification Report |
| **Deep Risk** | Assess risks of a plan | Risk Assessment |

---

## CORE PHILOSOPHY

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  DEEP EXPLORE V3.0 = KNOWLEDGE EXPANSION + UNCERTAINTY MAPPING +            │
│                       EXPLORATION + ENFORCEMENT                             │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  INPUT:   Decision problem, strategic question, complex choice              │
│  OUTPUT:  UNDERSTANDING (not just a map)                                    │
│           • What you learned                                                │
│           • What you still don't know                                       │
│           • Options with VERIFIED vs ASSUMED consequences                   │
│           • Decision readiness assessment                                   │
│                                                                              │
│  PRIORITIES (binding):                                                       │
│    1. COMPLETENESS > 2. DEPTH > 3. ACCURACY > 4. TOKEN_ECONOMY             │
│                                                                              │
│  CORE PRINCIPLE: EXPAND KNOWLEDGE BEFORE MAPPING OPTIONS                    │
│                  You cannot map territory you haven't explored              │
│                                                                              │
│  V3.0 ADDITION: Every instruction has an ENFORCEMENT MECHANISM.             │
│                  Intentions are replaced by executable constraints.          │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

---

## INVOCATION DIALOG

**When the user wants to explore a decision, display this dialog:**

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

---

## DEPTH LEVELS — Detailed

### QUICK (depth = quick)
```
STEPS:           0 → 1 → 2 → 3 → 4 → 5 → 6  (all steps, abbreviated)
MAX ITERATIONS:  1 (no feedback loops)
RESEARCH:        Top 2-3 items from queue
DIMENSIONS:      3 minimum
OPTIONS:         Top 2 options analyzed deeply
CHALLENGE:       Only key assumptions, basic bias check
COUNTER-CHECKS:  1 per phase minimum
COVERAGE TARGET: C ≥ 15 = COMPREHENSIVE
```

### STANDARD (depth = standard)
```
STEPS:           0 → 1 → 2 → 3 → 4 → 5 → 6  (full execution)
MAX ITERATIONS:  3 (feedback loops allowed)
RESEARCH:        All P1 and P2 items
DIMENSIONS:      4-6 dimensions
OPTIONS:         Top 3-5 options analyzed
CHALLENGE:       Full procedure: premortem, black swan, bias check
COUNTER-CHECKS:  2 per phase minimum
COVERAGE TARGET: C ≥ 35 = COMPREHENSIVE
```

### DEEP (depth = deep)
```
STEPS:           0 → 1 → 2 → 3 → 4 → 5 → 6  (full + deepened)
MAX ITERATIONS:  Unlimited (until resolved or user decision)
RESEARCH:        All items + exploratory research
DIMENSIONS:      Exhaustive discovery
OPTIONS:         All viable options
CHALLENGE:       Multiple rounds, devil's advocate, external validation
COUNTER-CHECKS:  3 per phase minimum
COVERAGE TARGET: C ≥ 50 = COMPREHENSIVE
```

---

## FEAR DETECTION

**Do not ask the user about fear analysis. Detect automatically from language.**

If the user's decision description contains:
- "I'm afraid", "I'm worried", "I'm concerned"
- "what if it doesn't work", "what if it fails"
- "blocked", "I don't know how to start", "impossible"
- "risk", "I'll lose", "failure"
- "paralysis", "I can't decide"
- "everyone says it's bad", "nobody does this"

**→ Enable `fear_analysis = on`**

This means:
- In Step 0: add Fear Inventory (E008), Control Analysis (E011), Blocker Analysis (E012)
- In Step 4: add Fear Resolution, Minimal Tests (E010), Growth Assessment (E014)
- In report: add Section 8 (Fear Resolution)

---

## FOUNDATIONAL METHODS

### Epistemological Core (E001-E007) — always used

| ID | Method | Purpose |
|----|--------|---------|
| E001 | Abductive Reasoning | Generate hypotheses from observations |
| E002 | Counterfactual Thinking | Identify causal factors and leverage points |
| E003 | Minimal Assertions | Compress knowledge to actionable principles |
| E004 | Boundary Analysis | Find limits where things stop working |
| E005 | Causal Models | Map influence relationships |
| E006 | Falsification | Test beliefs by trying to disprove them |
| E007 | Information Questions | Identify highest-value questions |

### Fear-Based Methods (E008-E014) — when fear_analysis = on

| ID | Method | Purpose |
|----|--------|---------|
| E008 | Failure Reason Exploration | Transform fear into structured risk map |
| E009 | Reverse Abduction | Discover paths by assuming success |
| E010 | Cognitive MVP | Find smallest action that teaches something |
| E011 | Control vs Influence Analysis | Separate controllable from uncontrollable |
| E012 | Fundamental Block Analysis | Find true "walls" vs false walls |
| E013 | Contrast Exploration | Learn from others' successes and failures |
| E014 | Growth Test | Filter decisions by whether they develop you |

---

## PROCESS METHODS

### MAP Phase (Step 2)
| ID | Method | Purpose |
|----|--------|---------|
| M001 | Dimension Discovery | Identify axes of choice |
| M002 | Option Enumeration | List ALL options per dimension |
| M003 | Constraint Mapping | Hard/soft constraints |

### ILLUMINATE Phase (Step 3)
| ID | Method | Purpose |
|----|--------|---------|
| M011 | Consequence Analysis | Map GAINS/COSTS/OPENS/CLOSES |
| M012 | Reversibility Check | Can this be undone? |
| M013 | Dependency Analysis | What must be decided first? |
| M014 | Stakeholder Impact | Who is affected? |
| M015 | Future Optionality | Preserve vs foreclose possibilities |
| M016 | Integration Points | Hidden complexity at touchpoints |
| M017 | Resource Trade-off | Hidden costs and resource needs |
| M018 | Opportunity Cost | What you give up |

### CHALLENGE Phase (Step 4)
| ID | Method | Purpose |
|----|--------|---------|
| M021 | Premortem | Imagine failure, trace causes |
| M022 | Black Swan Hunt | Low-probability high-impact events |
| M023 | Assumption Stress Test | Break assumptions one by one |
| M024 | Regret Minimization | What would future you regret not considering? |
| M025 | Devil's Advocate | Argue against favored option |
| M026 | Red Team Options | How would competitor exploit this? |

### SYNTHESIZE Phase (Step 5)
| ID | Method | Purpose |
|----|--------|---------|
| M031 | Option Clustering | Group similar strategies |
| M032 | Decision Sequencing | What first, what can wait |
| M033 | Real Options Identification | Delay while preserving optionality |
| M034 | Information Value Analysis | Most uncertainty-reducing information |
| M035 | Decision Criteria Extraction | Surface implicit criteria |
| M036 | Path Dependency Mapping | Early choices constrain later ones |

### CONVERGE Phase (Step 6)
| ID | Method | Purpose |
|----|--------|---------|
| M041 | Trade-off Presentation | Present without recommendation |
| M042 | Uncertainty Documentation | What remains unknown |
| M043 | Experiment Design | Small experiments before committing |
| M044 | Decision Record | Context, rationale, review triggers |

### META (Any Step)
| ID | Method | Purpose |
|----|--------|---------|
| M051 | Archetype Check | Known decision traps |
| M052 | Coverage Assessment | Is exploration sufficient? |
| M053 | Abstraction Level Check | Prevent scope creep |
| M054 | Cynefin Reassessment | Re-evaluate problem type |

---

## EXECUTION FLOW

```
                    ┌──────────────────────────────────────────┐
                    │          FEEDBACK LOOPS                  │
                    │     (only for standard and deep)         │
                    ▼                                          │
┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐     │
│ STEP 0  │───►│ STEP 1  │───►│ STEP 2  │───►│ STEP 3  │─────┤
│ AUDIT   │    │ RESEARCH│    │   MAP   │    │ DEEPEN  │     │
│ GATE_00 │    │ GATE_01 │    │ GATE_02 │    │ GATE_03 │     │
└─────────┘    └────┬────┘    └────┬────┘    └────┬────┘     │
                    │              │              │           │
                    └──────────────┴──────────────┘           │
                                         │                   │
                                         ▼                   │
                    ┌─────────┐    ┌─────────┐    ┌─────────┐
                    │ STEP 4  │───►│ STEP 5  │───►│ STEP 6  │
                    │CHALLENGE│    │SYNTHESIZE    │ OUTPUT  │
                    │ GATE_04 │    │ GATE_05 │    │ GATE_06 │
                    └─────────┘    └─────────┘    └─────────┘

Each step follows: ASSUMPTIONS → EXTRACT → VERIFY → RENDER → CHECKLIST → GATE
```

---

## ENFORCEMENT ARCHITECTURE SUMMARY

| Layer | Purpose | Trigger | Violation Response |
|-------|---------|---------|-------------------|
| ASSUMPTIONS_DECLARED | Log interpretive decisions | Before extraction | HALT if empty |
| EVR Sequence | Prevent premature rendering | During phase | HALT + return |
| Counter-checks | Challenge key claims | After key claims | Gate LOCKED |
| Post-phase Checklist | Verify completeness | After phase | Gate LOCKED |
| Binding Gate | Control phase transitions | At phase exit | Cannot proceed |
| SCOPE_REDUCTION | Formal skip declaration | When skipping | Must be logged |

---

## SCORING SYSTEM (V3.0)

See `data/coverage-scoring.yaml` for full scoring rules.

### Coverage Thresholds (by depth)

| Score | quick | standard | deep |
|-------|-------|----------|------|
| COMPREHENSIVE | C >= 15 | C >= 35 | C >= 50 |
| ADEQUATE | C >= 10 | C >= 22 | C >= 35 |
| PARTIAL | C >= 5 | C >= 12 | C >= 20 |
| INSUFFICIENT | C < 5 | C < 12 | C < 20 |

### Quality Gates (Minimum Requirements)

| Requirement | quick | standard | deep |
|-------------|-------|----------|------|
| Dimensions (min) | 3 | 4 | 5 |
| Options (min) | 6 | 12 | 15 |
| Verified consequences (min) | 2 | 5 | 10 |
| Assumptions tested (min) | 1 | 3 | 5 |
| Verification ratio (min) | - | 30% | 50% |
| Premortem causes (min) | - | 3 | 5 |
| Biases checked (min) | - | - | 5 |
| Counter-checks total (min) | 6 | 12 | 18 |
| Gates passed clean (min) | 5 | 6 | 7 |

---

## DIRECTORY STRUCTURE

```
deep-explore-v2/
├── workflow.md                           ← Execution program (with enforcement)
├── reference.md                          ← YOU ARE HERE (reference docs)
├── process.yaml                          ← Framework registration
├── methods.csv                           ← Method definitions (reference)
├── steps/
│   ├── step-00-knowledge-audit.md        ← Knowledge audit + invocation
│   ├── step-01-research.md               ← Research phase
│   ├── step-02-map.md                    ← Morphological mapping
│   ├── step-03-deepen.md                 ← Consequence analysis
│   ├── step-04-challenge.md              ← Adversarial challenge
│   ├── step-05-synthesize.md             ← Synthesis
│   └── step-06-output.md                 ← Report generation
└── data/
    ├── method-procedures/                ← Method procedure files
    │   ├── E001_Abductive_Reasoning.md   (shared with deep-explore v2.2)
    │   ├── ...
    │   └── M023_Assumption_Stress_Test.md
    ├── coverage-scoring.yaml             ← Scoring rules V3.0
    ├── exploration-report-template.md    ← Output template V3.0
    └── research-methods.md              ← Research guidance
```

---

## VERSION HISTORY

- **V3.0** — Enforcement architecture: binding gates, EVR sequence, ASSUMPTIONS_DECLARED, post-phase checklists, counter-checks, SCOPE_REDUCTION protocol. COMPLETENESS > TOKEN_ECONOMY priority. Execution-focused (HOW/WHEN, not WHAT).
- **V2.2** — Self-contained execution: lean workflow.md + reference.md, invocation dialog in step-00
- **V2.1.1** — Quality over quantity scoring, verification emphasis, fear analysis integration
- **V2.0** — Knowledge-first approach, morphological analysis, structured fear resolution
