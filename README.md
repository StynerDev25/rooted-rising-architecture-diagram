# Rooted & Rising – Immutable Trust Engine Architecture

![Architecture Diagram](Rooted_Rising_Architecture.svg)

> Mermaid source is included below for easy edits.  
> The SVG above guarantees the diagram always shows, even if Mermaid has issues.

---

## 📐 Mermaid source

```mermaid
flowchart TD
  %% data feeds
  subgraph "LAYER 1 · Continuous, Immutable Data Feeds"
      DOE["📘 DOE EDFacts API<br/>graduation & attendance"]
      HUD["🏠 HUD/Census API<br/>income & housing"]
      DOJ["🚨 DOJ Crime Stats<br/>school safety"]
      Campus["🎓 Campus LMS/SIS<br/>grades & reports"]
      Stripe["💸 Stripe Donations<br/>real-time gifts"]
  end

  %% AI layer
  subgraph "LAYER 2 · Self-Optimizing AI Fabric"
      ConnectorAI["🔗 AI Connector"]
      HarmonizerAI["🔎 Semantic Harmonizer"]
  end

  %% Vector DB
  subgraph "LAYER 3 · High-Speed KPI Memory"
      VectorMemory["🧠 Vector Memory DB"]
  end

  %% Ledger
  subgraph "LAYER 4 · Tamper-Proof Ledger"
      ICP["🛡️ ICP Smart Contracts"]
  end

  %% API gateway
  subgraph "LAYER 5 · Real-Time Streaming API"
      StreamAPI["🚦 GraphQL / REST Gateway"]
  end

  %% Dashboards
  subgraph "LAYER 6 · User-Facing Dashboards & Apps"
      BingePlayer["📺 Impact Binge Player"]
      DonorHub["🎁 Donor Transparency Desk"]
      OpsConsole["🎛️ Operations Console"]
  end

  %% Sentinel
  SentinelAI["🛡️ Sentinel AI"]

  %% flows
  DOE & HUD & DOJ & Campus & Stripe --> ConnectorAI
  Stripe --> ICP
  ConnectorAI --> HarmonizerAI --> VectorMemory
  VectorMemory -.-> ICP
  VectorMemory --> StreamAPI
  ICP --> StreamAPI
  StreamAPI --> BingePlayer & DonorHub & OpsConsole
  SentinelAI -.-> ICP & VectorMemory & StreamAPI

  %% simple styling (GitHub allows hex + basic attrs)
  classDef feeds    fill:#d8ebff,stroke:#0047ab,color:#00204a;
  classDef ai       fill:#fff5d6,stroke:#e59f00,color:#3e2600;
  classDef memory   fill:#ecebff,stroke:#5a2dc5,color:#1f0b5b;
  classDef ledger   fill:#e7ffe7,stroke:#1c7f31,color:#083516;
  classDef api      fill:#f8f8f8,stroke:#555,color:#111;
  classDef uis      fill:#fff0ea,stroke:#b62b1e,color:#5e100a;
  classDef sentinel fill:#ffecec,stroke:#e60000,color:#6a0000;

  class DOE,HUD,DOJ,Campus,Stripe feeds
  class ConnectorAI,HarmonizerAI ai
  class VectorMemory memory
  class ICP ledger
  class StreamAPI api
  class BingePlayer,DonorHub,OpsConsole uis
  class SentinelAI sentinel

