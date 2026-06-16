<!-- markdownlint-disable -->
<div align="center">

> *A hypothesis is not a guess — it is a precisely engineered bridge between what we know and what we need to test. The difference between having an idea and having a hypothesis is the difference between pointing at the horizon and drawing a map to get there.*

</div>

# 🧪 Hypothesis Formation

*Goal-Driven Hypothesis & Research Question Formation Engine for Academic Research*

> 🧭 **Part of the [De-Anthropocentric Research Engine](https://github.com/yogsoth-ai/de-anthropocentric-research-engine).** This repository is one of nine composable research packages that make up DARE — the full autonomous research-orchestration system. DARE bundles this package together with the others into a single self-contained clone, unified under one orchestrator. To use these skills as intended — with the spec-driven orchestrator and cross-package routing — clone the [main repository](https://github.com/yogsoth-ai/de-anthropocentric-research-engine) rather than this repo alone.

**Hypothesis Formation transforms upstream gaps and insights into testable hypotheses and precise research questions. You provide prioritized gaps — it ranks them, derives hypotheses with falsifiability criteria, and formulates framework-guided research questions with scope, success criteria, and sub-question decomposition. Three autonomous campaigns, each with quantitative budget enforcement.**

---

## ⚡ What It Does

- 🎯 **Gap Prioritization** — multi-criteria ranking of research gaps using AHP weighting, PiCMe assessment, pairwise comparison, portfolio optimization, and sensitivity testing
- 🔬 **Hypothesis Formulation** — transforms insights into structured hypotheses via deductive, inductive, and abductive reasoning. Produces competing hypotheses with falsifiability criteria and boundary conditions
- 📐 **Research Question Formation** — framework-guided formulation (PICO/SPIDER/SPICE/ECLIPSE), scope calibration, sub-question decomposition, and FINER criteria validation

---

## 🎯 Design Philosophy

### 🎖️ Campaign-Based Architecture

Each campaign is a self-contained research activity domain. The entry point routes to the correct campaign based on user intent, then the campaign autonomously selects strategies and executes with quantitative budget enforcement.

### 📐 Four-Level Hierarchy

```bash
ENTRY.md (root)
  → Campaign (3): self-contained research activity domain
    → Strategy: selected by research context and constraints
      → Tactic: multi-step orchestration pattern
        → SOP: single operation (import or subagent)
```

### 📏 Budget Enforcement

Every strategy embeds quantitative floors (dimensions evaluated, hypotheses produced, FINER criteria passed). Budget gates prevent premature exit. Context checkpoints after every strategy completion.

### 📖 兵法书 (Art of War) Pattern

Skills teach principles and provide default reference flows — CC reads, internalizes, and constructs its own approach for each specific research task. Hard constraints are minimal: Budget Gate, Minimum Yield, HARD-GATE, context-checkpoint.

---

## 🏗️ Architecture

```bash
┌───────────────────────────────────────────────────────────────┐
│  ENTRY POINT (ENTRY.md)                                       │
│  Routes to campaign based on research intent                  │
├───────────────────────────────────────────────────────────────┤
│  CAMPAIGN (3)                                                 │
│  gap-prioritization, hypothesis-formulation, research-question│
├───────────────────────────────────────────────────────────────┤
│  STRATEGY (15)                                                │
│  5 per campaign, selected by context                          │
├───────────────────────────────────────────────────────────────┤
│  TACTIC (10)                                                  │
│  3 + 4 + 3, orchestrate SOPs into workflows                  │
├───────────────────────────────────────────────────────────────┤
│  SOP (44)                                                     │
│  5 import + 2 shared + 37 campaign-specific                   │
│  Single-responsibility subagent operations                    │
└───────────────────────────────────────────────────────────────┘
```

---

## 📋 Campaign Overview

### Campaign 1: Gap Prioritization

| Strategy | When to Use |
|----------|-------------|
| multi-criteria-ranking | Default — 5-20 gaps, systematic multi-dimensional scoring |
| evidence-based-prioritization | Gaps from rigorous literature review with strong evidence |
| stakeholder-weighted-ranking | Multiple stakeholders with different priority weights |
| portfolio-optimization | 20+ gaps, portfolio-level risk/reward optimization |
| rapid-triage | 50+ gaps, quick filtering to manageable set |

### Campaign 2: Hypothesis Formulation

| Strategy | When to Use |
|----------|-------------|
| deductive-hypothesis-generation | Mature theory exists, gap is theory-reality deviation |
| inductive-hypothesis-generation | No theory, but data patterns or empirical observations |
| abductive-hypothesis-generation | Anomalous observations that defy existing explanations |
| competing-hypothesis-construction | Need multiple alternatives to avoid confirmation bias |
| hypothesis-operationalization | Have directional hypothesis, need to formalize |

### Campaign 3: Research Question Formation

| Strategy | When to Use |
|----------|-------------|
| framework-guided-formulation | Clear research type, standard framework available |
| scope-calibration | Question too broad or too narrow |
| decomposition-formulation | Complex question, single study can't answer |
| comparative-formulation | Need to compare A vs B systematically |
| feasibility-constrained-formulation | Ideal question exceeds available resources |

---

## 🔧 Dependencies

| Dependency | What It Provides |
|-----------|-----------------|
| [web-browsing](https://github.com/yogsoth-ai/web-browsing) | web-search + web-research (2 import SOPs) |
| [literature-engine](https://github.com/yogsoth-ai/literature-engine) | paper-overview + paper-search + paper-research (3 import SOPs) |
| [subagent-spawning](https://github.com/yogsoth-ai/subagent-spawning) | Subagent dispatch conventions |
| [context-management](https://github.com/yogsoth-ai/context-management) | context-init + context-checkpoint protocol |

### MCP Servers Required

| Server | Purpose |
|--------|---------|
| brave-search | Web search for frameworks, methods, background |
| apify | Deep web scraping, Google Scholar |
| alphaxiv | Paper discovery, content, PDF Q&A |
| semantic-scholar | Paper metadata, citations, recommendations |

---

## 🚀 Quick Start

1. Clone this repo alongside its dependencies:
```bash
git clone https://github.com/yogsoth-ai/hypothesis-formation.git
git clone https://github.com/yogsoth-ai/web-browsing.git
git clone https://github.com/yogsoth-ai/literature-engine.git
git clone https://github.com/yogsoth-ai/context-management.git
git clone https://github.com/yogsoth-ai/subagent-spawning.git
```

2. Copy `.mcp.example.json` to `.mcp.json` and fill in your API keys

3. Deploy skills to your Claude Code skills directory

4. Use via the entry point:
```
/hypothesis-formation I have 10 gaps from my literature survey on [topic]. Help me prioritize and formulate hypotheses.
```

---

## 📊 Scale

| Component | Count |
|-----------|-------|
| Campaigns | 3 |
| Strategies | 15 |
| Tactics | 10 |
| Subagent SOPs | 37 |
| Import SOPs | 5 |
| Shared SOPs | 2 |
| **Total skill directories** | **72** |

---

## 📄 License

[Apache-2.0](LICENSE)

---

*A component of the [De-Anthropocentric Research Engine](https://github.com/yogsoth-ai/de-anthropocentric-research-engine), part of the [Yogsoth AI](https://github.com/yogsoth-ai) ecosystem. Built by [Pthahnix](https://github.com/Pthahnix).*
