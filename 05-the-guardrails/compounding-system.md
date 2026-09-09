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


## Compounding Defensibility & Strategic Moats

* Build a Closed-Loop Defensibility Engine: Treat proprietary enterprise feedback (the data generated every time a technician overrides an extraction or resolves an ambiguity) as primary moat, ensuring every human correction directly updates our proprietary golden dataset and extraction lexicons.
* Accelerate Compound Velocity: While static competitor models drift and degrade against shifting field shorthand and new contract structures, continuously compress our model's iteration cycle through automated weekly regression testing and recursive prompt updates.
* Integrate Cross-Domain Intelligence: Rapidly bridge the Cross-Domain Transfer loop (our current architectural gap) so that insights learned in one service vertical (like HVAC) instantly improve extraction performance across entirely new verticals (like electrical or plumbing) before a static competitor can manually adapt.
* Embed Contextual Stickiness: Deepen native workflow integrations across enterprise endpoints (CRM contract registries, Jira ticketing, and localized voice-to-text pipelines) so that switching costs multiply alongside our system's compounding reliability gains.

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

### Discover, User-Side Workarounds
- Field technicians and dispatchers using external LLM wrappers or custom GPTs to parse shorthand voice notes and format raw work orders before manual CRM entry. | source: Support ticket | signal: Capability gap 
- Supervisors setting up private Zapier/Make automations to bridge unstructured voice transcripts directly into secondary Jira parts tracking systems outside official connectors. | source: Zapier/Make | signal: Workflow gap 
- Regional teams maintaining custom spreadsheets and local macro scripts to cross-reference ambiguous contract numbers and resolve facility name collisions. | source: Sales call | signal: Trust gap 


| Tool | Owner | Risk Level | Decision |
| :--- | :--- | :--- | :--- |
| External LLM wrappers & custom GPTs for voice note parsing | Field Operations / Dispatch | M | Govern |
| Private Zapier/Make automations bridging CRM to Jira | Enterprise Integrations | H | Kill |
| Regional spreadsheets and local macro scripts for contract cross-referencing | Regional Admin Teams | L | Keep |

### Shadow AI Audit Metrics
* **Total tools found:** 3
* **Tools after triage:** 2
* **Estimated hidden spend:** $4,500/mo ($1,200/mo in manual entry labor, $2,500/mo in prevented ticket errors, and $800/mo in administrative overhead)


## Action Plan

### Build
* Field Technician Shorthand Parsing ($1,200/mo saved in labor): Absorb native audio-to-CRM transcription and shorthand normalization directly into the QuietOps workflow, eliminating the need for external LLM wrappers by baking real-time entity extraction and validation into the core interface.
* Secondary Jira Parts Bridging ($2,500/mo in prevented ticket errors): Integrate automated bi-directional synchronization between CRM contract registries and Jira parts tracking natively into the product suite to remove the dependency on brittle custom Zapier loops.

### Partner
Cross-Reference & Contract Resolution ($800/mo in administrative overhead): Establish an official integration with regional enterprise middleware and directory tools rather than rebuilding custom multi-tenant directory lookups from scratch, allowing teams to leverage existing identity and master data management systems securely.

### Ignore + Monitor
Local Macro Scripts & Spreadsheets: Accept that edge-case power users will maintain legacy personal calculation sheets for fringe billing formulas, but actively monitor support channels to catch when these external tools signal a genuine capability or workflow gap requiring future native absorption.

## Roadmap Brief
Based on your audit: 3 user-side workarounds discovered.
Decisions: 2 build · 1 partner · 0 ignore · 0 TBD.
Estimated adjacent spend: $4500/mo across surveyed users.
Dominant signal: Capability gap.

Recommended next step: Capability gaps dominate, users want something your product does not do. Strongest near-term move is building one or two of these natively before a competitor does.

Sequence the Build column by frequency × strategic relevance. Confirm Partner candidates with the external tools' partnership teams. Re-run this audit each quarter, workarounds shift fast.






