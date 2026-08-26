# Three-Axis Vulnerability Diagnostic

## Product
<!-- Name the product you're diagnosing. Real product at your company — not a hypothetical. -->

**Product:** QuietOps / Draftless / ZeroForm


**Your Role:** AI Product Manager

---

## Scores

### Contextual Moat — 2/5
*Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?*

**Score rationale:**

If a competitor showed up with a slightly better voice-parsing model or a slicker auto-tagging UI, users would abandon ship in 48 hours.
While ambient capture deeply embeds the product into daily operational chatter, switching costs are moderate because the underlying raw communication data (Slack, email, audio) still lives in external third-party systems.

**Named attacker (from partner challenge):**
Verticalized workflow giants (e.g., Salesforce Agentforce or specialized field service suites) that build native ambient listeners directly into their proprietary ecosystems.

---

### Data Advantage — 2/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*

**Score rationale:**
At the start, the system relies primarily on foundational LLM zero-shot parsing rather than a massive proprietary dataset, making the initial data advantage relatively thin.

**Named attacker (from partner challenge):**
Foundation model providers (like OpenAI or Anthropic) baking native multi-turn semantic data-normalization features straight into their core APIs.

---

### Platform Exposure — 3/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native — then what?*

**Score rationale:**
The product sits as a translation and hygiene layer dependent on underlying communication APIs and LLM model providers, exposing it to platform shifts if ecosystem rules change.

**Named attacker (from partner challenge):**
Collaboration ecosystems (like Microsoft Teams or Slack) launching built-in, no-code automation features that ingest and clean data natively within their own walled gardens.

---

## Top Vulnerability
<!-- One line: what's the single biggest strategic risk? -->
Heavy reliance on external LLM APIs and chat platforms for raw data ingestion, leaving it vulnerable to upstream feature encroachment

## Confidence Level
<!-- H / M / L — how confident are you in this bet after the diagnostic? -->
H