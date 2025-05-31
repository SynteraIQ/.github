# .github

# 🧭 SynteraIQ UI Architecture

This repository serves as the **shared frontend foundation** for SynteraIQ's AI-powered PhysicalOps platform.  
It enables rapid development of **vertical-specific SaaS interfaces** across transport sectors such as **airports**, **railways**, and **ports**.

---

## 🧱 Repo Structure

| Repo | Purpose |
|------|---------|
| `ui-core` | Shared component library (chat, layout, auth, GPT UI) |
| `synteraiq-app-airports` | AirportOps UI — integrates with AODB, CapEx, MRO |
| `synteraiq-app-railways` | RailwayOps UI — focuses on maintenance, crew, scheduling |
| `synteraiq-app-ports` | PortOps UI — workflows for cranes, vendors, inspections |

All vertical-specific apps import from `ui-core` to ensure consistency in experience, branding, and functionality.

---

## 💡 Key Design Principles

- 🧩 **Composable:** Modular components using React + Tailwind + shadcn/ui
- 🌍 **Vertical-specific:** Custom workflows per domain (AODB, FRMS, etc.)
- 🔁 **Reusable:** All UIs inherit from a centralized UI system (`ui-core`)
- 🧠 **AI-native:** Integrated WebSocket GPT chat per agent

---

## 📁 Example Directory (in `ui-core`)

```
ui-core/
├── components/         # Buttons, chat, modals
├── layout/             # Header, sidebar, shell
├── lib/                # WebSocket, auth, agent client
├── pages/              # Minimal pages (used mostly for previews)
├── context/            # Theme, user, session
├── branding/           # White-label assets (logos, colors)
└── index.ts            # Export all UI modules
```

---

## 🚀 Usage in a Vertical App

From `synteraiq-app-airports`:

```tsx
import { ChatWindow, ApprovalTimeline } from "@synteraiq/ui-core";
```

---

## 📦 Tech Stack

- React + Next.js or Vite
- Tailwind CSS + `shadcn/ui`
- WebSocket support for GPT agents
- `react-hook-form` + `zod` for input validation
- Optional white-labeling per tenant or vertical

---

## 📄 License

MIT © 2025 SynteraIQ — UI infrastructure for intelligent PhysicalOps.
