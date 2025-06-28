# Rooted & Rising – Immutable Trust Engine Architecture
**Public reference diagram (Mermaid + SVG) for the Rooted & Rising impact platform**

Traditional civic-impact reports are fragmented and hard to verify.  
Rooted & Rising fixes that with a six-layer “Trust Engine” that turns live data feeds into tamper-proof metrics and stakeholder-ready dashboards.

---

## 📐 System Blueprint (Mermaid)

<details>
<summary>Click to view / edit Mermaid source</summary>

```mermaid
%% Mermaid config
config:
  layout: fixed
---
flowchart TD
  subgraph subGraph0["LAYER 1 · Continuous, Immutable Data Feeds"]
        DOE["📘 DOE EDFacts API<br><small>Federal education data — graduation, attendance</small>"]
        HUD["🏠 HUD &amp; Census API<br><small>Neighborhood income, housing, demographics</small>"]
        DOJ["🚨 DOJ Crime Stats<br><small>School safety &amp; crime trends</small>"]
        Campus["🎓 Campus LMS/SIS<br><small>Grades, attendance, performance reports</small>"]
        Stripe["💸 Stripe Donations<br><small>Who gave, how much, when — real-time</small>"]
  end
  subgraph subGraph1["LAYER 2 · Self-Optimizing AI Fabric"]
        ConnectorAI["🔗 AI Connector<br><small>Understands + formats raw data automatically</small>"]
        HarmonizerAI["🔎 Semantic Harmonizer<br><small>Aligns data meaning across sources</small>"]
  end
  subgraph subGraph2["LAYER 3 · High-Speed KPI Memory"]
        VectorMemory["🧠 Vector Memory DB<br><small>Instant search of all metrics; finds patterns</small>"]
  end
  subgraph subGraph3["LAYER 4 · Tamper-Proof Ledger"]
        ICP["🛡️ ICP Smart Contracts<br><small>Unchangeable records proving results + funds</small>"]
  end
  subgraph subGraph4["LAYER 5 · Real-Time Streaming API"]
        StreamAPI["🚦 GraphQL + REST Gateway<br><small>Secure, role-based data delivery instantly</small>"]
  end
  subgraph subGraph5["LAYER 6 · User-Facing Dashboards &amp; Apps"]
        BingePlayer["📺 Impact Binge Player<br><small>Auto-made stories of results; voice/video ready</small>"]
        DonorHub["🎁 Donor Transparency Desk<br><small>See how every dollar makes an impact</small>"]
        OpsConsole["🎛️ Operations Command Center<br><small>Live tasks, alerts, and internal audits</small>"]
  end
  subgraph subGraph6[" "]
        SentinelAI["🛡️ Sentinel AI<br><small>Constant monitoring for fraud, errors, or hacks</small>"]
  end
    DOE --> ConnectorAI
    HUD --> ConnectorAI
    DOJ --> ConnectorAI
    Campus --> ConnectorAI
    Stripe --> ConnectorAI & ICP
    ConnectorAI --> HarmonizerAI
    HarmonizerAI --> VectorMemory
    VectorMemory -. writes hashes .-> ICP
    VectorMemory --> StreamAPI
    ICP --> StreamAPI
    StreamAPI --> BingePlayer & DonorHub & OpsConsole
    SentinelAI -. audits .- ICP
    SentinelAI -. observes .- VectorMemory
    SentinelAI -. guards .- StreamAPI
     DOE:::feeds
     HUD:::feeds
     DOJ:::feeds
     Campus:::feeds
     Stripe:::feeds
     ConnectorAI:::ai
     HarmonizerAI:::ai
     VectorMemory:::memory
     ICP:::ledger
     StreamAPI:::api
     BingePlayer:::uis
     DonorHub:::uis
     OpsConsole:::uis
     SentinelAI:::sentinel
    classDef feeds    fill:#d8ebff,stroke:#0047ab,stroke-width:2px,color:#00204a
    classDef ai       fill:#fff3d9,stroke:#e59f00,stroke-width:2px,color:#3e2600
    classDef memory   fill:#e9e9ff,stroke:#5a2dc5,stroke-width:2px,color:#1f0b5b
    classDef ledger   fill:#e7ffe7,stroke:#1c7f31,stroke-width:2px,color:#083516
    classDef api      fill:#f8f8f8,stroke:#555,stroke-width:2px,color:#111
    classDef uis      fill:#fff5f0,stroke:#b62b1e,stroke-width:2px,color:#5e100a font-style:italic
    classDef sentinel fill:#ffecec,stroke:#e60000,stroke-width:2px,color:#6a0000 font-style:italic

