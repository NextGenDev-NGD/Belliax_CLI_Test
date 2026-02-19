# Belliax_CLI_Test
Repo to install and configure local AI CLI agents via WSL.

---

## Project Phases

```mermaid
flowchart TD
    A([🖥️ Start: Windows + WSL2]) --> B

    subgraph DONE [✅ Phase 1 — Environment Setup]
        B[Install Git on Windows\nwinget install Git.Git]
        B --> C[Install Node.js in WSL\nvia nodesource]
    end

    subgraph DONE2 [✅ Phase 2 — AI CLI Agents]
        D[Install Claude Code\nnpm install -g @anthropic-ai/claude-code]
        D --> E[Install Gemini CLI\nnpm install -g @google/gemini-cli]
    end

    subgraph NEXT [🔄 Phase 3 — API Key Configuration]
        F[Add ANTHROPIC_API_KEY to ~/.bashrc]
        F --> G[Add GEMINI_API_KEY to ~/.bashrc]
        G --> H[source ~/.bashrc]
    end

    subgraph PHASE4 [⏳ Phase 4 — IDE Setup]
        I[Install IntelliJ IDEA Community\nwinget install JetBrains.IntelliJIDEA.Community]
        I --> J[Install GitHub Copilot plugin\nfree tier via Marketplace]
    end

    subgraph PHASE5 [⏳ Phase 5 — Verify & Test]
        K[claude --version]
        K --> L[gemini --version]
        L --> M[Run a test prompt on each agent]
    end

    subgraph PHASE6 [🗺️ Phase 6 — Workflow Integration]
        N[Set up MCP servers for Claude Code]
        N --> O[Create shell aliases & scripts]
        O --> P[Connect agents to active projects]
    end

    DONE --> DONE2
    DONE2 --> NEXT
    NEXT --> PHASE4
    PHASE4 --> PHASE5
    PHASE5 --> PHASE6
```

---

## Status

| Phase | Description | Status |
|-------|-------------|--------|
| 1 | Environment Setup (WSL, Node.js, Git) | ✅ Done |
| 2 | AI CLI Agents (Claude Code, Gemini CLI) | ✅ Done |
| 3 | API Key Configuration | 🔄 Next |
| 4 | IDE Setup (IntelliJ + GitHub Copilot) | ⏳ Pending |
| 5 | Verify & Test all agents | ⏳ Pending |
| 6 | Workflow Integration (MCP, aliases, projects) | 🗺️ Planned |

---

## Setup Guide

See [`Source/windows-ai-dev-setup.md`](Source/windows-ai-dev-setup.md) for full installation instructions.
