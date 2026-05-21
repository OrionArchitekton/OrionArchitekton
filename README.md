# Dan Mercede — Systems Architect

**Runtime-enforced, governed AI operating systems.** I design executionenvironments where policy is evaluated at the moment of action, authority isenforced before state mutation, systems default to fail-closed, and everymaterial action produces an immutable audit receipt.

> If it bypasses the receipt log or a gate, it does not ship.

* * *

### Featured work (public)

* **[cosmocrat-operator](https://github.com/OrionArchitekton/cosmocrat-operator)** · RustGoverned operator plane for AI-executed code. Replaces autonomous AI coding with a`PLAN → EXECUTE → REVIEW → APPROVE` pipeline — five server-enforced human gates,per-task git worktrees, and an append-only Chronicle. No autonomous execution path exists.
  
* **[compound-intake-router](https://github.com/OrionArchitekton/compound-intake-router)** · JavaScriptWebhook intake pipeline: Claude classifies, deterministic config routes, SQLite logs anaudit trail. Every stage degrades gracefully — no silent drops. *AI classifies; rules route.*
  
* **[cadence-tracker](https://github.com/OrionArchitekton/cadence-tracker)** · model routingDual-variant Gemma routing (fast-path + MoE synthesizer) for a publishing cadence engine.dev.to Gemma challenge submission.
  
* **[cosmocrat-reference-architectures](https://github.com/OrionArchitekton/cosmocrat-reference-architectures)** Reader-facing reference architectures for the Cosmocrat governed-AI control plane.
  

*Most production systems (control-plane core, gateways, knowledge vaults, ventureinfrastructure) are private — client and venture IP.*

### The enforcement stack

| Layer | Invariant |
| --- | --- |
| Authority Gate | Execution depends on authority — evaluated before state mutation |
| Immutable Receipts | Mutation depends on attestation — receipts over logs |
| Drift Guard | Behavior constrained across time — authority decays, no standing paths |
| Gated Substrate | Capability removed, not restricted — isolation at the execution layer |

### What I work on

Governed AI control planes · agent-native systems and **MCP (Model Context Protocol)**servers · RAG / retrieval architectures · multi-cloud delivery (Vertex AI, Azure OpenAI,AWS) with IaC, CI/CD, and security architecture.

### Stack

`Rust` · `TypeScript` · `Python` · `SQL` · `Node.js` · `React/Next.js``Anthropic SDK` · `OpenAI SDK` · `MCP` · `LangChain/LangGraph` · `RAG` · `ClickHouse` · `Vertex AI` · `Azure OpenAI` · `AWS` · `Supabase/Postgres` · `Docker` · `Terraform`

### Elsewhere

* Site: https://danmercede.com · LinkedIn: https://www.linkedin.com/in/danmercede
