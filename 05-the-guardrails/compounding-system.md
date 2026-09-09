# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Technician overrides, field supervisor manual corrections from the exception queue, and low-confidence resolution selections. | Updated enterprise lexicon mappings, expanded entity resolution weights, and new automated regression test cases injected into the Golden Dataset. | Y | Active |
| Cross-Domain Transfer | Successful contract-to-asset mapping patterns and shorthand translation rules derived from HVAC and mechanical service tickets (e.g., Apex Corp deployments). | Generalized heuristic weights and contextual templates applied to new service domains (such as electrical, generator PM, or plumbing) without requiring domain-specific retraining. | Y | Missing |
| Network Intelligence | Anonymized, aggregated extraction successes, common STT phonetic errors, and contract-matching edge cases across multiple distinct enterprise tenant deployments. | Pre-trained base prompt optimizations and baseline industry contract lexicons that elevate Day-1 accuracy for new enterprise onboarding. | Y | Missing |

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
Enterprise-grade automation and AI extraction workflows for "QuietOps," specifically governing voice-to-text technician transcription parsing, CRM contract and asset matching, multi-system Jira ticketing routing, and human-in-the-loop exception handling. Excludes: General-purpose corporate IT chatbots, internal HR documentation search tools, and unverified third-party consumer LLM integrations operating outside the QuietOps secure enterprise tenant boundary.

**Autonomy boundaries:** 
Standard CRM contract and site matching where AI confidence exceeds 90% and inputs map to verified master agreements or active service schedules., auto. Ambiguous facility matches, multi-contract collisions, and extraction confidence scores falling between 50% and 90% that require field supervisor verification before work order synchronization., human approval required. High-risk contract overrides, mid-job billing pivots to emergency purchase orders without audit trails, and actions triggered by inputs registering below 50% confidence or tripping prompt-injection defense layers., never auto.

**Escalation triggers:** 
1. Low Confidence Threshold: AI extraction confidence drops below 50%, or falls between 50–90% on multi-contract facility lookups.
2. Adversarial Security Flags: Input strings contain potential prompt injection vectors, system-prompt override attempts, or unauthorized formatting payloads.
3. Cross-Facility Collisions: Extracted site names mismatch with registered CRM account hierarchies (e.g., a facility tied to Client A referenced under Client B).
4. Hallucination Detection Triggers: Continuous automated validation flags an unverified or invented contract ID/asset serial number during extraction processing.

**Audit cadence:** 
* Real-time, Automated latency, hallucination check, and security injection filtering (Owner: Site Reliability Engineering / Datadog Monitoring Lead)). 
* Weekly, Golden dataset regression audits and accuracy evaluations comparing rule and LLM judge outputs against production telemetry (Owner: Product Quality Manager).
* Monthly, Cross-domain transfer validation and drift velocity reviews to measure policy degradation and lexicon freshness (Owner: Data Governance & AI Operations Lead).
* Quarterly, Comprehensive CISO compliance review, regulatory exposure alignment, and executive risk assessment (Owner: Chief Information Security Officer).

**Regulatory exposure (EU AI Act / other):** 
U AI Act (High-Risk AI Systems Annex III / Critical Infrastructure & Service Management), GDPR (Data Minimization and Right to Explanation for automated work order decisions), and SOC 2 Type II Security Trust Services Criteria.. Risk tier: high. Controls: Multi-tier confidence gating with deterministic fallback queues, strict data anonymization pipelines for voice transcription logs, cryptographic audit logging of all system overrides, and immutable human-in-the-loop sign-off requirements for ambiguous financial mappings..

## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

* Transcription & Extraction Agent: Can parse unstructured technician voice notes and map them to known CRM entities. Can't modify live master billing agreements or bypass validation gates. Approval owner: Data Operations Lead.
* Multi-System Routing Agent: Can coordinate parallel API calls between CRM work orders and Jira parts ticketing. Can't dispatch assets or sync cross-account data when a facility collision flag is active. Approval owner: Enterprise Integrations Architect.
* Exception & Governance Agent: Can route low-confidence or adversarial inputs to human supervisory queues and trigger auto-rollbacks on hallucination breaches. Can't auto-resolve security violations or manually approve billing overrides without human sign-off. Approval owner: Field Operations Security Supervisor.


## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**


## Agent Topology






