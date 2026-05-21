# Dan Mercede — Founder & Systems Architect

**Runtime-enforced AI execution control planes.** I build systems where policy is
evaluated at the moment of action, authority is enforced before state mutation,
failures close by default, and every material action emits an immutable audit receipt.

> If it bypasses a gate or the receipt log, it does not ship.

---

### System boundary

**Cosmocrat Core** stays narrow by design: mutation authority decisions, policy
evaluation, fail-closed enforcement, receipt persistence, and audit queries.

Execution systems — MCP servers, RAG pipelines, orchestration, dashboards, CI/CD,
cloud delivery, and business workflows — belong outside core and integrate through
governed gates.

---

### Featured work (public)

- **[cosmocrat-operator](https://github.com/OrionArchitekton/cosmocrat-operator)** · Rust  
  Governed operator plane for AI-executed code. Replaces unsupervised AI coding with a
  server-enforced `PLAN → EXECUTE → REVIEW → APPROVE` pipeline: five human gates,
  per-task git worktrees, and an append-only Chronicle. No unsupervised mutation path exists.

- **[cosmocrat-reference-architectures](https://github.com/OrionArchitekton/cosmocrat-reference-architectures)**  
  Reader-facing reference architectures for the Cosmocrat governed-AI control plane.
  Maps authority gates, receipt trails, failure boundaries, and integration surfaces.

- **[compound-intake-router](https://github.com/OrionArchitekton/compound-intake-router)** · JavaScript  
  Webhook-driven intake pipeline. Claude classifies, deterministic config routes,
  and SQLite records the audit trail. Every stage degrades gracefully — no silent drops.
  *AI classifies; rules route.*

- **[cadence-tracker](https://github.com/OrionArchitekton/cadence-tracker)** · model routing  
  Dual-variant Gemma routing for a publishing cadence engine: fast-path classification
  plus MoE-style synthesis. Built as a dev.to Gemma challenge submission.

Public repos expose reference patterns and proofs. Production control planes,
gateways, knowledge vaults, and venture infrastructure remain private by design.

---

### Enforcement model

| Layer | Invariant |
|-------|-----------|
| Authority Gate | No mutation occurs without evaluated authority |
| Immutable Receipts | Every material action produces durable evidence |
| Drift Guard | Authority expires; standing mutation paths are rejected |
| Gated Substrate | Capability is unavailable unless granted at runtime |

---

### What I work on

Governed AI control planes · agent-native systems · **MCP (Model Context Protocol)**
servers · RAG / retrieval architectures · authority-gated execution · audit-grade
automation · secure multi-cloud delivery.

I focus on systems where AI can act only through explicit authority, bounded capability,
and observable runtime enforcement.

---

### Stack

**Languages:** Rust · TypeScript · Python · SQL  
**AI systems:** Anthropic SDK · OpenAI SDK · MCP · LangChain/LangGraph · RAG  
**Data:** Postgres/Supabase · SQLite · ClickHouse  
**Infra:** AWS · Azure OpenAI · Vertex AI · Docker · Terraform · CI/CD  
**Frontend:** React · Next.js · Node.js

---

### Elsewhere

- Site: [danmercede.com](https://danmercede.com)
- LinkedIn: [linkedin.com/in/danmercede](https://www.linkedin.com/in/danmercede)
