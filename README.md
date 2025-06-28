# Rooted & Rising – Immutable Trust Engine Architecture

![Architecture Diagram](Rooted_Rising_Architecture.svg)

> Mermaid source is included below for easy edits.
> The SVG above guarantees the diagram always shows, even if Mermaid has issues.

---

## 📐 Mermaid source

```mermaid
%%{ init: { "flowchart": { "nodeSpacing": 25, "rankSpacing": 50 } } }%%
flowchart TD
  %% ───── LAYER 1 ─────
  subgraph "LAYER 1 · Continuous, Immutable Data Feeds"
      DOE["📘 DOE EDFacts API<br/>Federal education data — graduation & attendance"]
      HUD["🏠 HUD & Census API<br/>Neighborhood income, housing & demographics"]
      DOJ["🚨 DOJ Crime Stats<br/>School safety & crime trends"]
      Campus["🎓 Campus LMS/SIS<br/>Grades, attendance & performance reports"]
      Stripe["💸 Stripe Donations<br/>Who gave, how much, when — real‑time"]
  end

  %% LAYER 2
  subgraph "LAYER 2 · Self‑Optimizing AI Fabric"
      ConnectorAI["🔗 AI Connector<br/>Parses & formats raw data automatically"]
      HarmonizerAI["🔎 Semantic Harmonizer<br/>Aligns meaning across all sources"]
  end

  %% LAYER 3
  subgraph "LAYER 3 · High‑Speed KPI Memory"
      VectorMemory["🧠 Vector Memory DB<br/>Instant search of every metric & pattern"]
  end

  %% LAYER 4
  subgraph "LAYER 4 · Tamper‑Proof Ledger"
      ICP["🛡️ ICP Smart Contracts<br/>Immutable records of results & funds"]
  end

  %% LAYER 5
  subgraph "LAYER 5 · Real‑Time Streaming API"
      StreamAPI["🚦 GraphQL / REST Gateway<br/>Secure, role‑based data delivery"]
  end

  %% LAYER 6
  subgraph "LAYER 6 · User‑Facing Dashboards & Apps"
      BingePlayer["📺 Impact Binge Player<br/>Auto‑created stories; voice & video ready"]
      DonorHub["🎁 Donor Transparency Desk<br/>See exactly how every dollar works"]
      OpsConsole["🎛️ Operations Command Center<br/>Live tasks, alerts & internal audits"]
  end

  %% Sentinel
  SentinelAI["🛡️ Sentinel AI<br/>Continuous fraud, error & security monitoring"]

  %% FLOWS
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

  %% STYLES
  classDef feeds    fill:#d8ebff,stroke:#0047ab,color:#00204a,stroke-width:2px;
  classDef ai       fill:#fff3d9,stroke:#e59f00,color:#3e2600,stroke-width:2px;
  classDef memory   fill:#ecebff,stroke:#5a2dc5,color:#1f0b5b,stroke-width:2px;
  classDef ledger   fill:#e7ffe7,stroke:#1c7f31,color:#083516,stroke-width:2px;
  classDef api      fill:#f8f8f8,stroke:#555,color:#111,stroke-width:2px;
  classDef uis      fill:#fff0ea,stroke:#b62b1e,color:#5e100a,stroke-width:2px;
  classDef sentinel fill:#ffecec,stroke:#e60000,color:#6a0000,stroke-width:2px;

  class DOE,HUD,DOJ,Campus,Stripe feeds
  class ConnectorAI,HarmonizerAI ai
  class VectorMemory memory
  class ICP ledger
  class StreamAPI api
  class BingePlayer,DonorHub,OpsConsole uis
  class SentinelAI sentinel
```

---

### 🔄 How to update the diagram

1. Open [https://mermaid.live](https://www.mermaidchart.com/app/projects/52f96f5a-3aac-4812-90c8-954dd2c42e7c/diagrams/cbe5c900-dc81-4ed2-a46f-41e54f28b622/version/v0.1/edit).
2. Paste the code block above and tweak any node or styling.
3. Export → **SVG** and overwrite `Rooted_Rising_Architecture.svg`.
4. Commit & push—GitHub will display both the static SVG and the live Mermaid source.

---

## 📁 Repo contents

```
/README.md                     ← this file
/Rooted_Rising_Architecture.svg← rendered SVG for quick preview
```

---

## 📝 License

Not MIT — Please do not fork, remix, or cite with a link back.

**Maintainer:** Styner Stiner · [stynerdev@gmail.com](mailto:stynerdev@gmail.com)
