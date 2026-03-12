# FlowSense AI: Project Development Plan

## Project Overview
**FlowSense AI** is an end-to-end AI-powered predictive crowd risk management system. It leverages agent-based simulations to detect and predict dangerous crowd conditions (stampedes, congestion) at large public events, providing AI-driven intervention recommendations.

---

## Phase 1: Research Phase
**Objective:** Establish a theoretical foundation for crowd dynamics and state-of-the-art predictive models.

*   **Tasks for Nishita (AI PM):**
    *   Conduct a literature review on crowd disasters (e.g., Hillsborough, Love Parade).
    *   Analyze existing crowd management protocols and international safety standards.
    *   Identify key performance indicators (KPIs) for event safety.
*   **Tasks for Aditi (AI Engineer):**
    *   Research agent-based modeling (ABM) frameworks (specifically Mesa).
    *   Investigate Force-Based Models (Social Force Model) for human movement.
    *   Evaluate GenAI models available through OpenRouter for reasoning tasks.
*   **Expected Deliverables:** Research Summary Document, Bibliography of relevant papers.
*   **Suggested Tools:** Google Scholar, Notion, Zotero.

---

## Phase 2: Problem Discovery
**Objective:** Define specific use cases, scenarios, and project constraints.

*   **Tasks for Nishita (AI PM):**
    *   Define 3 core scenarios: Music Festival (open field), Stadium Match (structured entry/exit), and Religious Gathering.
    *   Draft "User Personas" for the dashboard (Event Safety Officer, Security Lead).
    *   Define non-functional requirements (real-time latency, accuracy).
*   **Tasks for Aditi (AI Engineer):**
    *   Identify data constraints in simulation vs. real-world sensor data.
    *   Map out infrastructure "bottlenecks" common in large events.
*   **Expected Deliverables:** Requirement Specification Document, Scenario Definitions.
*   **Suggested Tools:** Miro, Figma (for user journey mapping).

---

## Phase 3: System Design
**Objective:** Design the high-level architecture and data flow between components.

*   **Tasks for Nishita (AI PM):**
    *   Define the intervention hierarchy (automated vs. human-in-the-loop).
    *   Review system architecture for alignment with project goals.
*   **Tasks for Aditi (AI Engineer):**
    *   Design the micro-service architecture: Simulation Engine, Analytics Layer, Agent Brain.
    *   Design API contracts between FastAPI (backend) and the Dashboard.
    *   Create a flowchart of the "Observe-Orient-Decide-Act" (OODA) loop for the agents.
*   **Expected Deliverables:** System Architecture Diagram, API Documentation (Draft), Sequence Diagrams.
*   **Suggested Tools:** Mermaid.js, Lucidchart, Swagger/OpenAPI.

---

## Phase 4: Data Modeling
**Objective:** Define the structures for agents, environments, and risk metrics.

*   **Tasks for Nishita (AI PM):**
    *   Define agent personas (e.g., "High-Panic Individual," "Staff Member").
    *   Catalog infrastructure components (Stage, VIP, Toilets, Exit A, etc.).
*   **Tasks for Aditi (AI Engineer):**
    *   Develop the data schema for agent states (position, velocity, vector).
    *   Implement data structures for "Zones" and "Accessibility Routes" in GeoJSON/JSON.
*   **Expected Deliverables:** Data Schema (Pydantic models), Scenario configuration files.
*   **Suggested Tools:** Pydantic, JSON Schema.

---

## Phase 5: Simulation Development
**Objective:** Build the core agent-based simulation engine using Mesa.

*   **Tasks for Nishita (AI PM):**
    *   Verify movement logic matches real-world human behavior (e.g., herd mentality).
    *   Provide feedback on "visual" realism of the simulation runs.
*   **Tasks for Aditi (AI Engineer):**
    *   Implement the `Mesa` Model and Agent classes.
    *   Develop the obstacle avoidance and goal-seeking logic (A* or Dijkstra).
    *   Add "Panic Sensitivity" as a variable that modifies speed and collision logic.
*   **Expected Deliverables:** Functional Simulation Engine, Demo of agent movement.
*   **Suggested Tools:** Python, Mesa, Matplotlib (for early viz).

---

## Phase 6: Data Analytics Engine
**Objective:** Calculate real-time metrics from the running simulation.

*   **Tasks for Nishita (AI PM):**
    *   Finalize the definitions of "Directional Conflict" and "Speed Variance."
    *   Establish "Warning" and "Danger" thresholds for each metric.
*   **Tasks for Aditi (AI Engineer):**
    *   Build a Pandas/NumPy pipeline to process agent snapshots every `t` steps.
    *   Implement density calculation using spatial hashing or grid-based counting.
    *   Develop a time-series log of all metrics for historic analysis.
*   **Expected Deliverables:** Analytics Module, Real-time Metric Processor.
*   **Suggested Tools:** Pandas, NumPy, Scipy.

---

