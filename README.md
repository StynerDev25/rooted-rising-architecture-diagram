%%{ init: { "flowchart": { "nodeSpacing": 25, "rankSpacing": 50 } } }%%
flowchart TD
  %% ──────────  LAYER 1  ──────────
  subgraph "LAYER 1 · Continuous, Immutable Data Feeds"
      DOE["📘 DOE EDFacts API<br/>Federal education data – graduation, attendance"]
      HUD["🏠 HUD & Census API<br/>Income, housing, demographics"]
      DOJ["🚨 DOJ Crime Stats<br/>School safety & crime trends"]
      Campus["🎓 Campus LMS/SIS<br/>Grades, attendance, performance"]
      Stripe["💸 Stripe Donations<br/>Who gave, how much, when (real-time)"]
  end

  %% ──────────  LAYER 2  ──────────
  subgraph "LAYER 2 · Self-Optimizing AI Fabric"
      ConnectorAI["🔗 AI Connector<br/>Parses & formats raw data"]
      HarmonizerAI["🔎 Semantic Harmonizer<br/>Aligns meaning across sources"]
  end

  %% ──────────  LAYER 3  ──────────
  subgraph "LAYER 3 · High-Speed KPI Memory"
      VectorMemory["🧠 Vector Memory DB<br/>Instant metric search & patterns"]
  end

  %% ──────────  LAYER 4  ──────────
  subgraph "LAYER 4 · Tamper-Proof Ledger"
      ICP["🛡️ ICP Smart Contracts<br/>Immutable records of results & funds"]
  end

  %% ──────────  LAYER 5  ──────────
  subgraph "LAYER 5 · Real-Time Streaming API"
      StreamAPI["🚦 GraphQL / REST Gateway<br/>Secure, role-based delivery"]
  end

  %% ──────────  LAYER 6  ──────────
  subgraph "LAYER 6 · User-Facing Dashboards & Apps"
      BingePlayer["📺 Impact Binge Player<br/>Auto-generated result stories"]
      DonorHub["🎁 Donor Transparency Desk<br/>See how every dollar works"]
      OpsConsole["🎛️ Ops Command Center<br/>Live tasks, alerts, audits"]
  end

  %% ──────────  Sentinel  ─────────
  SentinelAI["🛡️ Sentinel AI<br/>Constant fraud/error monitoring"]

  %% ──────────  FLOWS  ────────────
  DOE & HUD & DOJ & Campus & Stripe --> ConnectorAI
  Stripe --> ICP
  ConnectorAI --> HarmonizerAI --> VectorMemory
  VectorMemory -. writes hashes .-> ICP
  VectorMemory --> StreamAPI
  ICP --> StreamAPI
  StreamAPI --> BingePlayer & DonorHub & OpsConsole
  SentinelAI -. audits .- ICP
  SentinelAI -. observes .- VectorMemory
  SentinelAI -. guards .- StreamAPI

  %% ──────────  STYLES  ───────────
  classDef feeds    fill:#d8ebff,stroke:#0047ab,color:#00204a,stroke-width:2px;
  classDef ai       fill:#fff3d9,stroke:#e59f00,color:#3e2600,stroke-width:2px;
  classDef memory   fill:#ecebff,stroke:#5a2dc5,color:#1f0b5b,stroke-width:2px;
  classDef ledger   fill:#e7ffe7,stroke:#1c7f31,color:#083516,stroke-width:2px;
  classDef api      fill:#f8f8f8,stroke:#555555,color:#111111,stroke-width:2px;
  classDef uis      fill:#fff0ea,stroke:#b62b1e,color:#5e100a,stroke-width:2px;
  classDef sentinel fill:#ffecec,stroke:#e60000,color:#6a0000,stroke-width:2px;

  class DOE,HUD,DOJ,Campus,Stripe feeds
  class ConnectorAI,HarmonizerAI ai
  class VectorMemory memory
  class ICP ledger
  class StreamAPI api
  class BingePlayer,DonorHub,OpsConsole uis
  class SentinelAI sentinel

