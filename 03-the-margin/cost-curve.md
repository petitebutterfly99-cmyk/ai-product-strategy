# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
| :--- | :--- | :--- |
| Inference (primary model) | $1.44 | Mid-tier semantic extraction (40% volume share) |
| Inference (cascading/triage) | $0.09 | Small triage model routing & initial tagging (50% volume share) |
| Infrastructure | $0.50 | Vector database storage, webhook routing, and API gateway overhead |
| Data/storage | $0.20 | Encrypted audit logging and tenant-specific embeddings |
| Human-in-the-loop | $0.45 | Exception review queue fallback for sub-85% confidence extractions |
| **Total AI COGS** | **$2.68** | Blended monthly operating cost per active user |


## Justification of the Model

* **Small Tier (e.g., GPT-4o-mini):** Used for high-volume, low-complexity tasks like initial token classification and basic intent tagging because its sub-millisecond latency and ultra-low cost protect gross margins on routine inputs.

* **Mid Tier (e.g., Claude Sonnet):** Deployed for core semantic extractions and structured field note mapping because it strikes the optimal balance between high syntactic accuracy and moderate compute expense.

* **Frontier Tier (e.g., o3 / Claude Opus):** Reserved for low-volume, high-complexity exceptions and multi-system edge cases because its advanced reasoning capabilities guarantee error resolution when confidence scores drop below safety thresholds.

## Cascading Strategy

* **Triage model:** GPT-4o-mini
* **Frontier model:** Claude Sonnet / o3
* **Routing rule:** Route all inbound raw ambient audio and text logs through the triage model for initial classification; escalate to the mid-tier model for standard enterprise extractions, and trigger the frontier model only when confidence scores drop below the 85% threshold or complex multi-system edge cases arise.
* **Expected cascade ratio:** 90% (Triage + Mid) / 10% (Frontier)

## Pricing Model

* **Current pricing:** $45.00 / user / month (Flat-rate SaaS baseline)
* **Proposed AI pricing:** $45.00 / user / month base + $0.15 per verified outcome unit overage block
* **Model:** Hybrid (Seat-based floor with usage-based overage tiers tied to heavy ambient transcription volume)

## Stress Tests

| Scenario | Impact on Margin | Response |
| :--- | :--- | :--- |
| Inference costs 3x | Gross margin compresses from 94% down to 81%; monthly AI COGS surges to $8.04 per user. | Instantly widen the triage window by shifting 15% more volume from mid-tier to small models and activate aggressive semantic caching. |
| Heaviest segment doubles | Request volume surges 100% among power users, driving server and token costs up linearly. | Enforce fair-use rate limits or automatically migrate high-volume power users to enterprise usage-based billing tiers. |
| Model provider raises prices 50% | Direct margin erosion of 4.5 points across standard enterprise contracts. | Execute 48-hour fallback routing protocol via LiteLLM abstraction layer to secondary low-cost provider endpoints. |

## Board One-Pager

**Cost of one successful AI outcome:** $0.0178 (Calculated by taking the total blended monthly AI COGS per user of $2.68 and dividing it by an average baseline volume of 150 requests/outcomes per month).

**Price charged for that outcome:** $0.325 blended revenue per outcome unit (Derived from the hybrid pricing model, which generates $48.00 total monthly revenue per user—$45.00 base for the first 200 units plus an average overage capture—across 150–200 volume units).

**Impact of tripling usage:** If request volume triples from 150 to 450 requests per user/month, monthly AI COGS surges linearly from $2.68 to $8.04 per user. Under a flat-rate base pricing structure, this volume spike would rapidly erode profit margins; however, because the hybrid model captures outcome-based overage fees ($0.15 per unit over baseline), top-line revenue scales alongside compute costs, protecting profitability and keeping gross margins structurally resilient above 80%.


* **Before (traditional SaaS):** 85% gross margins with predictable, low-maintenance hosting and storage costs.
* **After (AI-enabled):** 94% gross margin at baseline, dropping to 81% under extreme token shock; protected by intelligent model cascading and hybrid pricing tiers.
* **Net margin shift:** -4% to +9% depending on successful enforcement of cascading routing and hybrid overage capture.
