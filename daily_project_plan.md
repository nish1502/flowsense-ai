# 🚀 FlowSense AI: 14-Day Rapid Build & Deploy Plan

This plan is optimized for **Antigravity** (your AI assistant), with daily **GitHub** syncing and mandatory **Testing Phases**. On **Day 15**, we deploy!

---

## 🛠️ The Tech Stack (What we are using)
- **Programming Language:** Python 3.11+
- **"Virtual People" Simulator:** `Mesa` (Python library for agent-based modeling)
- **The Engine (Backend):** `FastAPI` (Very fast tool to connect code to the web)
- **The Screen (Frontend):** `HTML5`, `Vanilla CSS`, `Javascript` (Simple and powerful)
- **The AI Brain:** `LangGraph` + `OpenRouter` (To connect to smart AI like Claude/GPT-4)
- **Data Math:** `Pandas` & `NumPy` (For counting and calculating risk)
- **Tools:** `VS Code`, `GitHub`, `Docker` (Optional but good for deployment)

---

## 📅 14-Day Sprint (Day-by-Day)

### **Phase 1: Environment & Research (Days 1)**
*Objective: Get everything ready and synced with GitHub.*
- **Day 1:**
  - **Both:** Set up a GitHub Repository. Connect it to VS Code.
  - **Nishita:** Research crowd disasters. Define "Danger Thresholds" (e.g., 5 people per meter = Red).
  - **Aditi:** Set up Python Environment. Install `Mesa`, `FastAPI`, and `Pandas`.
  - **End of Day:** Git Commit & Push.

---

### **Phase 2: Core Simulation (Days 2-4)**
*Objective: Make virtual people move and avoid walls.*
- **Day 2:**
  - **Nishita:** Define agent rules (speed, goals).
  - **Aditi:** Code the `Mesa` Grid and a simple "Person" agent.
- **Day 3:** 
  - **Both:** Add obstacles (walls/gates) and pathfinding (how agents find the best route).
- **Day 4: 🧪 PHASE 1-2 TESTING:**
  - **Both:** Run the simulation. Check: Do people walk through walls? (Bug!). Do they reach the exit?
  - **End of Day:** Fix bugs + Git Push.

---

### **Phase 3: Analytics & Risk Score (Days 5-7)**
*Objective: Teach the computer to measure "Crowd Danger."*
- **Day 5:** 
  - **Nishita:** Create a math formula for "Risk Score" (Density + Speed Conflict).
  - **Aditi:** Build the data logger (save per-second agent locations).
- **Day 6:**
  - **Nishita:** Set up "Visual Alerts" logic (turn zones red if score is high).
  - **Aditi:** Build the real-time density counter using NumPy.
- **Day 7: 🧪 PHASE 3 TESTING:**
  - **Both:** Run a crowded scenario. Does the "Risk Score" go up correctly?
  - **End of Day:** Fix any math errors + Git Push.

---

### **Phase 4: The AI Brain (Days 8-10)**
*Objective: Connect the AI to think and give advice.*
- **Day 8:** 
  - **Nishita:** Write "AI Playbooks" (If Gate A is full -> Advice: Open Gate B).
  - **Aditi:** Connect to OpenRouter API. Test a simple "Hello AI" call.
- **Day 9:**
  - **Both:** Use `LangGraph` to pass "Danger Scores" to the AI and get advice.
- **Day 10: 🧪 PHASE 4 TESTING:**
  - **Both:** Ask the AI: "Gate A is crowded, what should I do?" Check if its advice matches the playbook.
  - **End of Day:** Tweak AI prompts + Git Push.

---

### **Phase 5: The Dashboard & Real-time Visuals (Days 11-13)**
*Objective: Build the screen safety officers will use.*
- **Day 11:** 
  - **Nishita:** Design the Dashboard layout (Map on left, AI notes on right).
  - **Aditi:** Build the `FastAPI` server and WebSocket (for real-time data flow).
- **Day 12:**
  - **Both:** Build the Map visualization using HTML Canvas or a map library like Leaflet.js.
- **Day 13: 🧪 SYSTEM INTEGRATION TESTING:**
  - **Both:** Connect everything. Simulation -> Data -> AI -> Dashboard. Does the map update live?
  - **End of Day:** Performance optimization + Git Push.

---

### **Phase 6: Final Stress Test & Launch (Days 14-15)**
*Objective: Break the system to make it stronger, then go live.*
- **Day 14:**
  - **Both:** **"Black Swan" Testing.** Simulate a fire or a sudden gate closure. Check if the AI helps people escape successfully.
  - **End of Day:** Final UI polish and code cleanup.
- **Day 15: 🚀 DEPLOYMENT DAY:**
  - **Both:** Deploy the Backend to **Render/Railway** and Frontend to **Vercel/GitHub Pages**.
  - **Final Task:** Write a clean `README.md` and record a project demo.

---

## 💡 How to use Antigravity (Your AI Assistant)
1. **Coding:** Say "Antigravity, help me write the Mesa Agent class for Day 2."
2. **Debugging:** If you see an error, paste it and say "Antigravity, why is my WebSocket failing?"
3. **Daily GitHub:** At 5 PM every day, say "Antigravity, help me commit and push today's work with a good message."

**Final Tip:** Don't skip the **Testing Days**. If something is broken on Day 4, don't start Day 5 until it is fixed! 🛠️
