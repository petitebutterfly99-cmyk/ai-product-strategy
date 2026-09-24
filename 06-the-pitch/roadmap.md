# Three-Horizon Roadmap & Board Pitch for QuietOps / Draftless / ZeroForm 

# AI Evaluation

## Overall Score

**2.6/5**

## Biggest Risk

The product reaches **technical feasibility without strategic necessity**: it works reasonably well, but customers do not trust it enough for autonomous operation or derive enough differentiated value to justify putting another enterprise layer between their communications and systems of record.

In that scenario, Microsoft/Salesforce improving native extraction and workflow capabilities compresses the remaining differentiation.

## Top 3 Actions

1. **Run a narrowly scoped 4–6 week production pilot** with predefined adoption, ROI, accuracy, exception-rate, and kill thresholds.

2. **Expand the 14-row golden dataset into a production-grade evaluation system** and establish decision-specific reliability metrics before raising autonomy.

3. **Redesign defensibility around the proprietary operational entity graph and accumulated correction/context data.** Defer federated learning and demonstrate that customer-specific learning measurably improves performance over time.

## Strategic Conclusion

The central issue is that **the strategy is currently more mature than the evidence underneath it**.

There are sophisticated answers for architecture, governance, inference optimization, and future defensibility, but comparatively thin evidence for the three questions that matter first:

- **Do users repeatedly want it?**
- **Does it reliably perform the job?**
- **Does the resulting customer value comfortably exceed the cost and integration burden?**

Resolving those questions should precede most of the more ambitious platform work.

## Roadmap

### Horizon 1, Ship (0–4 weeks)

| Initiative | Strategy Component | Why it ships now | Confidence |
|---|---|---|---|
| **1. Multi-tier intelligent model routing** | Margin | Directly attacks the current $2.68/unit AI COGS and 54% AI-adjusted GM. Architecture is understood and measurable immediately. | H |
| **2. Semantic caching + tenant token tracking** | Margin | Low-risk cost optimization with immediate unit-economic visibility and savings. | H |
| **3. Admin view of token consumption + unit COGS** | Margin | You cannot manage the margin strategy without transaction-level economics. | H |
| **4. Fallback thresholds for cheap inference tiers** | Margin | Required to operationalize the cascading-model strategy already specified. | H |
| **38. Corporate jargon lexicon management** | Moat | Creates persistent tenant-specific workflow context and switching cost without requiring sophisticated ML. | H |
| **39. Save acronym mappings from exception reviews** | Moat | Turns existing HITL work into proprietary structured feedback immediately. | H |
| **72. Log AI decisions, confidence + overrides** | Guardrails | Foundational auditability; also creates evaluation/feedback data needed elsewhere. | H |
| **74. Quarantine expired-agreement work orders** | Guardrails | Deterministic rule with high downside protection; does not require speculative AI. | H |
| **107. Retry/rate-limit downstream integrations** | Guardrails | Basic production reliability prerequisite before automation volume increases. | H |
| **108. Technician sync confirmation** | Bet | Closes the user feedback loop and reduces duplicate manual entry—the behavior the product is supposed to eliminate. | H |
| **122. Streaming audio ingestion** | Bet | Core input capability for the voice-first workflow. | H |
| **123. One-tap messy voice capture** | Bet | Tests the central UX assumption with minimal abstraction between technician and value. | H |
| **124. Industrial audio filtering** | Contract | Directly improves upstream transcription quality and therefore downstream reliability. | H |
| **152. Index active customer-site embeddings** | Bet | Straightforward prerequisite for useful entity resolution. | H |
| **153. Auto-link logs to customer accounts** | Bet | Direct expression of the core operational value proposition. | H |
| **154. Score CRM account/site candidates** | Contract | Makes uncertainty explicit and enables confidence-gated validation. | H |
| **182. Backoff + idempotency for API calls** | Guardrails | Preventing duplicate writes is table stakes for trusted automation. | H |
| **183. Dispatcher cross-system confirmation** | Contract | Gives humans evidence that automated execution actually completed. | H |
| **212. Review-queue state transitions** | Contract | Creates traceability for the HITL architecture already specified in the strategy. | H |
| **213. Supervisor exception dashboard** | Contract | The review loop is part of the kill criteria; you need to observe whether humans actually use it. | H |
| **214. Confidence-based quarantine** | Contract | Implements the core safety mechanism, though the proposed 85% threshold must be calibrated rather than treated as permanent. | H |
| **242. Inspect outgoing LLM payloads** | Guardrails | Direct mitigation for the stated external-model/data-handling dependency. | H |
| **243. Export AI usage/audit logs** | Guardrails | Necessary enterprise governance capability and relatively low technical uncertainty. | H |
| **244. Scrub sensitive identifiers before logging** | Guardrails | Data-minimization control should precede greater enterprise data volume. | H |

