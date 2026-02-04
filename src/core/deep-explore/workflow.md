# Deep Explore V2.1.1 — Knowledge-First Decision Exploration

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

## INVOCATION

**When the user wants to explore a decision, ALWAYS start with this dialog:**

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                      DEEP EXPLORE                                          ║
║                      Decision Space Exploration                            ║
╠═══════════════════════════════════════════════════════════════════════════╣
║                                                                            ║
║  Before we begin, choose the exploration depth:                           ║
║                                                                            ║
║  ┌─────────────────────────────────────────────────────────────────────┐  ║
║  │  [1] QUICK  (10-20 min)                                             │  ║
║  │                                                                      │  ║
║  │  What you'll get:                                                    │  ║
║  │  • Basic option map (3 dimensions minimum)                          │  ║
║  │  • Key consequences for top 2 options                               │  ║
║  │  • Quick decision readiness assessment                              │  ║
║  │  • Most important risks                                              │  ║
║  │                                                                      │  ║
║  │  When to use:                                                        │  ║
║  │  → Urgent decision, limited time                                    │  ║
║  │  → Initial orientation before deeper analysis                       │  ║
║  │  → Low-stakes decision                                               │  ║
║  └─────────────────────────────────────────────────────────────────────┘  ║
║                                                                            ║
║  ┌─────────────────────────────────────────────────────────────────────┐  ║
║  │  [2] STANDARD  (45-90 min)                                          │  ║
║  │                                                                      │  ║
║  │  What you'll get:                                                    │  ║
║  │  • Full option map (4-6 dimensions)                                 │  ║
║  │  • Consequences for top 3-5 options (VERIFIED vs ASSUMED)           │  ║
║  │  • Challenge: premortem, bias check, assumption stress test         │  ║
║  │  • Strategic option clusters                                         │  ║
║  │  • Full report with decision sequence                               │  ║
║  │                                                                      │  ║
║  │  When to use:                                                        │  ║
║  │  → Important decision requiring careful thought                     │  ║
║  │  → You need confidence before taking action                         │  ║
║  │  → Medium/high-stakes decision                                       │  ║
║  └─────────────────────────────────────────────────────────────────────┘  ║
║                                                                            ║
║  ┌─────────────────────────────────────────────────────────────────────┐  ║
║  │  [3] DEEP  (2-4 hours)                                              │  ║
║  │                                                                      │  ║
║  │  What you'll get:                                                    │  ║
║  │  • Exhaustive map of ALL options                                    │  ║
║  │  • Deep consequence analysis for every option                       │  ║
║  │  • Multiple iterations with feedback loops                          │  ║
║  │  • External research where needed                                   │  ║
║  │  • Devil's advocate, black swan hunting                             │  ║
║  │  • Full dependency and turning point analysis                       │  ║
║  │                                                                      │  ║
║  │  When to use:                                                        │  ║
║  │  → Critical, irreversible decision                                  │  ║
║  │  → Very high stakes (career, company, life)                         │  ║
║  │  → You have time and want maximum certainty                         │  ║
║  └─────────────────────────────────────────────────────────────────────┘  ║
║                                                                            ║
║  Choose: [1] / [2] / [3]                                                  ║
║                                                                            ║
╚═══════════════════════════════════════════════════════════════════════════╝
```

**After user selection:**
1. Save selected level: `depth = quick | standard | deep`
2. Scan user input for fear/concern signals (see: FEAR DETECTION)
3. Start execution from Step 0

**Note:** Time estimates (10-20 min, 45-90 min, 2-4 hours) are approximate and depend on
problem complexity and user engagement. They are heuristics, not guarantees.

---

## FEAR DETECTION (automatic)

**Do not ask the user about fear analysis. Detect automatically from language.**

If the user's decision description contains words/phrases:
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

**If no fear signals → `fear_analysis = off`** (standard exploration)

---

## CORE PHILOSOPHY

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  DEEP EXPLORE = KNOWLEDGE EXPANSION + UNCERTAINTY MAPPING + EXPLORATION     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  INPUT:   Decision problem, strategic question, complex choice              │
│  OUTPUT:  UNDERSTANDING (not just a map)                                    │
│           • What you learned                                                │
│           • What you still don't know                                       │
│           • Options with VERIFIED vs ASSUMED consequences                   │
│           • Decision readiness assessment                                   │
│                                                                              │
│  CORE PRINCIPLE: EXPAND KNOWLEDGE BEFORE MAPPING OPTIONS                    │
│                  You cannot map territory you haven't explored              │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## DEPTH LEVELS — What you execute at each level

### QUICK (depth = quick)

```
STEPS:           0 → 1 → 2 → 3 → 4 → 5 → 6  (all steps, but abbreviated)
MAX ITERATIONS:  1 (no feedback loops)
RESEARCH:        Top 2-3 items from queue
DIMENSIONS:      3 minimum
OPTIONS:         Top 2 options analyzed deeply
CHALLENGE:       Only key assumptions, basic bias check
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
COVERAGE TARGET: C ≥ 50 = COMPREHENSIVE
```

---

## FOUNDATIONAL METHODS

Deep Explore is built on these epistemological foundations:

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

## EXECUTION FLOW

```
                    ┌──────────────────────────────────────────┐
                    │          FEEDBACK LOOPS                  │
                    │     (only for standard and deep)         │
                    ▼                                          │
┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐     │
│ STEP 0  │───►│ STEP 1  │───►│ STEP 2  │───►│ STEP 3  │─────┤
│ AUDIT   │    │ RESEARCH│    │   MAP   │    │ DEEPEN  │     │
└─────────┘    └────┬────┘    └────┬────┘    └────┬────┘     │
                    │              │              │           │
                    └──────────────┴──────────────┘           │
                                         │                   │
                                         ▼                   │
                    ┌─────────┐    ┌─────────┐    ┌─────────┐
                    │ STEP 4  │───►│ STEP 5  │───►│ STEP 6  │
                    │CHALLENGE│    │SYNTHESIZE    │ OUTPUT  │
                    └─────────┘    └─────────┘    └─────────┘
```

---

## EXECUTION PATH

**After user selects the level, execute:**

```
📂 Step 0: KNOWLEDGE AUDIT
   Load: steps/step-00-knowledge-audit.md

   □ Frame the decision (one sentence)
   □ Assess stakes: LOW/MEDIUM/HIGH
   □ Inventory: Known Facts, Assumptions, Known Unknowns
   □ 📂 E001 → Surface Unknown Unknowns
   □ Prioritize research needs

   IF fear_analysis = on:
   □ 📂 E008 → Structure fears into risk map
   □ 📂 E011 → Separate actionable concerns
   □ 📂 E012 → Find true walls vs false walls
   □ 📂 E009 → Reverse from success (if "impossible")
   □ 📂 E013 → Gain context from others
   → Fears become structured research queue

   Output: Knowledge Map + Research Queue (+ Fear Map if fear_analysis=on)

   ↓ PROCEED if research queue is defined
   ↓ STAY if framing is unclear (max 3 attempts, then escalate)
   ✖ ABORT if decision should not be made (premature/wrong question/blocked)

📂 Step 1: RESEARCH
   Load: steps/step-01-research.md

   □ Execute research queue by priority
   □ Use methods from: data/research-methods.md
   □ Record findings with sources
   □ Update Knowledge Map
   □ Add new unknowns to queue if discovered

   DEPTH ADJUSTMENT:
   • quick: Research top 2-3 items only
   • standard: Research all P1 and P2 items
   • deep: Research all items + exploratory research

   Output: Research Summary + Updated Knowledge Map

   ↓ PROCEED if critical unknowns addressed
   ↓ STAY if more research needed (check iteration limit)
   ↑ RETURN TO STEP 0 if framing changed
   ✖ ABORT if research reveals decision should not be made

📂 Step 2: MAP (Divergent)
   Load: steps/step-02-map.md

   □ 📂 M001 → Discover dimensions (axes of choice)
   □ 📂 M002 → Enumerate options per dimension
   □ 📂 M003 → Map hard and soft constraints
   □ Build Morphological Box (see step file for format)

   DEPTH ADJUSTMENT:
   • quick: 3 dimensions minimum
   • standard: 4-6 dimensions
   • deep: Exhaustive dimension discovery

   Output: Option Map (draft)

   ↓ PROCEED if dimensions are complete
   ↑ RETURN TO STEP 1 if knowledge gaps found (check loop limit)
   ✖ ABORT if no viable options exist

