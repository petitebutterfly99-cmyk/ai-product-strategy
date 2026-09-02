# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** |Direct OpenAI API calls tied to GPT-4o model-specific endpoints and schema formats. | H |Wrap core completion calls in a clean adapter interface to decouple application logic from vendor-specific SDKs. |
| **Abstraction** |Zero middleware layer; raw API requests pass directly from app backend to the LLM vendor. | H |Initialize and deploy an open-source abstraction layer (like LiteLLM) to unify prompt and response schemas. |
| **Routing** |Single-vendor pipeline with no automatic fallback options if primary endpoints fail or throttle. | M |Configure a secondary failover provider endpoint for non-blocking background tasks. |
| **Eval** |Manual spot-checking of extractions with no automated regression suite for model migrations. | M |Set up a baseline test dataset of 20 historical field logs to evaluate parser consistency across providers. |

## Portability Score
Locked

## If OpenAI doubles pricing tomorrow: 
<!-- What's your 48-hour response? -->
Gross margins collapse instantly. Because the product relies on continuous background semantic parsing and ambient audio-to-text transcription flows per user session, higher token costs directly erode the unit economics of the low-cost model without an immediate price hike to enterprise customers.

## If OpenAI ships a competing product:
<!-- What's defensible that they can't replicate? -->
Immediate operational disruption. Because the integration uses direct API calls tied to specific proprietary model features, a ToS shift regarding automated data logging or CRM sync pipelines would force an emergency code rewrite to route through an agnostic abstraction layer (like LiteLLM or Portkey).

## Three Actions

**This week:** Implement an open-source abstraction layer (such as LiteLLM or LangChain) to decouple direct provider API calls from the core application logic.

**This month:** Build automated fallback routing to a secondary provider (e.g., Anthropic Claude or Google Gemini) to ensure zero downtime if primary API availability or policy shifts occur.

**This quarter:** Establish a multi-provider evaluation test suite to benchmark token costs, latency, and extraction accuracy weekly, protecting operating margins against sudden price shocks.
