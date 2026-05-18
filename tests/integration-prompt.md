# Integration Test Scenarios

Live integration tests for the hypothesis-formation skill repo. Run these scenarios to verify campaign routing, strategy selection, and end-to-end execution.

## Prerequisites

- All MCP servers running (brave-search, apify, alphaxiv, semantic-scholar)
- Sibling repos available (web-browsing, literature-engine, subagent-spawning, context-management)
- Subagent support enabled
- North-star-crystallization complete (research intent crystallized)
- At least one upstream repo has produced gaps/insights

---

## Scenario 1: Gap Prioritization Routing

**Prompt:**
```
I have 8 research gaps from my literature survey on protein language models. Help me prioritize which ones to attack first.
```

**Expected behavior:**
- Routes to `gap-prioritization` campaign
- Campaign selects `multi-criteria-ranking` strategy (5-20 gaps, systematic evaluation)
- Tactic: `scoring-matrix-construction`
- SOPs: gap-normalization → importance-scoring → feasibility-scoring → novelty-scoring → priority-synthesis

**Quality checks:**
- [ ] Correct campaign selected (gap-prioritization)
- [ ] Strategy selection justified
- [ ] Budget Gate enforced (≥4 dimensions for M tier)
- [ ] context-checkpoint called after strategy completes
- [ ] Final output: ranked gap list + top 3-5 attack suggestions

---

## Scenario 2: Hypothesis Formulation Routing

**Prompt:**
```
Based on the gap "current protein language models fail to capture long-range structural dependencies", generate testable hypotheses about why this happens and what mechanisms might address it.
```

**Expected behavior:**
- Routes to `hypothesis-formulation` campaign
- Campaign selects `deductive-hypothesis-generation` strategy (existing theory → derive hypotheses)
- Tactic: `theory-mechanism-extraction`
- SOPs: theory-identification → mechanism-extraction → variable-identification → relationship-specification

**Quality checks:**
- [ ] Correct campaign selected (hypothesis-formulation)
- [ ] ≥3 structured hypotheses produced (M tier)
- [ ] Each hypothesis has: variables, direction, boundary conditions
- [ ] Falsifiability check performed for each hypothesis
- [ ] context-checkpoint called after strategy completes

---

## Scenario 3: Research Question Formulation Routing

**Prompt:**
```
I have the hypothesis "Incorporating 3D structural priors into protein language model pre-training improves downstream fold prediction accuracy." Help me formulate precise research questions.
```

**Expected behavior:**
- Routes to `research-question` campaign
- Campaign selects `framework-guided-formulation` strategy
- Tactic: `framework-selection-and-application`
- SOPs: framework-matching → pico-application → finer-criteria-check

**Quality checks:**
- [ ] Correct campaign selected (research-question)
- [ ] Framework selected with justification (likely PICO for quantitative)
- [ ] All framework components filled with specifics
- [ ] FINER 5/5 pass
- [ ] Success criteria defined (measurable)
- [ ] context-checkpoint called after strategy completes

---

## Scenario 4: Multi-Campaign Orchestration

**Prompt:**
```
I have raw gaps from my literature survey. Take me through the full pipeline: prioritize the gaps, generate hypotheses for the top ones, and formulate research questions.
```

**Expected behavior:**
- Executes gap-prioritization → hypothesis-formulation → research-question (serial)
- Each campaign has its own context file
- context-checkpoint after each strategy within each campaign

**Quality checks:**
- [ ] All 3 campaigns execute in correct order
- [ ] Gap prioritization output feeds into hypothesis formulation
- [ ] Hypothesis output feeds into research question formulation
- [ ] 3 separate context files created
- [ ] Budget Gates enforced at each campaign level

---

## Scenario 5: Competing Hypotheses

**Prompt:**
```
For the phenomenon "attention-based protein models outperform CNN-based models on contact prediction but underperform on stability prediction", generate competing hypotheses that could explain this discrepancy.
```

**Expected behavior:**
- Routes to `hypothesis-formulation` campaign
- Campaign selects `competing-hypothesis-construction` strategy
- Tactic: `competing-hypothesis-matrix`
- SOPs: competing-hypothesis-generation → discriminating-prediction-design → hypothesis-comparison-matrix

**Quality checks:**
- [ ] ≥3 competing hypotheses generated
- [ ] Discriminating predictions designed (what would distinguish them)
- [ ] Comparison matrix produced
- [ ] Each hypothesis is independently testable
