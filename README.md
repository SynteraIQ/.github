# 🧠 SynteraIQ – AI-Native Platform for PhysicalOps Automation

**SynteraIQ** is a modular AI platform built to automate operational workflows across physical infrastructure domains — including **airports**, **railways**, and **ports**.

Inspired by platforms like **Harness (DevOps)** and **ServiceNow (ITSM)**, SynteraIQ brings the same level of intelligence and structure to **PhysicalOps**

## 🧭 What is PhysicalOps?

**PhysicalOps** covers all workflows that support the operation, maintenance, and expansion of physical infrastructure:
- CapEx request and approval flows
- Procurement and vendor onboarding
- Maintenance planning and execution
- Risk, compliance, and audit tracking
- Shift management, resource allocation, incident response

SynteraIQ turns these traditionally manual, fragmented processes into intelligent, self-routing workflows using domain-aware, GPT-powered agents.

---

## 🧱 Platform Architecture Overview

```
            +-------------------------+
            |     synteraiq-app-*     |  ← SaaS UI (Airports, Railways, Ports)
            +-------------------------+
                      |
             [ WebSocket + REST ]
                      ▼
        +--------------------------+
        |      platform-core       |  ← Auth, user mgmt, approvals, tenants
        +--------------------------+
                      |
        +--------------------------+
        |    platform-router       |  ← Orchestrates multi-agent flows
        +--------------------------+
                      |
        ▼     ▼     ▼     ▼     ▼
    agent-capex   agent-procurement   agent-maintenance   ...
                      |
               [ GPT / LLMs ]
```

---

## 📦 Key Repositories

### UI

| Repo | Purpose |
|------|---------|
| `ui-core` | Shared UI components, layouts, GPT chat |
| `synteraiq-app-airports` | AirportOps UI (AODB, CapEx, MRO) |
| `synteraiq-app-railways` | RailwayOps UI (crew, track, terminal ops) |

### Backend

| Repo | Purpose |
|------|---------|
| `platform-core` | Central user, auth, approval logic |
| `platform-router` | Agent orchestration, multi-step logic |
| `agent-capex` | CapEx intake, validation, approval |
| `agent-maintenance` | Maintenance workflows, SLA |
| `agent-sdk` | Shared GPT, retry, logging logic |
| `ml-infra` | Embedding, vector stores, LLM pipelines |

### Infra / Tooling

| Repo | Purpose |
|------|---------|
| `infra-deployments` | Docker, Terraform, GitHub Actions |
| `docs` | Architecture, onboarding, API references |
| `template-agent` | FastAPI + GPT starter template |

---

## 🔌 Supported Integrations

- SAP (IO creation, procurement, WBS)
- AODB / FRMS (resource & flight data)
- SSO / AD (role-based access)
- GIS / IoT (asset tracking, real-time telemetry)
- Excel / CSV (AOP sheet parsing)

---

## 🧠 Tech Stack

- **Python** (FastAPI, SQLModel, LangChain)
- **React** + Tailwind + shadcn/ui
- **OpenAI / Claude** (LLM integration)
- **PostgreSQL**
- **Docker / GitHub Actions**
- (Optional) **Temporal** for durable workflows

---

## 🧪 Example Use Cases

- “Submit a CapEx for 3 baggage belts in Terminal 1”
- “Show maintenance history for Gate 24 over last 60 days”
- “Route this procurement to the HOD since it exceeds ₹10 lakh”
- “Generate IO and notify finance for approved terminal expansion”

---

## 📄 License

MIT © 2025 SynteraIQ – AI-native automation for the physical world.