The strategy explicitly calls out model-routing cost reduction, confidence gating, correction loops, agent boundaries, and enterprise governance, making these the highest-confidence implementation work.

### Horizon 2, Validate (1–3 months)

| Initiative | Strategy Component | Hypothesis | Kill Criteria | Confidence |
|---|---|---|---|---|
| **36. Proprietary operator-correction feedback loop** | Moat | Captured corrections materially improve tenant-specific recognition and reduce exceptions over time. | If we don't see **≥20% reduction in repeat jargon/acronym exceptions by week 6**, stop expanding the learning system. | M |
| **37. Weekly embedding updates from validated exceptions** | Moat | Periodically incorporating validated corrections improves future resolution enough to justify pipeline complexity. | If updated retrieval doesn't produce a **measurable lift over the static baseline by week 6**, stop automated updates. | M |
| **71. End-to-end auditability/security guardrails** | Guardrails | Enterprise buyers will accept the third-party hygiene layer when its decisions and access are auditable. | If pilot security stakeholders still identify **blocking audit/control gaps after week 6**, narrow or stop enterprise rollout. | M |
| **73. Compliance quarantine dashboard** | Guardrails | Dedicated compliance workflows materially reduce enterprise approval friction. | If compliance users don't use the dashboard for **≥80% of flagged pilot transactions by week 6**, fold the capability into the standard review queue. | M |
| **106. CRM → downstream ticketing bridge** | Bet | Cross-system automation creates substantially more value than transcription/extraction alone. | If the integration doesn't eliminate **≥50% of targeted double-entry work by week 6**, stop expanding integrations. | M |
| **109. Split compound voice notes across APIs** | Bet | One unstructured input can reliably initiate multiple system-specific actions without increasing correction burden. | If **<90% of pilot compound notes route correctly without manual reconstruction by week 6**, keep the product single-workflow. | M |
| **121. Real-time field audio processing** | Bet | Technicians will repeatedly use voice capture in noisy field conditions if latency and transcription quality are acceptable. | If **<80% of pilot technicians continue using voice capture or WER remains operationally unacceptable by week 6**, stop optimizing voice-first UX. | M |
| **151. Resolve field shorthand against CRM master data** | Bet | AI entity resolution removes enough lookup work to create step-change workflow value. | If correct entity resolution is **<93% on the expanded evaluation set by week 6**, stop autonomous matching and retain assisted search only. | M |
| **181. CRM/ticketing synchronization architecture** | Bet | Reliable cross-system execution increases workflow completion enough to justify integration complexity. | If automated synchronization doesn't eliminate **≥50% of targeted manual handoffs by week 6**, stop adding destination systems. | M |
| **184. Split voice notes into CRM + Jira records** | Bet | Multi-destination automation can execute accurately enough to outperform manual dispatch. | If **<90% of pilot splits produce correct destination records by week 6**, stop autonomous splitting. | M |
| **211. Low-confidence secure review queue** | Contract | HITL gating produces acceptable error rates without creating an operational bottleneck. | If reviewers bypass the queue or **>20% of work orders require manual review by week 6**, redesign the confidence model before scaling. | M |
| **241. Enterprise AI-use compliance monitoring** | Guardrails | Central AI governance materially reduces buyer security objections and shadow-AI risk. | If security stakeholders do not identify this capability as materially affecting deployment approval by week 6, stop building it as a standalone product surface. | M |

The review queue is especially important because the stated kill criteria explicitly includes users bypassing the confidence-gated review loop, while the current golden dataset contains only 14 rows.

### Horizon 3, Explore (3–6 months)

| Initiative | Strategy Component | What must be true first | Confidence |
|---|---|---|---|
| **Automated domain adaptation beyond basic correction retrieval** (future extension of 36–39) | Moat | Pilot data must prove that accumulated corrections create persistent accuracy gains and enough volume exists to justify specialized adaptation. | L |
| **Cross-tenant/federated learning implied by the Moat strategy** | Moat | Tenant-specific learning must work first; legal/data-rights review must establish what can legitimately be shared; measurable cross-tenant transfer must exist. | L |
| **Broader autonomous multi-system execution beyond CRM/Jira** | Bet | 106/109/181/184 must demonstrate reliable workflow completion and meaningful customer ROI before additional systems are added. | L |

This is intentionally a **small H3 portfolio**. The strategy already proposes federated learning as the encroachment defense, but the current data flywheel is only 8/20 and the network loop is 1/5.

### Unmapped (cut or rethink)

The dominant noise is **duplication**, not strategically unrelated ideas.

