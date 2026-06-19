# Dan Mercede — Founder & Systems Architect

![Rust](https://img.shields.io/badge/Rust-1a1a1a?style=flat&logo=rust&logoColor=B7410E)
![TypeScript](https://img.shields.io/badge/TypeScript-1a1a1a?style=flat&logo=typescript&logoColor=3178C6)
![Python](https://img.shields.io/badge/Python-1a1a1a?style=flat&logo=python&logoColor=3776AB)
![ClickHouse](https://img.shields.io/badge/ClickHouse-1a1a1a?style=flat&logo=clickhouse&logoColor=FFCC01)
![Langfuse](https://img.shields.io/badge/Langfuse-1a1a1a?style=flat&logoColor=B87333)
![Anthropic](https://img.shields.io/badge/Anthropic_Claude-1a1a1a?style=flat&logo=anthropic&logoColor=D97757)

**Architecting fail-closed AI execution governance.** Runtime authority. Immutable receipts. Policy evaluated at the moment of action. Fail-closed defaults.

> *Enforcement before state mutation. Receipts over logs. Authority is unavailable unless granted.*

---

## What I'm building

A **governed-AI execution control plane** decomposed across four services so no component can self-authorize.

| Service | Role | Language | State |
|---------|------|----------|-------|
| Operator UI | Intent submission · diff review · approval | React / TS | Built (not deployed) |
| Authority adapter | RBAC · attestation verify · Chronicle write · CCA forward | Python (FastAPI) | Built (not deployed) |
| Signing service | Ed25519 identity + signing — separated from policy | Rust (axum) | Built (not deployed) |
| **Decision kernel + Chronicle + OPA + Langfuse** | **Mutation authority · immutable receipts · policy · tracing** | Python | **Live · multi-node Tailscale cluster · running continuously for months** |

The signing/identity layer is deliberately separated from policy/authority and from the UI. The adapter holds no signing keys. The kernel is the sole receipt/audit authority. This is the correct shape for a fail-closed governance system.

I'm deliberate about what's enforced versus scaffolded. I can walk through exactly which controls are live today, which are stubbed, and the order I'd harden them. **Architecture and the live substrate are available for screen-share walkthrough under NDA.** Production repos are private.

The enforcement model also ships as public, runnable code — **[failclosed](https://github.com/OrionArchitekton/failclosed)** applies the Authority Gate to the coding-agent merge boundary: distrust the reviewer's verdict, refuse `MERGE_READY` on unparseable or self-contradictory output.

---

## Enforcement model *(doctrine)*

| Layer                  | Invariant                                               |
| ---------------------- | ------------------------------------------------------- |
| **Authority Gate**     | No mutation occurs without evaluated authority          |
| **Immutable Receipts** | Every material action produces durable evidence         |
| **Drift Guard**        | Authority expires; standing mutation paths are rejected |
| **Gated Substrate**    | Capability is unavailable unless granted at runtime     |

Full doctrine and reference architectures at **[danmercede.com](https://danmercede.com)**.

---

## System boundary

**Cosmocrat Core** stays narrow by design: mutation authority decisions, policy evaluation, fail-closed enforcement, receipt persistence, audit queries.

**Execution systems** — MCP servers, RAG pipelines, orchestration, dashboards, CI/CD, cloud delivery, business workflows — belong *outside* core and integrate through governed gates.

Around the runtime path sits a **contract-first Core layer** — language-neutral decision/receipt schemas, versioned policy-pack content, semantics-only memory-governance contracts, and a staged published-knowledge authority service — several with **test suites exceeding source** and fail-closed defaults. *Design-canon and staged; not all live-enforced today.*

---

## What I work on

Governed AI control planes · agent-native systems · trace/receipt data planes · **MCP (Model Context Protocol)** servers · RAG / retrieval architectures · authority-gated execution · audit-grade automation · secure multi-cloud delivery.

I focus on systems where AI can act only through **explicit authority, bounded capability, and observable runtime enforcement.**

---

## Selected writing

→ **[danmercede.com](https://danmercede.com)** — Doctrine, reference architectures, and field-tested patterns for runtime-governed AI.

The four-layer enforcement stack: *Authority Gate · Mutation Attestation · Drift Guard · Gated Substrate.* Enterprise AI does not fail on capability. It fails on control.

---

## Public repos

The production control planes are private/self-hosted. These are public.

**Flagship**

> **[failclosed](https://github.com/OrionArchitekton/failclosed)** · *Python*
> Fail-closed merge admission control for agent-written code. Runs an LLM reviewer, **distrusts its verdict**, and refuses `MERGE_READY` on unparseable, schema-invalid, or self-contradictory output. The Authority Gate and Immutable Receipts model, applied to the coding-agent merge boundary.

**Supporting artifacts**

> **[algorithm-reviews](https://github.com/OrionArchitekton/algorithm-reviews)** · *TypeScript · live*
> A governed agent that fact-checks claims against the live web, decides which sources are **admissible** (fail-closed), and ships a cryptographically **signed review receipt** — verdict, timestamped citations, dissent, and an ECDSA signature anyone can verify. Every admit/reject decision streams in real time. Admission control and attestation, end to end.

> **[proctor](https://github.com/OrionArchitekton/proctor)** · *TypeScript*
> An agent that QAs other agents. It learns each AI automation's behavioral contract, catches when a model or prompt change silently breaks it, self-heals the tests when the change is legitimate, and escalates real regressions to a human. Drift caught at the behavioral boundary, not after the fact.

> **[cosmocrat-reference-architectures](https://github.com/OrionArchitekton/cosmocrat-reference-architectures)** · *docs*
> Reader-facing reference architectures for governed-AI control planes — product boundary, deployment composition, authority gates, receipt trails, and failure boundaries. Docs only.

*Production control planes, gateways, knowledge vaults, observability infrastructure, and venture systems remain private by design.*

---

## Open-source contributions

I contribute upstream to the MCP and AI-observability tooling I build on — fixes and test coverage, in-domain.

**Merged**

> **[punkpeye/fastmcp#275](https://github.com/punkpeye/fastmcp/pull/275)** · *merged* · ⭐3.2k
> `/health` and `/ready` only matched `GET`, so `HEAD` probes from load balancers and
> orchestrators fell through to a `404` — the endpoint read as *down*. Extended both
> guards to answer `HEAD` (headers-only, status preserved, per HTTP/1.1). Closes #178.

> **[Arize-ai/openinference#3238](https://github.com/Arize-ai/openinference/pull/3238)** · *merged* · ⭐1k
> The Agno workflow instrumentor serialized Pydantic response content with `str()` —
> Python `repr` in traces instead of JSON. Switched to `model_dump_json()` with a safe
> `str()` fallback, plus regression tests. Closes #3235.

**Open · under review**

> **[truera/trulens#2536](https://github.com/truera/trulens/pull/2536)** · ⭐3.4k — Bedrock provider capability tests.

> **[truera/trulens#2537](https://github.com/truera/trulens/pull/2537)** · ⭐3.4k — Cortex provider capability tests.

---

## Stack

| Layer         | Tools                                                                                              |
| ------------- | -------------------------------------------------------------------------------------------------- |
| Languages     | Rust · TypeScript · Python · SQL                                                                   |
| AI systems    | Anthropic SDK · OpenAI SDK · MCP · LangChain / LangGraph · RAG · GraphRAG · Vertex AI · Azure OpenAI |
| Observability | Self-hosted Langfuse · ClickHouse · OPA · custom telemetry                                         |
| Data          | Postgres / Supabase · SQLite · ClickHouse · Neo4j + Cognee                                         |
| Infra         | AWS · Railway · Docker · Terraform · CI/CD · multi-node Tailscale mesh                             |
| Frontend      | React · Next.js · Node.js · *(production on Vercel)*                                               |

---

## Currently open to

AI Solutions Architect · Forward Deployed Engineer · AI Engineer · Founding Engineer roles in **agentic systems, runtime governance, observability for AI, and enterprise AI platforms.**

San Diego · Open to hybrid · Remote · Relocation for the right architectural opportunity.

---

## Elsewhere

```yaml
Site:     danmercede.com
LinkedIn: linkedin.com/in/danmercede
GitHub:   github.com/OrionArchitekton
Email:    dan@danmercede.com
Location: San Diego, CA
```
