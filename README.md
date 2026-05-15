<div align="center">

#  Agentic-AI-Frameworks

### A curated collection of production-grade Agentic AI implementations across LangGraph, CrewAI, LangChain, Streamlit & Google ADK

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![LangChain](https://img.shields.io/badge/LangChain-0.3.18-1C3C3C?style=for-the-badge&logo=chainlink&logoColor=white)](https://langchain.com)
[![LangGraph](https://img.shields.io/badge/LangGraph-0.3.21-2D9CDB?style=for-the-badge)](https://langchain-ai.github.io/langgraph)
[![CrewAI](https://img.shields.io/badge/CrewAI-1.13.0-FF4B4B?style=for-the-badge)](https://crewai.com)
[![Streamlit](https://img.shields.io/badge/Streamlit-Apps-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)
[![Google ADK](https://img.shields.io/badge/Google%20ADK-%E2%89%A51.33.0-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://google.github.io/adk-docs/)
[![License](https://img.shields.io/badge/License-MIT-22C55E?style=for-the-badge)](LICENSE)

*Five distinct agentic AI frameworks — from graph-based agent orchestration to multi-agent collaboration and Google's native agent platform — each solving a different dimension of autonomous AI system design.*

</div>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Framework Comparison](#-framework-comparison)
- [Project Index](#-project-index)
  - [LangChain](#1--langchain)
  - [LangGraph](#2--langgraph)
  - [Google ADK](#3--google-adk)
  - [CrewAI](#4--crewai)
  - [Streamlit](#5--streamlit)
- [Tech Stack](#-tech-stack)
- [Agentic AI Evolution Map](#-agentic-ai-evolution-map)
- [Author](#-author)

---

## 🔍 Overview

**Agentic-AI-Frameworks** is a systematic exploration of the modern agentic AI ecosystem. Each project in this collection tackles a different architectural challenge — from stateful graph-based agent workflows and multi-agent collaboration pipelines to LLM chain fundamentals and interactive AI-powered UIs.

This repository serves as both a **reference library** and a **portfolio of applied agentic AI engineering**.

```
Agentic-AI-Frameworks/
├── langchain/       # LLM chains, tools, and prompt engineering
├── langgraph/       # Graph-based stateful agent workflows (10 modules)
├── google-adk/      # Multi-agent travel planner — Google ADK + Gemini
├── crew-ai/         # Multi-agent research & blog writing pipeline
└── streamlit/       # Interactive AI-powered web applications
```

---

## 📊 Framework Comparison

| Feature | LangGraph | CrewAI | LangChain | Streamlit | Google ADK |
|---|---|---|---|---|---|
| **Primary Use** | Stateful agent graphs | Multi-agent collaboration | LLM chains & tools | Interactive AI UIs | Native Google agent platform |
| **Agent Type** | Single/Multi-agent | Role-based agents | Tool-using chains | UI layer | Hierarchical sub-agents |
| **Memory/State** | ✅ Full state graph | ✅ Context passing | ⚠️ Limited | ❌ Session only | ✅ ADK managed |
| **Human-in-Loop** | ✅ Native support | ⚠️ Limited | ❌ | ✅ Via UI | ⚠️ Limited |
| **Multi-Agent** | ✅ Supervisor pattern | ✅ Core feature | ❌ | ❌ | ✅ Native hierarchy |
| **Streaming** | ✅ Token + event | ⚠️ Limited | ✅ | ✅ | ✅ |
| **LLM Support** | OpenAI, Gemini, Groq | Gemini, OpenAI | All major LLMs | Any backend | Gemini (native) |
| **Complexity** | Advanced | Intermediate | Beginner–Advanced | Beginner | Intermediate |

---

## 📁 Project Index

---

### 1. 🔗 LangChain

> **The foundation — LLM chains, prompt engineering, tools, and retrieval primitives.**

A structured learning repository covering LangChain's core building blocks. From prompt templates and output parsers to tool-calling and retrieval chains — the fundamentals that power everything in this vault.

**→ Repository:** [LangChain](https://github.com/a-r-ashik/LangChain)

#### LangChain Ecosystem

```mermaid
flowchart LR
    A[💬 User Input] --> B[Prompt Template\nStructured prompts]
    B --> C[LLM\nOpenAI · Gemini · Groq]
    C --> D[Output Parser\nString · JSON · Pydantic]
    D --> E[✅ Structured Output]

    C -->|Tool call| F[Tools\nSearch · Calculator · APIs]
    F --> C

    C -->|Needs context| G[Retriever\nVector Store]
    G --> C

    style A fill:#1C3C3C,color:#fff
    style C fill:#2D9CDB,color:#fff
    style E fill:#22C55E,color:#fff
    style F fill:#D97706,color:#fff
    style G fill:#7C3AED,color:#fff
```

#### Stack
`LangChain` · `OpenAI` · `Google Gemini` · `Groq` · `ChromaDB` · `FAISS` · `python-dotenv`

---

### 2. 🔷 LangGraph

> **Graph-based agent orchestration — the most powerful way to build stateful, cyclical AI workflows.**

A hands-on learning journey through LangGraph's core concepts and real-world agent systems. Covers 10 progressive modules from basic graph primitives to full multi-agent architectures with human-in-the-loop patterns.

**→ Repository:** [LangGraph](https://github.com/a-r-ashik/LangGraph)

#### 10 Modules Covered

| # | Module | Key Concept |
|---|---|---|
| 1 | Introduction | StateGraph, nodes, edges, entry/finish points |
| 2 | Basic Reflection System | Generate → Reflect loops with conditional edges |
| 3 | Reflexion Agent | Self-critique with tool feedback, episodic memory |
| 4 | State System | TypedDict schemas, reducers, checkpointing |
| 5 | ReAct Agent | Reasoning + Acting loop with tool execution |
| 6 | Chatbots | Persistent memory via SqliteSaver, multi-session |
| 7 | Human in the Loop | Pause/resume execution, approval workflows |
| 8 | RAG Agent | Graph-based retrieval with conditional routing |
| 9 | Multi-Agent Architecture | Supervisor pattern, specialist agent delegation |
| 10 | Streaming | Token-level & event-level streaming, responsive UIs |

#### Core Architecture

```mermaid
flowchart TD
    A[StateGraph\nDefine typed state schema] --> B[Nodes\nComputation steps]
    B --> C{Conditional\nEdges}

    C -->|Continue| D[Next Node]
    C -->|Tool Call| E[Tool Execution]
    C -->|Human Review| F[⏸ PAUSE\nHuman-in-the-Loop]
    C -->|Done| G[END]

    F -->|Approved| D
    E --> B
    D --> C

    style A fill:#2D9CDB,color:#fff
    style F fill:#F59E0B,color:#fff
    style G fill:#22C55E,color:#fff
```

#### Multi-Agent Supervisor Pattern

```mermaid
flowchart TD
    U[💬 User Query] --> S[Supervisor Agent\nRouting LLM]

    S -->|Research needed| R[Researcher Agent]
    S -->|Code needed| C[Coder Agent]
    S -->|Analysis needed| A[Analyst Agent]

    R --> S
    C --> S
    A --> S

    S -->|Task complete| END[✅ Final Answer]

    style S fill:#2D9CDB,color:#fff
    style R fill:#7C3AED,color:#fff
    style C fill:#DC2626,color:#fff
    style A fill:#D97706,color:#fff
    style END fill:#22C55E,color:#fff
```

#### Stack
`LangGraph 0.3.21` · `LangChain 0.3.18` · `OpenAI GPT-4o` · `Google Gemini` · `Groq` · `LangSmith` · `SQLite Checkpointing` · `Jupyter`

---

### 3. ✈️ Google ADK

> **Google's native agent platform — a hierarchical multi-agent travel planner powered by Gemini, Google Search, and OpenStreetMap.**

A production-grade multi-agent travel planning system built with **Google Agent Development Kit (ADK)**. Orchestrates specialized AI sub-agents to deliver destination inspiration, real-time travel news, and nearby place discovery — all in one seamless conversation. Uses **zero paid third-party APIs** for place search — powered entirely by OpenStreetMap and Nominatim.

**→ Repository:** [Google-ADK](https://github.com/a-r-ashik/Google-ADK)

#### Multi-Agent Architecture

```mermaid
flowchart TD
    U["👤 User\nNatural language query"] --> TP

    TP["🧳 Travel Planner\nRoot Orchestrator\nCannot use tools directly"]

    TP -->|delegates to| TIA

    TIA["💡 Travel Inspiration Agent\nCore reasoning agent\nInspires · Identifies · Coordinates"]

    TIA -->|events & news| NA
    TIA -->|places & locations| PA

    NA["📰 News Agent\nTop 10 travel events\n& news results"]
    PA["📍 Places Agent\nNearby locations with\nname · address · coordinates"]

    NA -->|uses| GST["🔍 Google Search AgentTool\nADK native google_search grounding\nReal-time web results"]
    PA -->|uses| LT["🗺️ Places FunctionTool\nfind_nearby_places_open()\nGeopy Nominatim → Overpass API OSM\nFully free · No API key required"]

    style TP fill:#4285F4,color:#fff
    style TIA fill:#7C3AED,color:#fff
    style NA fill:#2D9CDB,color:#fff
    style PA fill:#D97706,color:#fff
    style GST fill:#059669,color:#fff
    style LT fill:#059669,color:#fff
```

#### Agent Roles

| Agent | Role | Tools |
|---|---|---|
| **Travel Planner** | Root orchestrator — delegates to sub-agents, cannot call tools directly | — |
| **Travel Inspiration Agent** | Core reasoning — inspires destinations, coordinates News & Places agents | `AgentTool(news_agent)`, `AgentTool(places_agent)` |
| **News Agent** | Fetches real-time travel events, news, and advisories (up to 10 results) | `google_search_grounding` |
| **Places Agent** | Returns nearby hotels, cafés, attractions with name, address & coordinates | `location_search_tool` |

#### Tool Architecture

```mermaid
flowchart LR
    A[💬 User Query] --> B[Travel Planner\nRoot Agent]
    B --> C[Travel Inspiration\nAgent]

    C --> D[News Agent]
    C --> E[Places Agent]

    D --> F[Google Search\nAgentTool\nLive web grounding]
    E --> G[OSM Places\nFunctionTool]

    G --> H[Geopy Nominatim\nGeocode location → lat/lon]
    H --> I[Overpass API\nQuery OSM nodes within radius]
    I --> J[✅ name · address · coords]

    style B fill:#4285F4,color:#fff
    style C fill:#7C3AED,color:#fff
    style F fill:#059669,color:#fff
    style J fill:#22C55E,color:#fff
```

#### Example Interactions

```
User: "I want a beach holiday in Saint Martin"
  └─▶ Travel Planner
        └─▶ Travel Inspiration Agent
              ├─▶ News Agent   → Top 10 events & news in Saint Martin
              └─▶ Places Agent → Hotels & resorts near Orient Bay Beach

User: "Find restaurants near Grand Case, Saint Martin"
  └─▶ Travel Planner
        └─▶ Travel Inspiration Agent
              └─▶ Places Agent → OSM: restaurants within 3km of Grand Case
```

#### Stack
`Google ADK ≥1.33.0` · `Gemini Flash` · `Google Search Grounding` · `Geopy Nominatim` · `Overpass API (OSM)` · `UV` · `Python 3.12+`

---

### 4. 🤝 CrewAI

> **Multi-agent collaboration — specialized agents working in sequence to research and write autonomously.**

A production-style CrewAI project that orchestrates two autonomous AI agents: a **Report Generator** that conducts deep research and a **Blog Writer** that transforms it into an accessible ELI5-style blog post. Output is auto-saved as a `.md` file — ready to publish.

**→ Repository:** [Crew-AI](https://github.com/a-r-ashik/Crew-AI)

#### Agent Pipeline

```mermaid
flowchart TD
    U[💬 User Input\nTopic] --> RG

    subgraph Crew ["🤝 Sequential Crew Pipeline"]
        direction TB
        RG["📋 Report Generator Agent\nRole: Expert Researcher\nGoal: ~1000-word structured report\nCovers: facts · trends · future outlook"]
        BW["✍️ Blog Writer Agent\nRole: Expert Blog Writer\nGoal: ~500-word ELI5 blog post\nStyle: Fun · Simple · Accessible"]
        RG -->|Report passed as context| BW
    end

    BW --> OUT[📄 blogs/output.md\nAuto-saved Markdown]

    style RG fill:#7C3AED,color:#fff
    style BW fill:#2D9CDB,color:#fff
    style OUT fill:#22C55E,color:#fff
```

#### YAML-Driven Configuration

```mermaid
flowchart LR
    A[agents.yaml\nRoles · Goals · Backstories] --> C[crew.py\nOrchestrator]
    B[tasks.yaml\nDescriptions · Expected Outputs] --> C
    C --> D[main.py\nEntry Point]
    D --> E[CrewAI Runner]

    style C fill:#FF4B4B,color:#fff
    style E fill:#22C55E,color:#fff
```

#### Sample Output
Generated blog topic: *"AI Engineering Career Path and Opportunities in Bangladesh 2026"*
- Covers Smart Bangladesh initiative, career specializations, hiring industries, and a beginner's roadmap
- Saved automatically to `blogs/ai_engineering_career_path.md`

#### Roadmap
- [ ] Add web search tool (Tavily) to the researcher agent
- [ ] Add Streamlit UI for live topic input and output display
- [ ] Add a third **Editor Agent** for fact-checking and refinement
- [ ] Integrate LangGraph for conditional agent routing

#### Stack
`CrewAI 1.13.0` · `Google Gemini` · `UV Package Manager` · `YAML Config` · `Python 3.10+`

---

### 5. 🎨 Streamlit

> **Interactive AI-powered web apps — bringing AI backends to life with clean, responsive UIs.**

A collection of three Streamlit applications demonstrating how to build real-time, interactive interfaces. Covers live data fetching, physics simulation, and health calculators — all deployable with a single command.

**→ Repository:** [Started\_with\_Streamlit](https://github.com/a-r-ashik/Started_with_Streamlit)

#### Three Apps

```mermaid
flowchart TD
    S[🎨 Streamlit Collection] --> A
    S --> B
    S --> C

    A["📈 AssetPulse\nReal-time stock & crypto tracker\nYahoo Finance API · Interactive charts\nPrice change · % change · Raw data toggle"]

    B["🏋️ BMI Calculator\nWHO obesity classification\nHeight ft/in + Weight kg input\nColour-coded category labels"]

    C["🛸 Mars Lander Game\nBrowser-based physics simulation\nReal-time gravity + thrust mechanics\nPlotly dark-theme · Live telemetry panel\nWin/crash detection · Restart button"]

    style S fill:#FF4B4B,color:#fff
    style A fill:#2D9CDB,color:#fff
    style B fill:#22C55E,color:#fff
    style C fill:#7C3AED,color:#fff
```

#### Mars Lander Game — Physics Loop

```mermaid
flowchart LR
    A[▶ Game Start] --> B[Physics Tick\nevery 300ms]
    B --> C[Apply Gravity\n+ Thrust]
    C --> D{Altitude\nCheck}
    D -->|Above ground| B
    D -->|Landing velocity\n< threshold| E[🏆 Safe Landing]
    D -->|Landing velocity\n> threshold| F[💥 Crash]
    E --> G[Restart?]
    F --> G
    G --> A

    style A fill:#FF4B4B,color:#fff
    style E fill:#22C55E,color:#fff
    style F fill:#DC2626,color:#fff
```

#### Stack
`Streamlit` · `yfinance` · `Plotly` · `pandas` · `streamlit-autorefresh` · `Python 3.8+`

---

## 🛠 Tech Stack

| Layer | Technologies |
|---|---|
| **Agent Orchestration** | LangGraph 0.3.21, CrewAI 1.13.0, Google ADK ≥1.33.0 |
| **LLM Framework** | LangChain 0.3.18 |
| **LLM Models** | OpenAI GPT-4o, Google Gemini 2.0/2.5/Flash, Groq LLaMA 3.3 70B |
| **State & Memory** | LangGraph SQLite Checkpointing, CrewAI context passing, ADK managed state |
| **Vector Stores** | ChromaDB, FAISS |
| **UI Framework** | Streamlit, Google ADK Web UI |
| **Data Visualization** | Plotly |
| **Observability** | LangSmith tracing |
| **Geospatial** | Geopy Nominatim, Overpass API (OpenStreetMap) |
| **Package Management** | UV, pip, venv |
| **Config** | YAML, python-dotenv |

---

## 🗺 Agentic AI Evolution Map

```mermaid
flowchart TD
    A["🔗 LangChain\nFoundation layer\nChains · Tools · Prompts · Retrievers"]

    A --> B["🔷 LangGraph\nAdd statefulness & cycles\nGraph workflows · Human-in-loop · Streaming"]
    A --> C["🤝 CrewAI\nAdd multi-agent roles\nSequential crews · YAML config · Auto output"]
    A --> D["🎨 Streamlit\nAdd interactive UI\nReal-time apps · User input · Visualization"]
    A --> E["✈️ Google ADK\nGoogle-native agent platform\nHierarchical agents · Gemini · OSM tools"]

    B --> F["🚀 Production Agentic AI\nStateful · Multi-agent · Interactive · Observable"]
    C --> F
    D --> F
    E --> F

    style A fill:#1C3C3C,color:#fff
    style B fill:#2D9CDB,color:#fff
    style C fill:#FF4B4B,color:#fff
    style D fill:#FF4B4B,color:#fff
    style E fill:#4285F4,color:#fff
    style F fill:#1e1b4b,color:#fff
```

Each framework is a deliberate step in mastering a different dimension of the agentic AI design space.

---

## 👤 Author

**Ashikur Rahman**

[![GitHub](https://img.shields.io/badge/GitHub-a--r--ashik-181717?style=for-the-badge&logo=github)](https://github.com/a-r-ashik)

---

> *Also check out **[RAG-Vault](https://github.com/a-r-ashik/RAG-Vault)** — a companion collection of 5 RAG implementations including Simple, Multimodal, Corrective, Vectorless RAG and RAGAS Evaluation.*

---

<div align="center">

*Built with curiosity, one agentic framework at a time.*

</div>