| Initiative | Why it's unmapped | Recommendation |
|---|---|---|
| **5, 8, 11, 14, 17, 20, 23, 26, 29, 32, 35** | Duplicate of #2 | **Cut duplicates**; retain #2 |
| **6, 9, 12, 15, 18, 21, 24, 27, 30, 33** | Duplicate of #3 | **Cut duplicates**; retain #3 |
| **7, 10, 13, 16, 19, 22, 25, 28, 31, 34** | Duplicate of #4 | **Cut duplicates**; retain #4 |
| **40, 43, 46, 49, 52, 55, 58, 61, 64, 67, 70** | Duplicate of #37 | **Cut duplicates**; retain #37 |
| **41, 44, 47, 50, 53, 56, 59, 62, 65, 68** | Duplicate of #38 | **Cut duplicates**; retain #38 |
| **42, 45, 48, 51, 54, 57, 60, 63, 66, 69** | Duplicate of #39 | **Cut duplicates**; retain #39 |
| **75, 78, 81, 84, 87, 90, 93, 96, 99, 102, 105** | Duplicate of #72 | **Cut duplicates**; retain #72 |
| **76, 79, 82, 85, 88, 91, 94, 97, 100, 103** | Duplicate of #73 | **Cut duplicates**; retain #73 |
| **77, 80, 83, 86, 89, 92, 95, 98, 101, 104** | Duplicate of #74 | **Cut duplicates**; retain #74 |
| **110, 113, 116, 119** | Duplicate of #107 | **Cut duplicates** |
| **111, 114, 117, 120** | Duplicate of #108 | **Cut duplicates** |
| **112, 115, 118** | Duplicate of #109 | **Cut duplicates** |
| **125, 128, 131, 134, 137, 140, 143, 146, 149** | Duplicate of #122 | **Cut duplicates** |
| **126, 129, 132, 135, 138, 141, 144, 147, 150** | Duplicate of #123 | **Cut duplicates** |
| **127, 130, 133, 136, 139, 142, 145, 148** | Duplicate of #124 | **Cut duplicates** |
| **155, 158, 161, 164, 167, 170, 173, 176, 179** | Duplicate of #152 | **Cut duplicates** |
| **156, 159, 162, 165, 168, 171, 174, 177, 180** | Duplicate of #153 | **Cut duplicates** |
| **157, 160, 163, 166, 169, 172, 175, 178** | Duplicate of #154 | **Cut duplicates** |
| **185, 188, 191, 194, 197, 200, 203, 206, 209** | Duplicate of #182 | **Cut duplicates** |
| **186, 189, 192, 195, 198, 201, 204, 207, 210** | Duplicate of #183 | **Cut duplicates** |
| **187, 190, 193, 196, 199, 202, 205, 208** | Duplicate of #184 | **Cut duplicates** |
| **215, 218, 221, 224, 227, 230, 233, 236, 239** | Duplicate of #212 | **Cut duplicates** |
| **216, 219, 222, 225, 228, 231, 234, 237, 240** | Duplicate of #213 | **Cut duplicates** |
| **217, 220, 223, 226, 229, 232, 235, 238** | Duplicate of #214 | **Cut duplicates** |
| **245, 248, 251, 254, 257, 260, 263** | Duplicate of #242 | **Cut duplicates** |
| **246, 249, 252, 255, 258, 261, 264** | Duplicate of #243 | **Cut duplicates** |
| **247, 250, 253, 256, 259, 262, 265** | Duplicate of #244 | **Cut duplicates** |

There is also an important **near-duplicate**:

Epic **#106 ("Bridge CRM work orders and downstream ticketing systems seamlessly")** and **#181 ("Bridge CRM work orders and downstream ticketing systems")** describe essentially the same strategic capability.

**Recommendation:** Merge them into one integration epic rather than fund both.

## Mapping Disagreements

**No disagreements, all user mappings stand.**

There are no visible `[User-mapped to: X]` annotations on the supplied initiative rows, so the component assignments above are mine, consistent with the instruction to choose the mapping where no user mapping is provided.

## Portfolio Assessment

**Most over-indexed horizon:** The portfolio is **over-indexed toward H1 implementation work**. What's missing is enough explicit H2 validation work around adoption, ROI, reliability, and buyer willingness to route operational data through QuietOps before scaling the architecture.

**H3 bet to protect:** If budget were cut, the **single H3 bet to protect is cross-tenant/domain learning—but only as a tightly bounded experiment**. If tenant-specific corrections demonstrably improve accuracy first, this is the exploratory path that could eventually change the defensibility story rather than merely add product capability.

**Initiative to kill today:** Kill **duplicate CRM/ticketing epic #181 as a separate initiative**. Merge it into #106 and eliminate the duplicated child backlog. More broadly, delete the repeated copies immediately—the backlog currently gives the appearance of far more strategic scope than the actual number of distinct bets warrants.

## Board Pitch

**Thesis (1 sentence):**

**The case:**
1. Why now:
2. What's defensible:
3. The economics:

**The risks:**
1. Trust / failure modes:
2. Scale / governance:
3. Competitive:

**The ask:**

## M1 Baseline vs. Now
*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:**

**Now:**
