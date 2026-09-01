# Data Flywheel Map

> Score each loop 1-5. Your weakest loop is where competitors attack first.
> The four loops below are the M2 starting point - adapt if your product has 2 or 6 loops instead of 4.
# Product Bet: The Zero-Interface Semantic Data Janitor

# Overview
This document outlines the strategic bet, technical architecture, and validation framework for **QuietOps**, an AI-native hybrid Oracle-Automator designed to eliminate administrative drag in enterprise environments.

# Core Hypothesis
By transforming unstructured, ambient operational communication (voice memos, Slack chats, client calls) into standardized, verified records for legacy systems (CRM, Jira) through a semantic cleaning and confidence-gated layer, we can capture an uncontested blue ocean market without forcing users to change their daily workflows.

# Strategic Architecture

**The Oracle Layer:** Parses messy, multi-modal human input and maps it against strict enterprise schemas.
**The Automator Layer:** Executes background system updates (creating tickets, logging hours, updating asset statuses) without manual UI entry.
**The Orchestrator Layer:** Manages probabilistic confidence thresholds, routing high-ambiguity extractions to a human-in-the-loop exception review queue.

# Validation & Prototyping Strategy

**Tooling:** Built on zero-cost developer tiers (e.g., Google AI Studio, Lovable, n8n) to prove utility before capital investment.
**Wedge Focus:** High-friction vertical workflows (such as field service reporting) where manual data entry tax is highest.

## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | 3/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | 2/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | 2/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | 1/5 |

### Correction Loop - 3/5
**What you capture today:** User edits and approvals made on the confidence-gated exception screen (e.g., when a technician corrects an extracted asset ID or SKU).
**How it compounds:** Every manual correction refines the few-shot prompt templates and fine-tuning datasets for that specific enterprise tenant, drastically reducing future ambiguity errors.

### Preference Loop - 2/5
**What you capture today:** Basic tenant-level configuration rules and static user profiles mapped to default routing schemas.
**How it compounds:** As individual users and teams interact with the system over time, it learns personalized communication shorthand, preferred formatting styles, and custom team terminology to tailor extractions automatically.

### Domain Context Loop - 2/5
**What you capture today:** Isolated vertical schema mappings for a single use case (e.g., field service repair logs).
**How it compounds:** Insights gathered from cleaning data in one operational workflow (like maintenance tracking) feed into adjacent enterprise workflows (like asset inventory or billing), reducing setup friction for new business units.

### Network Loop - 1/5
**What you capture today:** Completely isolated, single-tenant data silos where user activity on Company A provides zero benefit to Company B.
**How it compounds:** Shared anonymous industry taxonomies and standardized cross-company vocabularies allow the AI model to instantly understand niche sector jargon out-of-the-box for new users.

**Total Flywheel Score:** 8/20
**Weakest Loop:** Network 1/5
**Fix for weakest loop:** Build a decentralized, anonymous federated learning layer that aggregates generalized industry-specific entity mappings (e.g., universal equipment part numbers and service taxonomies) across tenants without exposing proprietary company data.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** Salesforce (via Agentforce) or Microsoft (via Copilot Studio)
**Vector:** Native ambient capture built directly into the collaboration layer (Teams/Slack) or CRM input streams.
**Time-to-threat:** 6 to 12 months
**% of value at risk:** 70%

### 2. Vertical Competitor
**Attacker:** Specialized field service software suites (e.g., ServiceMax or Salesforce Field Service)
**Vector:** Adding native voice-to-structured-record generation specifically engineered for field technician workflows.
**Time-to-threat:** 3 to 6 months
**% of value at risk:** 50%

### 3. Adjacent Expansion
**Attacker:** General-purpose transcription and meeting note AI tools (e.g., Otter.ai or Fireflies)
**Vector:** Expanding from passive meeting summarization directly into automated CRM and Jira record creation via webhook integrations.
**Time-to-threat:** 0 to 3 months
**% of value at risk:** 40%

---

## 90-Day Encroachment Plan

*Your partner played the Big Tech attacker. What was their plan to kill you?*

**Attacker:** Microsoft (via Microsoft Teams & Copilot ecosystem)
**Attack vector (target the weakest loop):** Exploiting the Network Loop by bundling pre-trained, cross-company enterprise taxonomies directly into the default office suite so new teams get instant zero-shot accuracy without training.
**Weeks 1-4 - what they ship:** Native voice and chat ambient logging embedded directly into Teams chats that auto-syncs with Dynamics 365 and Azure DevOps.
**Weeks 5-8 - how they poach users:** Offering zero-dollar add-on pricing for existing enterprise license holders, eliminating any financial or technical reason to install a third-party layer.
**Weeks 9-12 - why users don't come back:** The native tool leverages its massive cross-company network effect to instantly recognize internal corporate abbreviations that your isolated single-tenant setup still struggles with.
**Your defense:** Anchor deep workflow defensibility by becoming the vendor-agnostic system of record audit trail that bridges disparate silos (e.g., syncing Slack data into Jira and Salesforce simultaneously), ensuring high-friction switching costs that big tech walled gardens cannot easily replicate.
