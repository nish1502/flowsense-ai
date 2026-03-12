# FlowSense AI 🌊🤖

### **Predictive Crowd Risk Management via Agent-Based Simulation & Agentic AI**

[![Project Phase](https://img.shields.io/badge/Project%20Status-Research%20%26%20Design-orange?style=for-the-badge)](./phase_wise_plan.md)
[![Tech Stack](https://img.shields.io/badge/Tech%20Stack-Python%20|%20Mesa%20|%20LangGraph-blue?style=for-the-badge)](#tech-stack)

**FlowSense AI** is an end-to-end AI-powered system designed to detect and predict dangerous crowd conditions (stampedes, extreme congestion) before they escalate. By leveraging agent-based simulations and agentic decision-making, we provide event organizers with actionable, real-time interventions to save lives.

---

## 🚀 Key Features

- **Agent-Based Crowd Simulation**: Simulates individual human behavior using the Mesa framework, including position, speed, and panic sensitivity.
- **Real-Time Risk Analytics**: Calculates a dynamic **Crowd Risk Score** based on density, directional conflicts, speed variance, and congestion.
- **Agentic AI Decision System**: A LangGraph/CrewAI driven "brain" that recommends interventions like opening emergency gates or redirecting flows.
- **GenAI Explanation Layer**: Translates complex spatial data into natural language situation reports (SITREPs) via OpenRouter.
- **Command & Control Dashboard**: A high-fidelity visualization layer for event safety officers.

---

## 🧠 The Risk Model

Our system doesn't just look at how many people are in a space; it looks at how they move.
The **Risk Score** is calculated as:
$$Risk = 0.35 \times Density + 0.25 \times DirConflict + 0.20 \times SpeedVar + 0.20 \times Congestion$$

---

## 🛠 Tech Stack

- **Simulation**: [Mesa](https://mesa.readthedocs.io/) (Agent-Based Modeling)
- **Engine**: Python, Pandas, NumPy
- **Agent Framework**: [LangGraph](https://www.langchain.com/langgraph) / [CrewAI](https://www.crewai.com/)
- **GenAI Layer**: OpenRouter (GPT-4o / Claude 3.5 Sonnet)
- **Backend API**: FastAPI
- **Frontend Visualization**: HTML5, CSS3, JavaScript (D3.js / Leaflet.js)

---

## 📂 Project Structure

```text
flowsense-ai/
├── src/
│   ├── simulation/      # Mesa model and agent logic
│   ├── analytics/       # Risk score calculation engine
│   ├── agents/          # LangGraph decision logic
│   └── api/             # FastAPI backend
├── dashboard/           # Frontend visualization
├── docs/                # Research papers and design docs
├── phase_wise_plan.md   # Detailed development roadmap
└── README.md
```

---

## 👥 The team

| Name | Role | Responsibility |
| :--- | :--- | :--- |
| **Nishita** | AI Product Manager | System Design, Scenario Modeling, Policy Design |
| **Aditi** | AI Engineer | Simulation Development, Agent Frameworks, Integration |

---

## 📈 Roadmap

We are currently in the **Research & System Design** phase. Check out our [Phase-wise Development Plan](./phase_wise_plan.md) for the full roadmap.

1.  [x] Project Conceptualization
2.  [ ] Phase 1-4: Research, System Design & Data Modeling
3.  [ ] Phase 5-8: Simulation & AI Agent Development
4.  [ ] Phase 9-11: Dashboard & System Integration
5.  [ ] Phase 12-13: Testing, Experiments & Research Paper

---

## 📝 Research & Publications

This project aims to produce a conference paper focused on the synergy between **Agent-Based Modeling (ABM)** and **Agentic AI** in public safety. Stay tuned for updates!

---

## 🏗 Setup & Installation (Coming Soon)

```bash
# Clone the repo
git clone https://github.com/nish1502/flowsense-ai.git

# Install dependencies
pip install -r requirements.txt
```

---
*Developed with ❤️ for a safer world.*
