# FlowSense AI: Project Development Plan

## Project Overview
**FlowSense AI** is an end-to-end AI-powered predictive crowd risk management system. It leverages agent-based simulations to detect and predict dangerous crowd conditions (stampedes, congestion) at large public events, providing AI-driven intervention recommendations.

---

## Phase 1: Research Phase
**Objective:** Establish a theoretical foundation for crowd dynamics and state-of-the-art predictive models.

*   **Tasks for Nishita (AI Engineer):**
    *   Review literature on crowd disasters and benchmark existing Social Force Model (SFM) implementations for O(n^2) complexity bottlenecks.
    *   Develop a technical research summary highlighting mathematical models for speed-density relationships (e.g., Weidmann's formula).
    *   Identify key performance indicators (KPIs) and translate them into measurable software metrics.
*   **Tasks for Aditi (AI Engineer):**
    *   Set up the development environment (Python 3.11+, Mesa, FastAPI) and establish a baseline "Hello World" simulation.
    *   Research agent-based modeling (ABM) frameworks for performance benchmarks.
    *   Evaluate GenAI models via OpenRouter for latency and token-cost efficiency in real-time reasoning.
*   **Expected Deliverables:** Research Summary Document, Bibliography of relevant papers.
*   **Suggested Tools:** Google Scholar, Notion, Zotero.

---

## Phase 2: Problem Discovery
**Objective:** Define specific use cases, scenarios, and project constraints.

*   **Tasks for Nishita (AI Engineer):**
    *   Implement scenario configuration parsers (JSON/YAML) and define spatial boundaries using Shapely/GeoPandas.
    *   Draft technical "User Personas" defining API interaction patterns for the dashboard.
*   **Tasks for Aditi (AI Engineer):**
    *   Define simulated sensor data ingestion protocols (MQTT/WebSocket) and perform capacity limit analysis for environment layouts.
    *   Identify data constraints in simulation vs. real-world sensor data telemetry.
    *   Map out infrastructure "bottlenecks" using grid cell capacity calculation logic.
*   **Expected Deliverables:** Requirement Specification Document, Scenario Definitions.
*   **Suggested Tools:** Miro, Figma (for user journey mapping).

---

## Phase 3: System Design
**Objective:** Design the high-level architecture and data flow between components.

*   **Tasks for Nishita (AI Engineer):**
    *   Design the Agent state machine and interaction protocol for agent-to-agent communication.
    *   Develop the OODA (Observe-Orient-Decide-Act) loop flowchart for AI decision logic.
    *   Review system architecture for alignment with real-time throughput requirements.
*   **Tasks for Aditi (AI Engineer):**
    *   Design the micro-service architecture: Simulation Engine, Analytics Layer, and Agent Brain modules.
    *   Specify Pydantic-based API contracts for Dashboard-Backend communication.
    *   Design an asynchronous message queue for simulation-to-analytics telemetry.
*   **Expected Deliverables:** System Architecture Diagram, API Documentation (Draft), Sequence Diagrams.
*   **Suggested Tools:** Mermaid.js, Lucidchart, Swagger/OpenAPI.

---

## Phase 4: Data Modeling
**Objective:** Define the structures for agents, environments, and risk metrics.

*   **Tasks for Nishita (AI Engineer):**
    *   Implement the Environment class with grid-based spatial indexing for agent proximity checks.
    *   Categorize infrastructure components into spatial zones with unique accessibility attributes.
*   **Tasks for Aditi (AI Engineer):**
    *   Develop the data schema for agent states (position, velocity, vector) using Pydantic.
    *   Implement GeoJSON/JSON data structures for "Zones" and "Accessibility Routes."
    *   Write scripts to generate environment layouts from configuration files.
*   **Expected Deliverables:** Data Schema (Pydantic models), Scenario configuration files.
*   **Suggested Tools:** Pydantic, JSON Schema.

---

## Phase 5: Simulation Development
**Objective:** Build the core agent-based simulation engine using Mesa.

*   **Tasks for Nishita (AI Engineer):**
    *   Implement collision detection logic (Force-based) for human movement.
    *   Add `PanicFactor` as a weight in the movement vector calculation based on local density.
    *   Verify movement logic against real-world crowd movement patterns.
*   **Tasks for Aditi (AI Engineer):**
    *   Implement the `Mesa` Model and Agent base classes with custom schedulers.
    *   Develop A* pathfinding logic with dynamic obstacle avoidance for agent goal-seeking.
    *   Optimize simulation loop performance for high agent counts (>1000).
*   **Expected Deliverables:** Functional Simulation Engine, Demo of agent movement.
*   **Suggested Tools:** Python, Mesa, Matplotlib (for early viz).

---

## Phase 6: Data Analytics Engine
**Objective:** Calculate real-time metrics from the running simulation.

*   **Tasks for Nishita (AI Engineer):**
    *   Develop spatial hashing for O(n) density calculation across the simulation grid.
    *   Implement Directional Conflict and Speed Variance formulas in NumPy.
    *   Establish "Warning" and "Danger" thresholds trigger logic.
*   **Tasks for Aditi (AI Engineer):**
    *   Build a Pandas-based telemetry pipeline to process agent snapshots every `t` steps.
    *   Implement a time-series log of all metrics for historic analysis and replay.
    *   Develop the Analytics Module for real-time metric broadcasting.
*   **Expected Deliverables:** Analytics Module, Real-time Metric Processor.
*   **Suggested Tools:** Pandas, NumPy, Scipy.

---

## Phase 7: Risk Prediction Model
**Objective:** Implement the Weighted Risk Score formula and predictive logic.

*   **Tasks for Nishita (AI Engineer):**
    *   Implement the Weighted Risk Score formula: `0.35 Density + 0.25 Conflict + 0.20 Speed + 0.20 Congestion`.
    *   Write unit tests to verify risk score accuracy across standard simulation scenarios.
*   **Tasks for Aditi (AI Engineer):**
    *   Develop a "Future-State Predictor" (Linear Extrapolation / Markov Chain) to forecast risk in `T+10` steps.
    *   Implement the Threshold Alert System that triggers events based on predictive risk scores.
*   **Expected Deliverables:** Risk Prediction Module, Threshold Alert System.
*   **Suggested Tools:** Python, Statsmodels.

---

## Phase 8: AI Agent System
**Objective:** Build the decision-making brain using LangGraph or CrewAI.

*   **Tasks for Nishita (AI Engineer):**
    *   Implement the intervention decision-tree (Policy Designer) for the Agent brain.
    *   Define the logic-set for "AI Playbooks" (e.g., Gate Redirection logic).
*   **Tasks for Aditi (AI Engineer):**
    *   Implement a LangGraph execution flow that receives real-time Risk Scores as input.
    *   Develop interface tools (Python functions) for the agent to "intervene" in the Mesa environment.
    *   Implement integration between the analytics engine and the LangGraph brain.
*   **Expected Deliverables:** LangGraph/CrewAI Agent Logic, Intervention Toolset.
*   **Suggested Tools:** LangGraph, CrewAI, LangChain.

---

## Phase 9: GenAI Integration (Explanation Layer)
**Objective:** Provide human-readable explanations for AI decisions.

*   **Tasks for Nishita (AI Engineer):**
    *   Engineer dynamic prompt templates for SITREP generation with structured output.
    *   Implement output parsing to ensure natural language responses map to actionable alerts.
*   **Tasks for Aditi (AI Engineer):**
    *   Integrate OpenRouter API with async retry logic and error handling.
    *   Develop a context-assembler to pass simulation "snapshots" into LLM prompts effectively.
    *   Implement a caching layer for LLM responses to reduce token costs in similar scenarios.
*   **Expected Deliverables:** Natural Language Explanation Module.
*   **Suggested Tools:** OpenRouter, GPT-4o or Claude 3.5 Sonnet.

---

## Phase 10: Dashboard Development
**Objective:** Build the command-and-control visualization interface.

*   **Tasks for Nishita (AI Engineer):**
    *   Build the frontend components using React or Vanilla JS/CSS for real-time visualization.
    *   Implement a 2D/Canvas-based visualization of the crowd using the raw WebSocket stream.
*   **Tasks for Aditi (AI Engineer):**
    *   Develop a FastAPI backend to stream simulation and risk data via WebSockets.
    *   Implement the state-broadcasting logic for sub-second visual updates.
    *   Ensure cross-thread safety between the simulation loop and the WebSocket broadcast.
*   **Expected Deliverables:** Real-time Dashboard, WebSocket Server.
*   **Suggested Tools:** FastAPI, Leaflet.js / D3.js, Tailwind CSS (optional).

---

## Phase 11: System Integration
**Objective:** Connect all modules into a singular, cohesive pipeline.

*   **Tasks for Nishita (AI Engineer):**
    *   Lead the development of end-to-end integration tests (Simulation -> Analytics -> Dashboard).
    *   Perform thread-safety validation and concurrent access checks for shared simulation state.
*   **Tasks for Aditi (AI Engineer):**
    *   Containerize the entire application stack using Docker and Docker-Compose.
    *   Set up a CI/CD pipeline (GitHub Actions) for automated testing and linting.
    *   Optimize resource allocation for the Docker containers.
*   **Expected Deliverables:** Integrated Project Prototype.
*   **Suggested Tools:** Docker, GitHub Actions (CI).

---

## Phase 12: Testing and Experiments
**Objective:** Stress-test the system with "Black Swan" scenarios.

*   **Tasks for Nishita (AI Engineer):**
    *   Implement automated "Black Swan" scenario triggers (e.g., Sudden Gate Closure script).
    *   Analyze agent response latency vs. crowd density using qualitative and quantitative metrics.
*   **Tasks for Aditi (AI Engineer):**
    *   Execute batch simulations (Monte Carlo) to evaluate intervention effectiveness across 100+ runs.
    *   Collect and visualize performance benchmarks (RAM/CPU usage) for various agent scales.
*   **Expected Deliverables:** Experiment Report, Comparative Analysis (Agent vs. No-Agent).
*   **Suggested Tools:** Jupyter Notebooks, Plotly.

---

## Phase 13: Documentation & Research Paper
**Objective:** Finalize project collateral for the conference submission and LinkedIn.

*   **Tasks for Nishita (AI Engineer):**
    *   Write the "Technical Implementation" and "Algorithms" sections of the research paper.
    *   Create technical visualizations including flowcharts and system architecture diagrams.
*   **Tasks for Aditi (AI Engineer):**
    *   Document the "Risk Prediction Model" and "Agent Architecture" sections of the paper.
    *   Write technical documentation (README.md, Environment Setup, and API Specs).
*   **Expected Deliverables:** GitHub Repository (Clean), Research Paper (PDF), Project Video Demo.
*   **Suggested Tools:** LaTeX (Overleaf), Markdown, Loom (for demo).
