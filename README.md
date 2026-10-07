# Real-Time Intelligence for Treasury and Wealth: A Strategy for Streaming-Backed AI Assistants and Human-Released Agents

Strategy paper for a bank's Enterprise Architecture and Payments leadership · October 7, 2026

---


## Executive summary

**The answer.** Build a streaming context engine (change data capture into an event backbone, stateful stream processing, a keyed serving store and a governed retrieval layer) as shared infrastructure, and put AI assistants and exception-handling agents on top of it under a human-release design. Sequence it: conversational analytics on fresh facts first, proactive alerts second, drafted actions third, executed actions within limits last. Fund it as a platform, measure it as a product, and govern it as a model from day one.

**Why now.** Five signals converged in the last six weeks.

1. **The industry is scoring maturity, and the gap between use cases and value is public.** The 2026 Evident AI Index, released October 6, ranks JPMorgan first for the fifth year and reports that only 12% of banks' reported AI use cases show measurable operational impact and about 1% disclose concrete financial returns, even as average scores rose 26% year over year and JPMorgan plans $19.8 billion of technology spend for 2026 ([Analytics Insight on the Evident AI Index, October 6, 2026](https://www.analyticsinsight.net/amp/story/news/jpmorgan-tops-banking-ai-rankings-for-5th-straight-year-2026)). The differentiator in 2027 will not be having assistants; it will be proving they changed an operational number.
2. **The winning design pattern for agents in banking has been named.** At Sibos 2026 in Miami this month, BNY, BNP Paribas, Deutsche Bank, HSBC and Citi showed production agents in exception handling, and every one followed the same sequence: the AI proposes, deterministic rules validate against scheme standards, a person releases. BNY's payment-repair agent handles over 10% of its global repair volume; BNP Paribas automated 80 to 85% of one trade flow within weeks ([Sibos 2026 recap](https://www.beri.net/article/sibos-2026-recap-ai-agents-payment-repair-trade-exceptions-iso-20022-human-release), [The Fintech Times](https://thefintechtimes.com/sibos-2026-day-two-banks-put-ai-agents-to-work-but-keep-the-judgement-for-people)).
3. **Competitors are shipping treasury intelligence on fresh data.** Bank of America launched Payments Insights inside CashPro on September 28, with CashPro processing 213 million payments in the first half of 2026, up 10% ([FinTech Global, September 28, 2026](https://fintech.global/2026/09/28/bank-of-america-turns-to-ai-to-improve-treasury-payments/)). J.P. Morgan Payments opened an API in April giving treasury platforms' AI agents near-real-time access to balances and transactions ([TMI, April 29, 2026](https://treasury-management.com/news/atlar-first-to-use-j-p-morgan-payments-new-api-to-connect-ai-agents-to-banking-data-in-seconds)).
4. **Money itself moved to real time.** FedNow's transaction limit rose to $10 million in November 2025; the network passed 1,800 participants including seven of the ten largest US banks, moving $271 billion in the first quarter of 2026, while RTP processed 128 million transactions worth $480 billion in the same quarter ([Digital Transactions, July 2026](https://www.digitaltransactions.net/fednow-marks-a-third-anniversary-tally-at-more-than-1800-banks-and-credit-unions/)). An assistant that reasons from last night's balances is now wrong by design.
5. **The regulatory frame shifted toward governance-by-design.** US agencies rescinded the 2011 model-risk guidance on April 17, 2026, explicitly excluded generative and agentic AI from the new framework as "novel and rapidly evolving," and signaled a request for information on banks' AI deployment ([Orrick, April 2026](https://www.orrick.com/en/Insights/2026/04/Agencies-Overhaul-Model-Risk-Management-Guidance-for-Banks-Heres-What-Changed)). The EU's AI Omnibus Regulation, in force since July 27, 2026, moved stand-alone high-risk obligations to December 2027 while Article 50 transparency duties took effect August 2, 2026 ([SBS Software](https://sbs-software.com/insights/ai-data-in-banking/eu-ai-act-delay-banks-compliance/)). And on October 6 the CEO of the largest US bank said cyber risk "went up 10-fold" after frontier models exposed vulnerabilities no one knew about ([PYMNTS, October 6, 2026](https://www.pymnts.com/news/artificial-intelligence/2026/jpmorgan-ceo-warns-ai-risks-jumped-tenfold-after-mythos/)). Governance is no longer a constraint on the design; it is the design.

**The economics, in one line.** The streaming context engine is a platform cost that compounds: each assistant, alert and agent built on it is cheaper than the last, and the same fresh, reconciled, entitled facts serve treasury, wealth, fraud and operations. Measured as a single product it looks expensive; measured as the foundation for a portfolio it is the only path that scales. The investment model in Section 6 is parameterized so leadership can test it against the firm's own numbers.

**What we ask leadership to decide.** Five things, in Section 15: fund the platform as shared infrastructure; adopt the human-release design as policy for any agent that moves money; sequence capabilities by risk tier; commit to value measurement that would survive the Evident test; and name a single accountable sponsor for AI governance, which the research links to higher returns.

---

## 1. Situation: what changed in 2026

### 1.1 The maturity race is being measured, and the value gap is visible

The Evident AI Index evaluates 50 major banks on more than 70 indicators across talent, innovation, leadership and transparency. Its 2026 edition, out this week, found industry scores up 26% year over year, adoption accelerating at nearly three times the 2023 to 2025 pace, and a stark gap between activity and outcome: 12% of reported use cases with measurable operational impact, roughly 1% of banks disclosing financial returns from individual implementations ([Analytics Insight, October 6, 2026](https://www.analyticsinsight.net/amp/story/news/jpmorgan-tops-banking-ai-rankings-for-5th-straight-year-2026)). JPMorgan leads for the fifth consecutive year; Capital One, RBC and Commonwealth Bank follow.

Earlier reporting put JPMorgan's 2026 technology budget near $19.8 billion with about $1.2 billion of additional AI-related investment, and quoted the CFO that machine-learning analytics are contributing to revenue and operational improvement across segments ([AI News, March 5, 2026](https://www.artificialintelligence-news.com/news/jpmorgan-expands-ai-investment/)). Firm-wide, LLM Suite reaches roughly 250,000 employees with about half using it daily, on OpenAI and Anthropic models refreshed on an eight-week cycle ([CeFPro](https://connect.cefpro.com/article/view/inside-jpmorgan-llm-suite-as-ai-agents-spread-across-the-bank)); 450-plus use cases are in production and about $2 billion in annual savings is attributed to AI ([Forbes, July 2026](https://www.forbes.com/sites/bernardmarr/2026/07/01/how-jpmorgan-chase-is-building-the-ai-powered-bank-of-the-future/)).

**So what.** Leadership in the index does not resolve the value question; it raises the bar for proving it. The next tier of value is operational: assistants and agents that change how money and exceptions move, with numbers that can be disclosed.

### 1.2 The agent pattern that works has been shown in production

Sibos 2026 is the clearest evidence this year of what banks are actually running. Five institutions demonstrated agents in exception handling: payment repair, trade document checking, dispatch between workflow steps. Every deployment shared one architecture: AI proposes a correction; deterministic rules validate it against ISO 20022, Swift or SEPA requirements; a human approves before release. BNY's "digital employee" on its Eliza platform handles more than 10% of global payment-repair volume; BNP Paribas reached 80 to 85% automation on one securities trade flow within weeks; HSBC's Smart Checking validates trade documents; Deutsche Bank's Ada framework serves lending operations; Citi discussed regulatory oversight of agent deployment ([Sibos 2026 recap](https://www.beri.net/article/sibos-2026-recap-ai-agents-payment-repair-trade-exceptions-iso-20022-human-release)).

**So what.** The debate about whether agents belong in payments is over. The design question is settled too: judgment stays with people, validation is deterministic, and the agent's job is to propose. That pattern depends on the agent seeing the current state of the payment, not yesterday's.

### 1.3 Treasury intelligence is a competitive front, and it runs on fresh data

Bank of America's Payments Insights, launched September 28 inside CashPro, analyzes payment efficiency, benchmarks clients against peers, and visualizes cross-border flows; CashPro processed 213 million payments in the first half of 2026, up 10% year over year ([FinTech Global](https://fintech.global/2026/09/28/bank-of-america-turns-to-ai-to-improve-treasury-payments/)). J.P. Morgan Payments' December 2023 prototype of a conversational treasury analytics assistant described a path to "self-driving treasury" within treasurer-defined parameters ([J.P. Morgan Payments](https://www.jpmorgan.com/insights/payments/data-intelligence/genai-virtual-analytics-assistant-treasury)); its April 2026 API gives treasury platforms' agents near-real-time balances and transactions, with the first partner connecting accounts "in seconds, with no IT development" ([TMI](https://treasury-management.com/news/atlar-first-to-use-j-p-morgan-payments-new-api-to-connect-ai-agents-to-banking-data-in-seconds)). The firm's developer guidance frames APIs as "the data foundation" and emphasizes current balances over end-of-day reports ([developer.payments.jpmorgan.com](https://developer.payments.jpmorgan.com/blog/ai-ml/rethinking-treasury-ai-apis)). An IMF note this year examines how agentic AI will reshape payments, including the policy questions it raises ([IMF Notes 2026/004](https://www.elibrary.imf.org/view/journals/068/2026/004/article-A001-en.xml)).

**So what.** Clients will compare assistants on whether the number is right now. Freshness becomes table stakes in treasury, and the bank that owns the real-time data path owns the client relationship through the agent.

### 1.4 Money moves in real time, at corporate scale

FedNow's limit rose from $500,000 at launch to $1 million in March 2025 and $10 million in November 2025. By July 2026 more than 1,800 banks and credit unions participate, including seven of the ten largest; 2025 volume was $853 billion across 8.4 million transactions, and the first quarter of 2026 alone moved $271 billion. RTP processed 128 million transactions worth $480 billion in that quarter ([Digital Transactions](https://www.digitaltransactions.net/fednow-marks-a-third-anniversary-tally-at-more-than-1800-banks-and-credit-unions/)).

**So what.** A $10 million instant payment changes a corporate cash position in seconds. Intraday liquidity decisions made on batch data carry real cost, and the client will know.

### 1.5 The regulatory frame moved toward governance-by-design

- **US model risk.** On April 17, 2026, the agencies rescinded SR 11-7 and its OCC and FDIC equivalents. The new guidance applies most to institutions above $30 billion in assets, is explicitly non-enforceable, narrows the definition of a model, replaces prescriptive validation with a materiality framework, and **excludes generative and agentic AI from its scope**, directing banks to manage those risks through broader governance and signaling a request for information on AI deployment ([Orrick](https://www.orrick.com/en/Insights/2026/04/Agencies-Overhaul-Model-Risk-Management-Guidance-for-Banks-Heres-What-Changed)). The practical effect: there is no prescriptive rulebook for generative and agentic AI in US banking right now, which means the bank's own governance design is what examiners will evaluate.
- **EU AI Act.** The AI Omnibus Regulation entered force July 27, 2026, moving stand-alone high-risk obligations to December 2, 2027 and embedded high-risk to August 2, 2028, while Article 50 transparency obligations took effect August 2, 2026 and DORA has applied since January 2025. The guidance to banks is to use the window to build data governance, lineage, documentation, human oversight and deployment controls into AI systems from the outset ([SBS Software](https://sbs-software.com/insights/ai-data-in-banking/eu-ai-act-delay-banks-compliance/)).
- **Cyber.** JPMorgan's CEO said on October 6 that cyber threats "went up 10-fold" after a frontier model exposed previously unknown vulnerabilities, and that the firm's response is to "roll up our sleeves and go to work to fix it" ([PYMNTS](https://www.pymnts.com/news/artificial-intelligence/2026/jpmorgan-ceo-warns-ai-risks-jumped-tenfold-after-mythos/)).

**So what.** Three implications. Governance has to be designed in, because there is no external template to point to. Lineage, human oversight and deployment controls are the same controls the EU will require in 2027, so building them now is not early. And any agent with access to payment systems is now a cyber surface; least privilege and human release are security controls, not only compliance ones.

### 1.6 The infrastructure trend lines point the same way

Data streaming in 2026 is consolidating around Kafka-native platforms, moving storage to object stores with Iceberg as the "store once" layer, pulling analytics into the streaming layer, demanding zero-data-loss SLAs for financial workloads, respecting regional data sovereignty, and positioning streaming as the "context engine" that feeds operational facts to AI agents at the right time ([Kai Waehner, December 2025](https://www.kai-waehner.de/blog/2025/12/10/top-trends-for-data-streaming-with-apache-kafka-and-flink-in-2026/)). AWS's 2026 guidance on agentic AI names the same three patterns: streaming features to inference to action; event-driven agent invocation with pre-assembled context; change data capture keeping agent memory current ([AWS](https://aws.amazon.com/blogs/big-data/powering-agentic-ai-with-real-time-streaming-data-on-aws/)). The 2025 DORA report found 90% of organizations run an internal platform and that platform quality correlates directly with the ability to get value from AI, while AI without foundations raises throughput and hurts stability ([Google Cloud](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)).

**So what.** The streaming context engine is not an exotic bet. It is where the ecosystem, the cloud providers and the delivery research have converged.

---
## 2. The core insight

Two things are true at once, and the strategy follows from holding both.

**Freshness is now a correctness property, not a performance property.** When a $10 million instant payment can change a position in seconds, an assistant answering from a nightly batch is not slow; it is wrong. The value of an assistant in treasury is bounded by the age of the facts it reasons from.

**Judgment stays human, and the architecture has to make that cheap.** Every production agent shown at Sibos this month proposes, is validated by deterministic rules, and is released by a person. That pattern is only economical if the human sees the right exception with the right context at the right time, which is a data-flow problem before it is a model problem.

Put together: **the asset is not the assistant. The asset is a governed, fresh, reconciled, entitled stream of operational facts that any assistant or agent can read, and a release path that keeps people in charge of money.** Assistants and agents are products on top of it, and they will be replaced as models improve; the context engine and the release path are the durable investment.

This reframing changes three decisions. Funding: the engine is platform infrastructure, not a feature budget. Sequencing: facts before alerts before actions. Measurement: freshness, correctness and release-path metrics are leading indicators of the business outcomes, and they are the numbers that would survive the Evident test.

---

## 3. Where the value is

Public numbers set the scale; the firm's own volumes set the size. Each pool below is described by its mechanism, the public evidence that it is real, and the firm-specific inputs needed to size it. No invented dollar totals.

### 3.1 Treasury: intraday liquidity and payment exceptions

- **Mechanism.** A treasurer who sees the position now, with the as-of time, makes sweep, funding and investment decisions on current data rather than end-of-day. An assistant that answers "what is my position" from a streamed serving store, and alerts when a liquidity pattern fires, moves decisions earlier and reduces idle balances and overdraft costs.
- **Evidence it is real.** Instant payment volumes and limits above; competitor launches (Payments Insights) and J.P. Morgan's own agent API; the 2023 prototype's "days to seconds" framing for analytics ([J.P. Morgan Payments](https://www.jpmorgan.com/insights/payments/data-intelligence/genai-virtual-analytics-assistant-treasury)).
- **Inputs to size it.** Number of corporate clients on the platform; average intraday balance variance; current time-to-answer for a position query (the prototype article implied days for custom analytics); share of clients making intraday funding decisions; fee and balance economics per client.
- **Leading indicators.** Freshness p95; time-to-answer; share of position queries answered from the assistant; alert action rate.

### 3.2 Payment operations: exception handling with human release

- **Mechanism.** Repairs, returns, sanctions-screening escalations and document checks are high-volume, rules-heavy, human-released work. An agent that proposes the fix with the current state of the payment, validated by scheme rules, cuts handling time and error rate while a person keeps the release.
- **Evidence.** BNY's agent at more than 10% of global repair volume; BNP Paribas at 80 to 85% on one flow; HSBC's document validation ([Sibos 2026](https://www.beri.net/article/sibos-2026-recap-ai-agents-payment-repair-trade-exceptions-iso-20022-human-release)).
- **Inputs.** Exception volumes by type; handling time per exception; error and rework rates; staffing cost; straight-through-processing rate.
- **Leading indicators.** Proposed-fix acceptance rate; handling time; rework rate; share of volume touched by the agent.

### 3.3 Wealth: advisor preparation and client context

- **Mechanism.** Advisors preparing for client meetings need current holdings, transactions and interactions, plus research. A context engine that keeps client facts fresh and a retrieval layer over approved content cuts preparation time and improves the conversation.
- **Evidence.** Connect Coach is publicly described as assisting Private Bank advisors with meeting preparation, idea generation and research synthesis ([reruption.com](https://reruption.com/en/knowledge/industry-cases/jpmorgans-llm-suite-turbocharging-wealth-advisor-productivity)); a peer firm's public figures for an advisor assistant include 98% advisor-team adoption and follow-ups moving from days to hours ([OpenAI on Morgan Stanley](https://openai.com/index/morgan-stanley/)).
- **Inputs.** Advisor count; preparation time per meeting; meetings per advisor; share of time on content search; client satisfaction and retention sensitivity.
- **Leading indicators.** Preparation time; adoption; edit rate on drafted communications; client response time.

### 3.4 Fraud and anomaly detection

- **Mechanism.** Pattern detection on the stream (velocity, impossible travel, account takeover sequences) feeds both automated controls and agent-assisted investigation; the same stream that serves the assistant serves the fraud models.
- **Evidence.** Real-time transaction monitoring is among the named AI use cases at scale ([AI News](https://www.artificialintelligence-news.com/news/jpmorgan-expands-ai-investment/)); FedNow added a network intelligence API for fraud prevention ([Digital Transactions](https://www.digitaltransactions.net/fednow-marks-a-third-anniversary-tally-at-more-than-1800-banks-and-credit-unions/)).
- **Inputs.** Loss rates; false-positive costs; investigator time; detection latency today.
- **Leading indicators.** Detection latency; precision; investigator time per case.

### 3.5 The platform multiplier

The four pools share the engine. Capture, backbone, processing, serving store, retrieval, lineage and the release path are built once. The second product on the platform pays a fraction of the first's cost; the fourth is nearly marginal. This is the economic argument for funding the engine as infrastructure, and it is what the DORA finding about platform quality predicts ([Google Cloud](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)).

### 3.6 The cost of inaction

- **Client attrition in treasury.** Competitors are shipping fresh-data intelligence inside their portals now; the agent API race means third-party treasury platforms will sit between the bank and the client unless the bank's own context engine is better.
- **Stranded AI spend.** The Evident finding (12% measurable impact) is the industry's current state. Assistants on stale data add to the 88%.
- **Regulatory exposure.** Building assistants without lineage, oversight and deployment controls now means rebuilding for the EU's 2027 obligations and for whatever the US request for information produces.
- **Cyber surface.** Agents attached to payment systems without least privilege and human release are the vulnerabilities the CEO was describing.

---

## 4. Strategic options

Three options were considered. Each is evaluated against seven criteria: freshness, correctness assurance, time to first value, platform leverage, governance fit, cyber posture, and cost shape.

### Option A: Assistant on existing batch and warehouse data

Put a retrieval layer and an LLM over the warehouse and document stores as they are; refresh on the existing schedule.

- **Freshness:** hours. Wrong by design for treasury; acceptable for research and policy content.
- **Correctness:** depends on warehouse quality; no reconciliation problem because there is no projection.
- **Time to first value:** fastest; months.
- **Platform leverage:** low; each assistant re-integrates.
- **Governance:** manageable; the risks are groundedness and entitlement, not freshness.
- **Cyber:** read-only, limited surface.
- **Cost:** low build; per-query warehouse cost grows with use.
- **Verdict:** right for a wealth research assistant; wrong as the foundation for treasury or any agent.

### Option B: Assistant on per-request APIs

Have the assistant call systems of record and existing APIs (balances, payment status) at question time.

- **Freshness:** current, where APIs exist with adequate latency and entitlement. J.P. Morgan's own balance APIs show this is the provider-side direction.
- **Correctness:** inherits the source's; no projection drift.
- **Time to first value:** fast where APIs exist; slow where they must be built or where sources can't take the load.
- **Platform leverage:** moderate; APIs are reusable, but running aggregates, pattern detection and fan-out are not available.
- **Governance:** good; entitlement at the API.
- **Cyber:** each API is a surface; agents calling many APIs need tight scoping.
- **Cost:** low build; load on sources; no 24/7 processing.
- **Verdict:** the right default for point lookups where fresh APIs exist. It cannot do alerts, running balances across sources, or exception context assembled from several events. It is a component of the answer, not the answer.

### Option C: Streaming context engine with human-released agents

Change data capture into an event backbone, stream processing for projections and patterns, a serving store and retrieval layer, assistants and agents on top, with deterministic validation and human release for actions.

- **Freshness:** seconds, with as-of times per source.
- **Correctness:** requires exactly-once projections, event time, per-key ordering and scheduled reconciliation; engineered, not inherited.
- **Time to first value:** slower to first demo (a quarter of enablers); faster for every product after the first.
- **Platform leverage:** highest; one engine for treasury, operations, wealth and fraud.
- **Governance:** strongest when designed in: lineage from source event to answer, tiering, evaluation gates, release path.
- **Cyber:** the backbone and processing are internal surfaces that must be locked down; agents get least privilege and human release.
- **Cost:** 24/7 processing cost plus a platform team; offset by removing per-request warehouse load and by the multiplier.
- **Verdict:** the only option that supports alerts, agents and a portfolio of assistants. It must be sequenced and reconciled, and it should use Option B's APIs where they already exist rather than re-streaming them.

### Comparison

| Criterion | A: Batch | B: APIs | C: Streaming engine |
| --- | --- | --- | --- |
| Freshness | Hours | Current where APIs exist | Seconds, all sources |
| Correctness assurance | Inherited | Inherited | Engineered (reconciliation required) |
| Time to first value | Months | Weeks to months | One quarter of enablers, then compounding |
| Alerts and pattern detection | No | No | Yes |
| Agent context assembly | No | Partial | Yes |
| Platform leverage | Low | Moderate | High |
| Governance by design | Partial | Good | Strongest |
| Cyber surface | Smallest | Per API | Internal backbone plus scoped agents |
| Cost shape | Low build, per-query | Low build, source load | Platform plus 24/7, multiplier |

### Recommendation

**Option C as the strategy, with B as a component and A for content that doesn't change.** Research, policy and approved language stay on scheduled refresh or are preloaded. Point lookups use fresh APIs where they exist. Everything that needs running state, patterns, fan-out or assembled exception context runs on the engine. Capabilities ship in risk order: facts, alerts, drafted actions, executed actions.

---

## 5. The recommended design, in one page

The architecture and the delivery plan are detailed in the two companion documents. The strategic shape:

**Layer 1: Capture and backbone.** Change data capture from the systems of record (SQL Server first, Oracle as its own program) into Kafka-compatible topics keyed by entity, with a schema registry, data contracts, dead-letter handling and retention for replay. Zero-data-loss configuration for financial topics.

**Layer 2: Processing.** Stateful stream processing computing effectively-once projections (balances, positions, payment status), detecting patterns deterministically, enriching with reference data, and embedding only the unstructured content that needs similarity search.

**Layer 3: Stores.** A keyed serving store for current facts with as-of times and source event IDs; a vector index for documents; an Iceberg lakehouse on object storage for history and replay; a scheduled reconciliation that compares projections to the ledger.

**Layer 4: Serving and governance.** A retrieval service that enforces entitlements before ranking; an LLM gateway with logging, model inventory and evaluation; prompt assembly that passes numbers as structured fields the model presents and never computes.

**Layer 5: Products.** Conversational analytics; proactive alerts with rate limits; drafted actions with human approval; executed actions within limits, dual control and a kill switch. The Sibos sequence: AI proposes, rules validate, a person releases.

**Across all layers:** classification at the source, lineage from event to answer, evaluation gates in the Definition of Done, risk tiering, supervision logging and retention. These are the EU's 2027 obligations and the US agencies' stated expectation of "broader governance practices," built once.

---
## 6. Economics: a parameterized model

No dollar totals are invented here. The model below is structured so that leadership can enter the firm's own numbers and read the result. The shape of the economics is the point: a platform cost that is mostly fixed, product value that is mostly variable, and a multiplier as products accumulate.

### 6.1 Investment

| Line | Shape | What drives it | Typical range for a first program (order of magnitude, to be replaced by the firm's estimates) |
| --- | --- | --- | --- |
| Platform team | Fixed, annual | 6 to 8 engineers plus an SRE and a product owner | One team-year per year |
| Assistant product team | Fixed, annual | 6 to 8 including PO, design, evaluation engineer | One team-year per year per product |
| Governance enabling | Part-time, annual | Risk, compliance and model-risk partners plus one engineer | A fraction of a team-year |
| Capture and backbone run cost | Continuous | Connector workers, broker count, storage, retention | Scales with sources and retention, not with users |
| Stream processing run cost | Continuous | Processing units, parallelism, state size | Scales with event rate and state; autoscaling bounds it |
| Serving store and index | Per request plus storage | Hot keys, document volume | Scales with users and content |
| Model inference | Per token | Prompt length, generation length, volume | Scales with users; prefix caching and small models for classification bound it |
| Lakehouse storage | Per GB | History retained | Cheap; grows linearly |
| Change management | Fixed per cohort | Enablement, manager briefings, communications | Scales with cohorts, not with software |

### 6.2 Value

| Pool | Value driver | Formula shape | Firm inputs |
| --- | --- | --- | --- |
| Treasury liquidity | Reduced idle balances and overdraft cost from earlier, better-informed decisions | clients × share using the assistant × average intraday balance improvement × funding spread | Client count, balance variance, spread, adoption curve |
| Treasury fees and retention | Retained and won clients from a better treasury experience | clients at risk × retention lift × revenue per client | Churn baseline, competitor launches, revenue per client |
| Exception handling | Reduced handling time and rework with human release | exceptions × handling-time reduction × loaded cost + rework reduction × cost per rework | Exception volumes, handling times, rework rates (Sibos benchmarks: 10% of repair volume, 80 to 85% on one flow) |
| Advisor productivity | Preparation time returned to client work | advisors × meetings × preparation-time reduction × value of advisor hour | Advisor count, meeting load, time study |
| Fraud | Earlier detection and fewer false positives | loss rate reduction × volume + investigator time saved | Loss and false-positive baselines |
| Platform multiplier | Avoided integration cost for each subsequent product | (first-product integration cost) × (number of later products) × (reuse factor) | Product roadmap |

### 6.3 Timing

- **Quarter 1:** platform investment with no product value; the demo is correct data and a reconciliation report.
- **Quarter 2:** conversational analytics in canary; first measurable time-to-answer and freshness; alerts piloted.
- **Quarters 3 to 4:** alerts at scale; drafted actions piloted; second product (operations or wealth) begins on the platform at a fraction of the first's cost.
- **Year 2:** executed actions within limits where the pilot ran clean; third and fourth products; platform cost per product falls.

### 6.4 Sensitivities to test

1. **Adoption.** The research says adoption follows workflow redesign and manager readiness, not features. Model adoption at half the planned curve and confirm the case still holds.
2. **Processing cost.** Run cost scales with event rate; a source with heavy end-of-day bursts needs headroom. Model at 1.5 times the base estimate.
3. **Reconciliation findings.** Early drift is normal; each finding costs engineering time. Budget it.
4. **Inference cost.** Prompt length is the lever; model it at twice the base and show the mitigations (prefix caching, structured facts, smaller models for classification).
5. **The multiplier.** The case rests on a second and third product arriving. If the roadmap has only one, Option B may be cheaper. Name the second product before funding the first.

### 6.5 What we would need to believe

- That treasury clients value freshness enough to change behavior (evidence: competitor launches, instant payment growth, the firm's own API direction).
- That exception handling with human release yields the Sibos-scale automation in the firm's flows (evidence: five banks' production numbers; the firm's own exception volumes decide the size).
- That the platform will host at least three products within two years (evidence: the four pools above share the engine; the roadmap must name them).
- That governance-by-design costs less than governance-by-retrofit under the EU's 2027 obligations and the US request for information (evidence: the regulatory timeline; the cost of rebuilding lineage after the fact).

---

### 6.6 Unit economics the sponsor should ask for every quarter

| Unit | Definition | Why it matters |
| --- | --- | --- |
| Cost per answered question | (inference + retrieval + serving-store reads + allocated platform) ÷ answered questions | Falls with prefix caching, structured facts and adoption; rising cost per answer means prompt bloat or thin adoption |
| Cost per alert delivered | (processing + alerting + allocated platform) ÷ alerts delivered, with precision beside it | An alert that isn't acted on is pure cost |
| Cost per exception handled with the agent | (inference + validation + allocated platform) ÷ exceptions, against the human-only baseline | The Sibos-style productivity case in one number |
| Platform cost per product | Total platform run cost ÷ products live | The multiplier made visible; should fall each half-year |
| Freshness cost | Marginal run cost of moving a source from scheduled to streamed | Decides which sources earn the stream |

### 6.7 A worked illustration, with the assumptions exposed

To show the shape, not the size, take one treasury client segment and one exception flow, with placeholder inputs the firm should replace.

- **Treasury segment.** 2,000 clients; 40% adopt within a year; each adopting client improves average intraday idle balance by a modest amount of their daily variance; a funding spread applied to that improvement; plus a retention lift on a small share of at-risk clients. Every one of those numbers is an input, and the output is linear in each, which is why adoption and the spread dominate the sensitivity.
- **Exception flow.** 400,000 exceptions a year in one flow; the agent proposes fixes on 60% of them in year one (the Sibos range is 10% of global repair volume at one bank and 80 to 85% on one flow at another); handling time falls by a third on those; rework falls by a quarter. The output scales with volume and the handling-time reduction, which is why the baseline time study is the first thing to commission.
- **Platform.** One platform team plus run cost in year one; the second product adds a product team but reuses capture, backbone, processing, stores, retrieval and governance, so its integration cost is a fraction of the first's.

The honest reading of such a model: year one is investment; year two turns on the second product and on adoption; the sensitivities to run are adoption at half the curve and processing cost at 1.5 times. The case should be presented with those two sensitivities on the same page as the base.

---

## 7. Operating model

### 7.1 Structure

Three team types, following the platform-and-stream-aligned pattern that the delivery research associates with AI value: a streaming platform team owning capture, backbone, processing, stores and reconciliation as a shared service with self-service onboarding; stream-aligned product teams owning each assistant or agent and its outcomes; and a governance enabling team owning the evaluation framework, tiering, entitlement tests and the model-risk relationship until the product teams can run them.

### 7.2 Accountability

- **A single accountable sponsor for AI governance,** senior enough to decide phase gates and to own the firm's answer to the regulators' request for information. The research links senior ownership of AI governance to higher returns.
- **Phase gates as decisions on evidence,** not dates: parallel run, shadow verification, canary, alerts, drafted actions, executed actions.
- **Value tracking by a function outside delivery,** so the numbers that go to the index and the regulator were not produced by the team being measured.

### 7.3 Governance in the delivery path

Risk tier assigned when a story is refined; the evaluation gate in the Definition of Done; review path by tier; evidence linked from the work item; a decision log. This is the mechanism that lets governance accelerate delivery rather than block it, and it is the practice the new US guidance's "broader governance" language leaves to the bank to define.

### 7.4 Change management as a gated workstream

Stakeholder groups mapped (users, their managers, engineers, control partners, operations, executives); an adoption sequence planned per group; manager readiness as a condition for launching a cohort; pacing against the total change the user population is absorbing; communications by audience answering what changes, when, and where to go if it's wrong. The change research is explicit that saturation and unprepared managers are the main failure modes.

### 7.5 The release path as policy

For any agent that proposes an action affecting money, records or client communications: AI proposes; deterministic rules validate against scheme and policy; a named person releases; limits are enforced by the system of action, not the prompt; dual control above thresholds; everything traced; a kill switch tested. This is written as firm policy, not a design preference, because it is what every bank at Sibos converged on and what the cyber environment demands.

---

## 8. Risks and controls

| Risk | Why it matters now | Control |
| --- | --- | --- |
| **Confident wrong numbers** | A fresh pipeline can deliver wrong figures fast; a wrong balance in an assistant's voice is a client and conduct event | Effectively-once projections; event time; per-key ordering; scheduled reconciliation to the ledger; the model presents numbers and never computes; sampled-answer checks in evaluation |
| **Agents as a cyber surface** | The CEO's "10-fold" remark; frontier models exposing unknown vulnerabilities; agents attached to payment APIs | Least privilege per task; human release; limits in the payments system; prompt-injection cases in evaluation; retrieved text treated as data; kill switch |
| **Governance gap for generative and agentic AI** | US guidance excludes them and leaves "broader governance" to the bank; an RFI is coming; EU high-risk obligations land in 2027 | Model inventory; evaluation gates; tiering; lineage from event to answer; human oversight documented; a single accountable sponsor |
| **Oracle capture difficulty** | Practitioner reports this year describe Oracle CDC as a program, not a connector: type handling, log retention, failover | Sequence Oracle second; type tests and reconciliation before production; generated configuration as a contract |
| **Change saturation** | One in four transformations succeeds; 41% of managers ready | Portfolio view of change on the user population; cohort pacing; manager readiness as a gate |
| **Value not measured** | 12% of use cases show impact; 1% disclose returns | Leading indicators from sprint 3; value tracked by a function outside delivery; the disclosure standard set at the start |
| **Vendor and platform lock-in** | Ecosystem consolidation; managed services | Open formats (Kafka protocol, Iceberg, OpenAPI); exit paths documented; contracts owned by the bank |
| **Alert fatigue** | Trust lost in the first week of alerts | Precision targets; rate limits; dedup; storm testing before pilot |
| **Data sovereignty and residency** | Regional compliance drives deployment decisions | Regional deployment of backbone and processing; classification register; residency in contracts |
| **AI-assisted program artifacts entering records unverified** | Plans, risks and status drafted by tools | Draft space; source-checked line by line; named approver; nothing sensitive in unauthorized tools |

---

## 9. Roadmap: three horizons

### Horizon 1 (quarters 1 to 2): the engine and the first fresh facts
- Scope, classification and contracts; SQL Server capture; backbone with registry; balance and status projections; serving store; reconciliation; retrieval with entitlements; evaluation framework; parallel run; shadow verification; canary of conversational analytics for one client segment.
- **Exit criteria:** freshness p95 within target; reconciliation within tolerance for an agreed period; zero entitlement failures; sampled-answer correctness at threshold; canary cohort's time-to-answer and satisfaction measured.

### Horizon 2 (quarters 3 to 4): proactive, and the second product
- Oracle capture as its own phased program; CEP patterns and the alerting service; drafted actions with human approval in pilot; the second product (payment exception handling with human release, or advisor context) onboarded to the platform; value tracking disclosed internally in the index's terms.
- **Exit criteria:** alert precision and false-alarm targets met; drafted-action acceptance rate and zero unapproved executions; second product live at a measured fraction of the first's integration cost.

### Horizon 3 (year 2): acting within limits, and the portfolio
- Executed actions within treasurer-defined limits, dual control and a kill switch, only where drafted actions ran clean; third and fourth products; the engine as the firm's context layer for agents, with regional deployments where sovereignty requires; readiness for the EU's December 2027 high-risk obligations and the US RFI response.
- **Exit criteria:** executed-action reconciliation at 100%; platform cost per product falling; governance artifacts complete against the EU obligations; value disclosed.

---

## 10. The client's day: two personas the design must serve

Strategy that doesn't change a specific person's morning is a slide. These two days are the test of every capability in the roadmap.

### 11.1 The corporate treasurer, today and after

**Today.** Logs into the bank portal and an ERP; pulls end-of-day balances and an intraday report that is an hour old; reconciles three sources in a spreadsheet; decides a sweep by late morning on data that may be missing the morning's instant receipts; learns of a rejected payment from a supplier's call; asks the bank's service desk for analytics that arrive in days.

**After Horizon 1.** Asks the assistant for the position across accounts and sees each figure with the time it was true and the source; the instant receipt from 10:00 is included at 10:10; the answer cites the serving store, not a model's arithmetic.

**After Horizon 2.** Receives one alert, not twelve, when a liquidity pattern fires, listing the triggering wires and the as-of time; asks for a drafted sweep; reviews and approves it in the payments system under limits the treasurer set.

**After Horizon 3.** Lets the assistant execute sweeps within pre-set limits and dual control above them, and spends the time on funding strategy. This is the "self-driving treasury within treasurer-defined parameters" that the bank's own 2023 prototype described, reached by evidence rather than ambition.

**What the treasurer will ask the bank, and the answer the design gives.** "How do I know the number is right?" The as-of time, the source, and the hourly reconciliation to the ledger. "What if it's wrong?" A one-touch report path, a same-week fix, and a human who still releases money. "Who else can see this?" Entitlements enforced where the data is retrieved, with zero-tolerance tests.

### 11.2 The Private Bank advisor, today and after

**Today.** Prepares for a client meeting from holdings reports, CRM notes, research and email threads across several systems; spends a large part of the morning searching for the right content and the latest interaction; drafts follow-ups by hand under supervision rules.

**After.** Asks for the client's current context and gets holdings and interactions fresh to within minutes, research retrieved from approved sources with citations, and a drafted follow-up in approved language that the advisor edits and sends. The firm's existing advisor tool already serves preparation, ideas and research synthesis; the context engine makes its facts current and its drafts grounded.

**What the advisor's supervisor will ask.** "Is every communication supervised and retained?" Yes, by design, through the gateway and the logging standard. "Can the assistant say something it shouldn't?" The approved-language corpus is preloaded, prohibited statements are checked at output, and the advisor sends.

---

## 11. Build, buy, partner

The engine has well-defined layers, and the make-or-buy answer differs by layer.

| Layer | Recommendation | Reasoning |
| --- | --- | --- |
| Capture | Buy the connector (Debezium, open source, or a managed CDC service); build the contracts and the reconciliation | The connector is commodity; the correctness program around it is the bank's |
| Backbone | Managed Kafka-compatible service with the bank's security and residency configuration | Ecosystem consolidation favors Kafka-native platforms; the bank should own topics, contracts and access, not brokers |
| Processing | Managed stream processing where tuning exposed is sufficient; self-managed on Kubernetes where the platform team already exists | Engineers on the jobs, not the cluster, unless the firm has a platform team for it |
| Stores | Managed serving store, vector index and lakehouse in open formats (Iceberg, OpenAPI) | Exit paths matter more than any vendor's features |
| Model layer | Model-agnostic gateway in front of managed foundation models and internal hosting | The firm already runs multiple providers on an eight-week refresh; the gateway is the control point |
| Retrieval and evaluation | Build | This is where the bank's entitlements, classifications, scenario sets and judgment live; it is the differentiator |
| Assistants and agents | Build on the platform; partner where a third-party treasury platform owns the client workflow | The April agent API shows the bank can be the data provider to partners' agents as well as the owner of its own |
| Change management | Build internally with external support for scale | Manager enablement and workflow redesign are the bank's own work |

The partner question deserves emphasis. Third-party treasury platforms are now connecting their agents to bank data through APIs. The bank has two roles at once: the owner of its own assistants, and the freshest, most trusted data provider to the agents its clients choose. The context engine serves both; the human-release policy applies to both.

---

## 12. Capabilities and talent

Five capabilities decide whether the strategy lands, and three of them are not engineering.

1. **Stream-processing engineering.** Stateful processing, exactly-once patterns, event time, reconciliation. Scarce; grow it inside the platform team with a few experienced leads and pairing.
2. **Evaluation engineering for AI products.** Scenario-set design, scoring, thresholds, adversarial cases, LLM-as-judge calibration. Newer and scarcer; this is the role that makes governance a gate rather than a meeting.
3. **Product ownership in a regulated setting.** Writing acceptance criteria that engineering and compliance read the same way; tiering; saying no in priority order. The co-pilot program is the template.
4. **Program management with governance in the path.** Dependency boards, RAID, gates as decisions, executive reporting, change plans, and AI-assisted artifacts with validation. The Enterprise Architecture execution function is where this sits.
5. **Change leadership among line managers.** The 41% figure is the constraint. Manager enablement is a funded workstream, not a communication.

Hiring signals from the market this year: the bank is staffing agentic treasury analytics product roles ([eFinancialCareers](https://www.efinancialcareers.com/jobs-United_States-Hoboken-Product_Manager_Agentic_Treasury-Payments_Data__Analytics-Vice_President.id24559293)); peers are hiring AI compliance and ethics specialists; evaluation and observability platforms now have an analyst market guide. The talent plan should assume these roles are contested and build internal paths.

---

## 13. Scenarios: what could change the answer

The recommendation holds across three plausible futures; the sequencing and emphasis shift.

**Scenario 1: Regulation tightens faster.** The US request for information produces prescriptive expectations for agentic AI in 2027, and the EU's December 2027 obligations arrive on schedule. **Effect:** the governance-by-design investment pays off early; executed actions may need an explicit supervisory conversation before Horizon 3. **Adjustment:** bring the model inventory and lineage documentation forward; treat the evidence pack as a regulatory artifact from Horizon 1.

**Scenario 2: A major cyber incident involving an AI agent at a peer.** Given the CEO's "10-fold" comment and the acknowledged breaches during model testing this year, this is plausible within the roadmap. **Effect:** executed actions pause industry-wide; human release becomes the only acceptable design. **Adjustment:** the recommendation already makes human release policy; the kill switch, least privilege and injection testing move from controls to selling points. Horizon 3 timing slips; Horizons 1 and 2 are unaffected.

**Scenario 3: Models commoditize, context differentiates.** Foundation models converge in capability and price; the eight-week refresh becomes routine. **Effect:** the assistant layer becomes interchangeable; the fresh, entitled, reconciled fact layer and the release path are the moat. **Adjustment:** none; this is the thesis of the paper. Invest more in the engine and the evaluation framework, less in any single assistant.

A fourth scenario is less likely but worth naming: **streaming costs rise or the platform team can't be staffed.** Effect: Option B (fresh APIs per request) carries more of the load; alerts and assembled exception context arrive later. Adjustment: start with the sources that already expose fresh APIs, stream only where running state or patterns are required, and grow the engine as the team grows.

---

## 14. Readiness assessment

Score each dimension one to five before funding; anything at one or two is a Horizon 1 workstream, not an assumption.

| Dimension | What a five looks like | Typical starting point | Evidence to gather |
| --- | --- | --- | --- |
| Source readiness | SQL Server CDC enabled, Oracle supplemental logging and archive retention configured, change rates measured | Two to three; Oracle usually the gap | DBA assessment; change-rate measurement over a month-end |
| Data classification | Every candidate table and column classified; exclusions agreed | Two | Classification register for the first source set |
| Platform team | Stream-processing leads in place; on-call model funded | Two to three | Hiring plan; on-call budget |
| Entitlement model | Entitlements expressible as metadata filters at retrieval; test suite exists | Two | Entitlement rules documented; zero-tolerance tests written |
| Evaluation capability | Scenario sets, scoring and thresholds in use for an existing AI product | Three where a co-pilot or assistant already ships; one otherwise | Existing evaluation artifacts |
| Model governance | Model inventory covers generative and agentic systems; change control for prompts | Two; the April guidance removed the external template | Inventory; a documented change-control process |
| Reconciliation discipline | Scheduled reconciliation to the ledger for existing projections | Two to three | Existing reconciliation jobs and their findings |
| Change capacity | Portfolio view of change on treasurers and advisors; manager readiness measured | One to two | A change-load inventory for the target population |
| Value measurement | Leading indicators defined; a function outside delivery to track them | One to two; the Evident gap is the industry norm | Baselines for time-to-answer, exception handling time, preparation time |
| Cyber posture for agents | Least-privilege model for agent identities; injection testing; kill switch | One to two | Security review of the agent surface |

A program with more than three dimensions at one or two should extend Horizon 1 rather than compress it. The research on AI amplifying existing conditions is exactly about this: the engine will make a well-governed bank faster and a poorly governed one faster at being wrong.

---
## 15. Decisions requested

1. **Fund the streaming context engine as shared infrastructure** with a platform team, not as a line item in one product's budget, and name the second and third products that will use it.
2. **Adopt the human-release design as policy** for any agent that affects money, records or client communications: AI proposes, rules validate, a person releases, limits live in the system of action.
3. **Sequence capabilities by risk tier:** facts, alerts, drafted actions, executed actions, each behind its own evidence gate.
4. **Commit to the measurement standard** that the industry index and the regulators will ask for: leading indicators from the first quarter, value tracked outside delivery, a disclosure-ready number by the end of Horizon 2.
5. **Name a single accountable sponsor for AI governance** who decides the gates and owns the firm's response to the regulatory request for information and the EU timeline.

---
## Appendix A. Evidence base: what each claim rests on

| Claim in this paper | Evidence | Date |
| --- | --- | --- |
| JPMorgan ranks first in banking AI maturity for a fifth year; 12% of use cases show measurable impact; about 1% of banks disclose returns; scores up 26% | [Evident AI Index coverage](https://www.analyticsinsight.net/amp/story/news/jpmorgan-tops-banking-ai-rankings-for-5th-straight-year-2026) | October 6, 2026 |
| JPMorgan's CEO: cyber risk "went up 10-fold" after frontier models exposed unknown vulnerabilities | [PYMNTS](https://www.pymnts.com/news/artificial-intelligence/2026/jpmorgan-ceo-warns-ai-risks-jumped-tenfold-after-mythos/) | October 6, 2026 |
| Five banks run production agents in exception handling under a human-release design; BNY above 10% of repair volume; BNP Paribas 80 to 85% on one flow | [Sibos 2026 recap](https://www.beri.net/article/sibos-2026-recap-ai-agents-payment-repair-trade-exceptions-iso-20022-human-release); [The Fintech Times](https://thefintechtimes.com/sibos-2026-day-two-banks-put-ai-agents-to-work-but-keep-the-judgement-for-people) | Early October 2026 |
| Bank of America launched Payments Insights in CashPro; 213 million payments in H1 2026, up 10% | [FinTech Global](https://fintech.global/2026/09/28/bank-of-america-turns-to-ai-to-improve-treasury-payments/) | September 28, 2026 |
| J.P. Morgan Payments API gives treasury platforms' agents near-real-time balances and transactions | [TMI](https://treasury-management.com/news/atlar-first-to-use-j-p-morgan-payments-new-api-to-connect-ai-agents-to-banking-data-in-seconds) | April 29, 2026 |
| J.P. Morgan Payments' treasury analytics prototype and "self-driving treasury" direction | [J.P. Morgan Payments](https://www.jpmorgan.com/insights/payments/data-intelligence/genai-virtual-analytics-assistant-treasury) | December 2023 |
| FedNow: $10 million limit since November 2025; 1,800-plus participants; $271 billion in Q1 2026; RTP 128 million transactions, $480 billion in Q1 2026 | [Digital Transactions](https://www.digitaltransactions.net/fednow-marks-a-third-anniversary-tally-at-more-than-1800-banks-and-credit-unions/) | July 2026 |
| US agencies rescinded SR 11-7; new guidance excludes generative and agentic AI; RFI signaled | [Orrick](https://www.orrick.com/en/Insights/2026/04/Agencies-Overhaul-Model-Risk-Management-Guidance-for-Banks-Heres-What-Changed) | April 17, 2026 |
| EU AI Omnibus in force July 27, 2026; high-risk obligations moved to December 2027 and August 2028; Article 50 transparency in force August 2, 2026 | [SBS Software](https://sbs-software.com/insights/ai-data-in-banking/eu-ai-act-delay-banks-compliance/) | August 2026 |
| JPMorgan 2026 technology spend near $19.8 billion with about $1.2 billion additional AI investment | [AI News](https://www.artificialintelligence-news.com/news/jpmorgan-expands-ai-investment/) | March 5, 2026 |
| LLM Suite at roughly 250,000 employees, half daily; eight-week model refresh | [CeFPro](https://connect.cefpro.com/article/view/inside-jpmorgan-llm-suite-as-ai-agents-spread-across-the-bank) | 2026 |
| 450-plus AI use cases; about $2 billion annual savings attributed to AI | [Forbes](https://www.forbes.com/sites/bernardmarr/2026/07/01/how-jpmorgan-chase-is-building-the-ai-powered-bank-of-the-future/) | July 1, 2026 |
| Connect Coach assists Private Bank advisors with meeting preparation, ideas and research synthesis | [reruption.com](https://reruption.com/en/knowledge/industry-cases/jpmorgans-llm-suite-turbocharging-wealth-advisor-productivity) | 2025 to 2026 |
| 2026 streaming trends: Kafka-native consolidation, diskless and Iceberg, analytics in the stream, zero-data-loss SLAs, regional compliance, agentic context engines | [Kai Waehner](https://www.kai-waehner.de/blog/2025/12/10/top-trends-for-data-streaming-with-apache-kafka-and-flink-in-2026/) | December 2025 |
| Streaming patterns for agentic AI on AWS | [AWS](https://aws.amazon.com/blogs/big-data/powering-agentic-ai-with-real-time-streaming-data-on-aws/) | 2026 |
| Platform quality correlates with AI value; AI raises throughput and hurts stability without foundations; 90% of organizations run a platform | [Google Cloud, 2025 DORA report](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report) | 2025 |
| Agile relevance 95%, proficiency 7% | [Forrester](https://www.forrester.com/blogs/amidst-the-ai-hype-agile-still-remains-relevant-in-2025/) | 2025 |
| 21% have redesigned workflows for generative AI; 27% review outputs; senior ownership of AI governance correlates with returns | [HPCwire on the 2025 State of AI survey](https://www.hpcwire.com/aiwire/2025/03/18/mckinsey-highlights-how-organizations-are-rewiring-for-ai-success/) | March 2025 |
| One in four transformations succeeds; change saturation the primary risk; 41% of managers ready | [OCM trends 2025 to 2026](https://www.ocmsolution.com/wp-content/uploads/2025/08/2025-2026-Organizational-Change-Management-OCM-Trends-Report.pdf) | August 2025 |
| Oracle CDC is a program, not a connector | [Confluent Current 2026, MarketAxess](https://current.confluent.io/post-conference-videos-26/the-plug-play-lie-why-your-oracle-cdc-pipeline-will-fail-ldn26) | 2026 |
| Pattern detection before agents reduces volume, cost and hallucination risk; detection is deterministic and auditable | [Kai Waehner, April 2026](https://www.kai-waehner.de/blog/2026/04/28/flink-cep-and-agentic-ai-real-time-pattern-detection-as-the-foundation-for-autonomous-decisions/) | April 28, 2026 |
| Incremental index updates beat rebuilds; time-aware retrieval beats fine-tuning under drift | [arXiv 2508.05662](https://arxiv.org/abs/2508.05662); [ACL Findings 2026](https://preview.aclanthology.org/ingest-acl/2026.findings-acl.546/) | 2025 to 2026 |
| LLM judges over-trust structured signals; KV-cache reuse trades quality and can fail silently with wrong entities | [arXiv 2603.20252](https://arxiv.org/html/2603.20252v1); [arXiv 2609.10266](https://arxiv.org/html/2609.10266v1) | March and September 2026 |
| IMF analysis of agentic AI in payments | [IMF Notes 2026/004](https://www.elibrary.imf.org/view/journals/068/2026/004/article-A001-en.xml) | 2026 |

---

## Appendix B. What is deliberately not claimed

- Any internal detail of how Connect Coach, Fusion, LLM Suite or J.P. Morgan Payments systems are built. Only public descriptions are used.
- Any dollar value for the pools. The model is parameterized; the firm's numbers decide the size.
- That streaming is right for every workload. Research, policy and approved language stay on scheduled refresh or are preloaded; point lookups use fresh APIs where they exist.
- That any vendor's agent features in project tooling have specific governance properties. The validation discipline is stated independently of any product.
- That executed actions should ship in the first year. They are Horizon 3, conditional on drafted actions running clean.

---

## Appendix C. The one-page board version

**Situation.** AI maturity is being ranked and the value gap is public: 12% of use cases show impact. Banks have converged on a production pattern for agents: AI proposes, rules validate, a person releases. Competitors ship treasury intelligence on fresh data; instant payments move $10 million in seconds. US model-risk guidance now leaves generative and agentic AI to the bank's own governance; the EU's obligations land in 2027; cyber risk has stepped up.

**Insight.** The durable asset is a governed, fresh, reconciled, entitled stream of operational facts and a human release path. Assistants and agents are products on top and will be replaced; the engine and the release path compound.

**Recommendation.** Build the streaming context engine as shared infrastructure. Ship facts, then alerts, then drafted actions, then executed actions within limits, each behind an evidence gate. Use fresh APIs where they exist and scheduled refresh for content that doesn't change. Write the human-release design into policy.

**Economics.** Platform cost mostly fixed; product value mostly variable; a multiplier as products accumulate. Name the second and third products before funding the first. Test adoption at half the curve and processing cost at 1.5 times.

**Risks.** Confident wrong numbers, agents as a cyber surface, the governance gap, Oracle capture, change saturation, unmeasured value. Each has a named control.

**Decisions.** Fund the engine as infrastructure; adopt human release as policy; sequence by risk; commit to the measurement standard; name one accountable sponsor.

---

## Appendix D. How Eric Ren can use this document

The paper is a reference design and a market synthesis, not a record of your work. In interviews:

- **Claim** the parts you did: you owned requirements and the batch-to-streaming migration of a pipeline of this shape under an advisor co-pilot, with governance built into the delivery path, a shadow-then-canary cutover, and executive reporting with ROI models.
- **Cite, don't claim,** the market facts: the Evident index, Sibos, Bank of America's launch, the J.P. Morgan Payments API, FedNow's limits, the April model-risk overhaul, the EU timeline. Say "the industry pattern this month is" and name the source.
- **Use the strategic framing** as your own point of view, because it is defensible from public evidence: freshness as correctness; the engine and the release path as the asset; facts before alerts before actions; governance as the design.
- **Decline** to describe how any named bank's internal systems work. "That isn't public, and I'd want to learn how it's done here" is the right answer.

Two sentences that carry the paper's argument, for a program or platform interview:

"The research this month says most banks have assistants and almost none can show the operational number changed. The way to be in the few is to build the fresh, reconciled, entitled fact layer once, put every assistant and agent on it, keep people releasing anything that moves money, and measure freshness and correctness from the first sprint."

---

## Sources

Listed in Appendix A with dates. All were opened during the preparation of this paper or its two companion documents.