📂 Step 3: DEEPEN
   Load: steps/step-03-deepen.md

   □ 📂 E002 → Apply Counterfactual Thinking to key options
   □ 📂 E004 → Apply Boundary Analysis to key options
   □ 📂 E005 → Apply Causal Models to understand relationships
   □ 📂 M011 → Map consequences (mark VERIFIED vs ASSUMED)
   □ 📂 M012 → Assess reversibility of each option
   □ 📂 M013 → Map decision dependencies

   DEPTH ADJUSTMENT:
   • quick: Top 2 options only
   • standard: Top 3-5 options
   • deep: All viable options

   Output: Consequence Map with verification status

   ↓ PROCEED if critical consequences verified
   ↑ RETURN TO STEP 1 if consequences need research (check loop limit)
   ✖ ABORT if all consequences unacceptable

📂 Step 4: CHALLENGE (Adversarial)
   Load: steps/step-04-challenge.md

   □ 📂 E006 → Apply Falsification to key beliefs
   □ 📂 M021 → Imagine failure, trace causes
   □ 📂 M022 → Find low-probability high-impact events
   □ 📂 M023 → Break assumptions one by one
   □ Check for cognitive biases
   □ Update map based on findings

   IF fear_analysis = on:
   □ 📂 E010 → Find smallest test to learn
   □ 📂 E014 → Assess if path develops user
   □ 📂 E008 → Revisit risks — which are now addressed?
   □ Update Fear Map with verified/falsified concerns

   DEPTH ADJUSTMENT:
   • quick: Key beliefs only, basic bias check
   • standard: Full challenge procedure
   • deep: Multiple rounds, devil's advocate, external validation

   Output: Challenged map with strengthened/weakened items
           (+ Updated Fear Map with resolution status if fear_analysis=on)

   ↓ PROCEED if challenge passed (normal path)
   ↑ RETURN TO STEP 0 if fundamental reframe needed (rare, requires user agreement)
   ✖ ABORT if all options are fatally flawed

📂 Step 5: SYNTHESIZE
   Load: steps/step-05-synthesize.md

   □ 📂 E003 → Compress insights to minimal assertions
   □ Cluster natural strategic options
   □ Identify decision sequence (what first, what can wait)
   □ Assess decision readiness per item
   □ 📂 E007 → Identify remaining gaps

   Output: Synthesis ready for report

   ↓ PROCEED to final output

📂 Step 6: OUTPUT
   Load: steps/step-06-output.md
   Load template: data/exploration-report-template.md

   □ Section 1: What We Learned
   □ Section 2: What We Still Don't Know
   □ Section 3: Option Map
   □ Section 4: Strategic Clusters
   □ Section 5: Consequence Map
   □ Section 6: Decision Readiness
   □ Section 7: Suggested Next Steps
   □ Section 8: Fear Resolution (only if fear_analysis=on)

   Output: EXPLORATION REPORT
