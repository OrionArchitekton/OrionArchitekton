# Dan Mercede

**Operator · AI Product Builder · Systems Architect**

*Ambiguous workflow → deployed product → honest evaluation → operating proof*

<!-- hero image slot: embed the new operator-builder banner here when the asset lands, e.g. assets/hero-operator-builder.png; the old governance banner stays unembedded -->

I turn ambiguous operating workflows into narrow AI products, and carry them from product thesis through working system, evaluation, and operational proof. The full path: finding the decision worth improving, building the product and the infrastructure under it, and proving where it works, where it fails, and where it should abstain.

---

## Selected recent builds

#### [notary](https://github.com/OrionArchitekton/notary)

Data catalogs accumulate claims (units, freshness, enums) that nothing re-checks, so an agent grounded on the catalog can quote revenue 100x off with the catalog's authority behind it. Notary cross-examines those claims with deterministic SQL probes and writes CONFIRMED, CONTRADICTED, or UNVERIFIABLE verdicts back into DataHub via MCP.

[Replay demo](https://notary-replay.vercel.app) · `9 of 12 planted lies caught` · `0 of 6 controls misclassified` · evals published verbatim, misses included

#### [standing-questions](https://github.com/OrionArchitekton/standing-questions)

Asking a live firehose a question gets you a one-time paragraph that silently rots as the data changes. Each question runs as a durable agent turn that answers with a gated chart, keeps re-evaluating on a schedule, and reopens the thread with a before and after delta.

[Keyless live demo](https://standing-questions.vercel.app) · `scheduled tasks verified live in production` · `59 unit tests` · honest limit: ingest is a sampled stream

#### [whisperways](https://github.com/OrionArchitekton/whisperways)

Community noise acceptance gates advanced air mobility. Whisperways plans eVTOL corridors by who hears them (a census-grounded population-noise raster plus Dijkstra), with Claude drafting a community brief grounded only in engine-computed numbers.

[Live demo](https://whisperways.vercel.app) · `LAX to Burbank at night: about 221,000 people hear the direct route, about 51,000 the quiet corridor (77% fewer)` · a planning heuristic, not certification acoustics

#### [codex-rule-ledger](https://github.com/OrionArchitekton/codex-rule-ledger)

A diff shows what an agent changed, not which instruction chain governed the change, and confusing missing evidence with compliance corrupts review. The ledger first asks whether the supplied evidence makes any verdict admissible at all; deterministic TypeScript alone owns verdicts and hashes, the LLM only proposes source-linked semantics.

[Keyless demo, recorded cases only](https://codex-rule-ledger.vercel.app) · `77 tests` · `lint, typecheck, production build, five Chromium E2E flows`

#### [engram](https://github.com/OrionArchitekton/engram)

Agents forget everything between sessions, or "solve" it by stuffing the whole chat history into context. Engram treats memory as an engineering problem: typed memories with decay half-lives, budget-bounded recall through a property-tested packer, contradiction adjudication.

[Live backend](https://engram.orionbot.online) on Alibaba Cloud Function Compute · caveat stated plainly: the instance stores memories in /tmp SQLite, so recycling resets the store

---

## How I build

- Start from a named user and the specific decision they get wrong today.
- Models only at the ambiguous edges; deterministic code owns every step where an error touches money or state, fail-closed where a wrong verdict could otherwise pass silently.
- Publish evaluations verbatim, misses included.
- Ship the operating proof with the product: live URLs where something is live, frozen replays labeled as replays, prototypes labeled as prototypes.

---

## Foundational systems

- **[failclosed](https://github.com/OrionArchitekton/failclosed)** runs an LLM code reviewer and then refuses to trust it: unparseable, schema-invalid, or self-contradictory reviewer output never yields MERGE_READY. Its own label: a narrow, runnable demonstration of one principle.
- **[proctor](https://github.com/OrionArchitekton/proctor)** QAs non-deterministic AI automations, a UiPath AgentHack 2026 finalist: it learns each automation's behavioral contract, classifies drift as real regression, legitimate evolution, or flake, and pauses on a durable human approval before any mutation; all four surfaces verified live against a UiPath Labs tenant, and the README calls it what it is, a working MVP with disclosed limits.
- **[schemafit](https://github.com/OrionArchitekton/schemafit)** lints structured-output and tool schemas against each provider's documented constraints in CI, no model calls and no API key: across 50 real public schemas, 44 (88%) would be rejected by at least one major provider.

---

## Production and upstream proof

The production substrate is private: a decision kernel with Chronicle receipts, OPA policy, and Langfuse tracing runs live on a multi-node Tailscale cluster, in continuous personal operation for months, with the operator UI, authority adapter, and Rust signing service built and integration-tested alongside it. Upstream, in the tooling I build on:

- [punkpeye/fastmcp#275](https://github.com/punkpeye/fastmcp/pull/275), merged: /health and /ready answer HEAD probes from load balancers.
- [Arize-ai/openinference#3238](https://github.com/Arize-ai/openinference/pull/3238), merged: Agno traces carry real JSON instead of Python repr.
- [acryldata/mcp-server-datahub#140](https://github.com/acryldata/mcp-server-datahub/pull/140), open: accounts for omitted documents in grep_documents results.

---

## Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) ![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white) ![ClickHouse](https://img.shields.io/badge/ClickHouse-FFCC01?style=flat&logo=clickhouse&logoColor=black) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat) ![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)

Anthropic and OpenAI SDKs, MCP, LangChain and LangGraph, Vertex AI, SQL; self-hosted Langfuse for observability; Supabase, SQLite, Neo4j; Terraform and a multi-node Tailscale mesh.

---

## Contact

Site and writing: [danmercede.com](https://danmercede.com) · Working log: [danmercede.online](https://danmercede.online) · LinkedIn: [linkedin.com/in/danmercede](https://linkedin.com/in/danmercede) · Email: [dan@danmercede.com](mailto:dan@danmercede.com) · San Diego, CA

Best technical read: the [notary README](https://github.com/OrionArchitekton/notary).

I'm drawn to valuable, messy workflows that lack a clear owner, especially where a narrow AI product can become the system of action.
