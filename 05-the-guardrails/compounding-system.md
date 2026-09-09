# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Technician overrides, field supervisor manual corrections from the exception queue, and low-confidence resolution selections. | Updated enterprise lexicon mappings, expanded entity resolution weights, and new automated regression test cases injected into the Golden Dataset. | Y | active |
| Cross-Domain Transfer | Successful contract-to-asset mapping patterns and shorthand translation rules derived from HVAC and mechanical service tickets (e.g., Apex Corp deployments). | Generalized heuristic weights and contextual templates applied to new service domains (such as electrical, generator PM, or plumbing) without requiring domain-specific retraining. | Y | missing |
| Network Intelligence | Anonymized, aggregated extraction successes, common STT phonetic errors, and contract-matching edge cases across multiple distinct enterprise tenant deployments. | Pre-trained base prompt optimizations and baseline industry contract lexicons that elevate Day-1 accuracy for new enterprise onboarding. | Y | missing |

**Broken loop identified by partner:** 

1. Cross-Domain Transfer is leaking value due to siloed service ticket data across distinct enterprise verticals (e.g., HVAC maintenance vs. heavy equipment overhaul), causing newly onboarded service domains to start with cold-start extraction accuracy penalties.
**Fix plan:** 1. Monday Morning Schema Normalization: Deploy a shared, domain-agnostic metadata layer that abstracts facility, asset, and contract attributes into a unified schema so entity-resolution weights can be shared instantly.
2. Automated Cross-Pollination Pipeline: Configure a weekly scheduled export that pulls validated, anonymized correction rules from Loop 1 (Recursive Learning) and pushes generalized translation heuristics into the global lexicon registry.
3. Baseline Template Injection: Pre-load new enterprise tenant deployments with generalized baseline prompt templates derived from mature mechanical and electrical service workflows to instantly boost Day-1 zero-shot contract matching performance.
4. Cross-Domain Evaluation Suite: Integrate cross-domain regression rows into the master Golden Dataset to continuously measure and verify that performance improvements in one service vertical successfully transfer to adjacent verticals without introducing regression errors.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** 
* Field-to-Engineering Loop: Human-in-the-loop (HITL) corrections and exception queue overrides flow directly from field operations supervisors back into the golden dataset and lexicon registry.
* Metadata Normalization: Shared asset and contract extraction schemas propagate successful parsing patterns across distinct service domains (e.g., HVAC maintenance to electrical generator overhauls).
* Automated Evaluation Pipelines: Weekly automated regression suites circulate updated rule and LLM judge benchmarks across the engineering and product teams to maintain alignment on reliability metrics.

**Where it silos:** 
* Vertical-Specific Jargon Boundaries: Specialized shorthand and localized trade terminology remain trapped within individual client accounts or distinct service verticals, preventing instant zero-shot transfer.
* System Disconnects: Unstructured technician voice notes processed by conversational interfaces occasionally fail to synchronize back into structured CRM and Jira reporting dashboards without manual intervention.
* Feedback Latency: Manual supervisor overrides sit in exception queues longer during peak operational windows, delaying the ingestion of fresh training signals into the recursive learning loop.

## Governance Policy

**Scope:**
**Autonomy boundaries:**
**Escalation triggers:**
**Audit cadence:**
**Regulatory exposure (EU AI Act / other):**

## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**