```

---

## SCORING SYSTEM (V2.1.1)

### Design Principles

1. **Verification > Enumeration** - verifying is harder and more valuable than listing
2. **Quality Gates** - minimum requirements must be met regardless of score
3. **Diminishing Returns** - caps prevent gaming with excessive items
4. **Verification Ratio** - must verify a percentage of consequences

### Exploration Coverage Score (C)

| Category | Item | Points | Cap |
|----------|------|--------|-----|
| **DISCOVERY** | Dimension discovered | +1.5 | max 8 |
| | Option enumerated | +0.5 | max 20 |
| **VERIFICATION** | Consequence VERIFIED | +2.0 | - |
| | Consequence ASSUMED | +0.2 | - |
| | Assumption tested | +1.5 | - |
| | Assumption falsified | +2.0 | - |
| **ANALYSIS** | Unknown Unknown surfaced | +1.5 | - |
| | Boundary identified | +1.0 | - |
| | Causal relationship mapped | +1.0 | - |
| **CHALLENGE** | Premortem cause found | +0.5 | - |
| | Black swan identified | +0.5 | - |
| | Bias checked | +0.3 | - |
| | Belief stress tested | +0.5 | - |

**When fear_analysis = on, additional:**

| Fear Resolution | Points |
|-----------------|--------|
| Fear classified | +0.5 |
| False wall identified | +1.5 |
| True wall confirmed | +1.5 |
| Controllable concern found | +0.5 |
| Success path discovered | +2.0 |
| Comparable analyzed | +0.5 |

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

**Failing quality gates caps the level regardless of score.**

### Coverage Thresholds (by depth)

| Score | quick | standard | deep |
|-------|-------|----------|------|
| COMPREHENSIVE | C ≥ 15 | C ≥ 35 | C ≥ 50 |
| ADEQUATE | C ≥ 10 | C ≥ 22 | C ≥ 35 |
| PARTIAL | C ≥ 5 | C ≥ 12 | C ≥ 20 |
| INSUFFICIENT | C < 5 | C < 12 | C < 20 |

**Note:** When fear_analysis=on, thresholds increase by +5.

---

## CRITICAL RULES

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  EXPLORATION COMMANDMENTS                                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  1. ALWAYS START WITH INVOCATION                                            │
│     Display the depth selection dialog before doing anything                │
│     Wait for user choice before proceeding                                  │
│                                                                              │
│  2. KNOWLEDGE BEFORE MAPPING                                                │
│     Never map options in a space you don't understand                       │
│     Step 0 + Step 1 are NOT optional                                        │
│                                                                              │
│  3. VERIFY BEFORE CLAIMING                                                  │
│     Mark every consequence as VERIFIED or ASSUMED                           │
│     Critical assumptions MUST be verified or flagged                        │
│                                                                              │
│  4. RESPECT DEPTH LIMITS                                                    │
│     quick = 1 iteration, no loops                                           │
│     standard = max 3 iterations                                             │
│     deep = until resolved                                                   │
│                                                                              │
│  5. AUTO-DETECT FEAR                                                        │
│     Don't ask about fear analysis - detect from language                    │
│     If detected, enable silently and include in report                      │
│                                                                              │
│  6. USER DECIDES, AI EXPLORES                                               │
│     Output is UNDERSTANDING, not recommendation                             │
│     Present options fairly, let user weigh trade-offs                       │
│                                                                              │
│  7. LOAD FILES WHEN NEEDED                                                  │
│     Announce: "📂 Loading [path]"                                           │
│     Follow the procedure in the loaded file                                 │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## FILE LOADING PROTOCOL

When you need specific data, announce and load:

| Situation | Load | Announcement |
|-----------|------|--------------|
| Start Step 0 | `steps/step-00-knowledge-audit.md` | "📂 Loading Step 0: Knowledge Audit" |
| Start Step 1 | `steps/step-01-research.md` | "📂 Loading Step 1: Research" |
| Start Step 2 | `steps/step-02-map.md` | "📂 Loading Step 2: Map" |
| Start Step 3 | `steps/step-03-deepen.md` | "📂 Loading Step 3: Deepen" |
| Start Step 4 | `steps/step-04-challenge.md` | "📂 Loading Step 4: Challenge" |
| Start Step 5 | `steps/step-05-synthesize.md` | "📂 Loading Step 5: Synthesize" |
| Start Step 6 | `steps/step-06-output.md` | "📂 Loading Step 6: Output" |
| Execute method | `data/method-procedures/[ID]_[Name].md` | "📂 Loading method: [Name]" |
| Generate report | `data/exploration-report-template.md` | "📂 Loading report template" |
| Scoring | `data/coverage-scoring.yaml` | "📂 Loading scoring rules" |

---

## KEY PATHS

```
deep-explore-v2/
├── workflow.md                           ← This file (start here)
├── steps/step-{00-06}-*.md               ← Step procedures
├── data/method-procedures/{ID}_*.md      ← Method procedures
├── data/coverage-scoring.yaml            ← Scoring rules
├── data/exploration-report-template.md   ← Output template
└── data/research-methods.md              ← Research guidance
```

Method file naming: `{ID}_{Name}.md` where ID is E001-E014 or M001-M023.

---

## METHOD NAMING CONVENTION

Deep Explore uses two method categories:

| Prefix | Category | Purpose | Used In |
|--------|----------|---------|---------|
| **E***  | Epistemological | Foundation methods for knowledge discovery | All steps |
| **M***  | Process | Step-specific methods for exploration phases | Specific steps |

**E-methods (E001-E014):**
- E001-E007: Core epistemological methods (always available)
- E008-E014: Fear-based methods (when `fear_analysis = on`)

**M-methods (M001-M054):**
- M001-M003: MAP phase (Step 2)
- M011-M018: ILLUMINATE phase (Step 3)
- M021-M026: CHALLENGE phase (Step 4)
- M031-M036: SYNTHESIZE phase (Step 5)
- M041-M044: CONVERGE phase (Step 6)
- M051-M054: META (any step)

**Note:** The `methods.csv` file contains all methods with their descriptions and output patterns.