## Phase 7: Risk Prediction Model
**Objective:** Implement the Weighted Risk Score formula and predictive logic.

*   **Tasks for Nishita (AI PM):**
    *   Fine-tune the weights: `0.35 Density + 0.25 Conflict + 0.20 Speed + 0.20 Congestion`.
    *   Verify simulation scenarios trigger the risk score accurately.
*   **Tasks for Aditi (AI Engineer):**
    *   Implement the Risk Score Calculator.
    *   Develop a "Future-State Predictor" (simple linear extrapolation or Markov chain) to predict risk in `T+10` steps.
*   **Expected Deliverables:** Risk Prediction Module, Threshold Alert System.
*   **Suggested Tools:** Python, Statsmodels.

---

## Phase 8: AI Agent System
**Objective:** Build the decision-making brain using LangGraph or CrewAI.

*   **Tasks for Nishita (AI PM):**
    *   Define the "Playbook" of interventions (e.g., Case 1: High Density -> Action: Redirect to Exit B).
    *   Act as the "Policy Designer" for the AI agents.
*   **Tasks for Aditi (AI Engineer):**
    *   Implement an Agent Graph (LangGraph) that receives Risk Scores as input.
    *   Develop tools/functions for the agent to "intervene" in the simulation (e.g., `open_gate(gate_id)`).
*   **Expected Deliverables:** LangGraph/CrewAI Agent Logic, Intervention Toolset.
*   **Suggested Tools:** LangGraph, CrewAI, LangChain.

---

## Phase 9: GenAI Integration (Explanation Layer)
**Objective:** Provide human-readable explanations for AI decisions.

*   **Tasks for Nishita (AI PM):**
    *   Define the "Tone of Voice" for the AI assistant (Professional, Urgent).
    *   Design the structure of the "Situation Report" (SITREP).
*   **Tasks for Aditi (AI Engineer):**
    *   Integrate OpenRouter to pass the "Risk Context" to an LLM.
    *   Prompt Engineering to generate explanations like: *"Red Alert: Density at Gate 4 is 4.5 pax/sqm due to influx from Stage A. Recommendation: Open Gate 5 immediately to vent flow north."*
*   **Expected Deliverables:** Natural Language Explanation Module.
*   **Suggested Tools:** OpenRouter, GPT-4o or Claude 3.5 Sonnet.

---

## Phase 10: Dashboard Development
**Objective:** Build the command-and-control visualization interface.

*   **Tasks for Nishita (AI PM):**
    *   Wireframe the dashboard layout.
    *   Ensure the "Risk Score" is the most prominent visual element.
*   **Tasks for Aditi (AI Engineer):**
    *   Develop a FastAPI backend to stream simulation data via WebSockets.
    *   Build the frontend using Vanilla JS/CSS or React.
    *   Implement a 2D/Canvas-based visualization of the crowd.
*   **Expected Deliverables:** Real-time Dashboard, WebSocket Server.
*   **Suggested Tools:** FastAPI, Leaflet.js / D3.js, Tailwind CSS (optional).

---

## Phase 11: System Integration
**Objective:** Connect all modules into a singular, cohesive pipeline.

*   **Tasks for Nishita (AI PM):**
    *   Lead the "Integration Testing" sessions.
    *   Validate the end-to-end flow from Simulation -> Dashboard.
*   **Tasks for Aditi (AI Engineer):**
    *   Containerize the application (optional but recommended).
    *   Ensure thread-safety between the simulation loop and the API.
*   **Expected Deliverables:** Integrated Project Prototype.
*   **Suggested Tools:** Docker, GitHub Actions (CI).

---

## Phase 12: Testing and Experiments
**Objective:** Stress-test the system with "Black Swan" scenarios.

*   **Tasks for Nishita (AI PM):**
    *   Design the "Panic Test": What happens if a fire alarm goes off in the simulation?
    *   Record qualitative observations of AI agent effectiveness.
*   **Tasks for Aditi (AI Engineer):**
    *   Run batch simulations (Monte Carlo) to see how interventions reduce average risk score across 100 runs.
    *   Collect performance metrics (latency of the agent graph).
*   **Expected Deliverables:** Experiment Report, Comparative Analysis (Agent vs. No-Agent).
*   **Suggested Tools:** Jupyter Notebooks, Plotly.

---

## Phase 13: Documentation & Research Paper
**Objective:** Finalize project collateral for the conference submission and LinkedIn.

*   **Tasks for Nishita (AI PM):**
    *   Draft the "Abstract" and "Conclusion" of the research paper.
    *   Create a "Build-in-Public" content calendar for LinkedIn (videos, carousels).
*   **Tasks for Aditi (AI Engineer):**
    *   Write technical documentation (README.md, Setup Guide).
    *   Document the "Risk Model" and "Agent Architecture" sections of the paper.
*   **Expected Deliverables:** GitHub Repository (Clean), Research Paper (PDF), Project Video Demo.
*   **Suggested Tools:** LaTeX (Overleaf), Markdown, Loom (for demo).
