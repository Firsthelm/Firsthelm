# FirstHelm

**The control plane for autonomous AI agents.**

Frameworks build agents. FirstHelm governs them.

## What we're building

AI agents are moving from demos to production, and the question has shifted from *"can it do the task?"* to *"who's making sure it does it safely, on budget, and on the record?"*

FirstHelm is a framework-agnostic control plane that sits between your team and your autonomous agents:

- **Agent registry** — one inventory of every agent your organisation runs: framework, owner, autonomy level, status. You cannot govern what you cannot see.
- **Pre-execution constraints** — budget ceilings, forbidden actions, rate limits, time windows and data-access rules, evaluated *before* an action runs. Verdicts: allowed, blocked, or needs approval.
- **Human-in-the-loop approvals** — risky actions pause mid-flight; a human approves or rejects; the agent continues or stops. Silence is never treated as consent.
- **Adaptive autonomy** — autonomy as an adjustable dial per agent, earned through track record and withdrawn after failures.
- **Activity logging & audit trail** — append-only, tamper-evident records of every action, constraint verdict, approval and intervention. Exportable as evidence.
- **Mid-flight intervention** — pause, inspect, override, or stop any running agent at any time.

## Built for compliance from day one

The EU AI Act's Article 12 (record-keeping) and Article 14 (human oversight) turn oversight from a nice-to-have into an operational duty. FirstHelm also supports alignment with **ISO/IEC 42001**, **NIST AI RMF** and **UK GDPR** — the control plane your AI management system runs on.

## Quickstart

Any agent that can make an HTTP call can be governed:

```bash
# 1. Register an agent
curl -X POST https://api.firsthelm.dev/functions/registerAgent \
  -H "Authorization: Bearer fhk_your_api_key" \
  -d '{"name": "support-bot", "framework": "langchain", "autonomyLevel": 2}'

# 2. Log an action for pre-execution checking
curl -X POST https://api.firsthelm.dev/functions/logActivity \
  -H "Authorization: Bearer fhk_your_api_key" \
  -d '{"agentId": "agt_123", "actionType": "send_email", "payload": {...}}'
# → { "verdict": "needs_approval" }
```

Works with OpenAI, LangChain, CrewAI, AutoGen, or your own code.

## Learn more

- Website: https://firsthelm.dev
- Docs: https://firsthelm.dev/docs
- API reference: https://firsthelm.dev/docs/api-reference
- What is an AI agent control plane? https://firsthelm.dev/guides/what-is-an-ai-agent-control-plane
- Governance glossary: https://firsthelm.dev/glossary
- LinkedIn: https://www.linkedin.com/company/firsthelm

## Open source at FirstHelm

The control plane itself stays closed; the edges are open. We're building towards public SDKs and example repos — watch this space.

---

*FirstHelm Ltd (company number 17455295, registered in England and Wales).*
