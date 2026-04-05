# FlowSense AI: 30-Day Step-by-Step Learning & Coding Plan

Welcome! This plan is designed for two freshers (Nishita and Aditi) to build **FlowSense AI**. Don't worry about the big words—we will explain everything as we go.

---

## 🛠️ Simple Glossary (The "What is this?" Section)
- **Agent:** A "virtual person" in our computer simulation.
- **Mesa:** A tool we use to create and move thousands of these virtual people.
- **Analytics:** The part of the code that counts things (like how crowded a corner is).
- **LLM/AI Brain:** A smart computer program (like ChatGPT) that helps make decisions.
- **Backend (FastAPI):** The hidden engine that makes the app work.
- **Frontend/Dashboard:** The screen you see with charts and maps.

---

## 📅 Roadmap: From Zero to FlowSense

### **Week 1: Foundations & Virtual People**
*Goal: Get your computer ready and see virtual people move on a screen.*

| Day | Nishita's Tasks | Aditi's Tasks |
| :--- | :--- | :--- |
| **1-2** | **Research:** Read about how crowds behave during stampedes. Find 5 real-life examples and write down what went wrong. | **Setup:** Install Python and VS Code. Try making a "Hello World" program in a tool called Mesa. |
| **3** | **Planning:** Draw a simple map of a stadium on paper. Decide where the "EXIT" signs and "STAGE" should be. | **Coding:** Write the code that tells a virtual person, "Go from the Stage to the Exit." |
| **4** | **Rules:** Decide how fast people walk and what happens when they bump into each other (simple rules). | **Coding:** Make 100 virtual people appear on a screen and start moving toward the exit. |
| **5-7** | **Physics:** Add a "Panic" rule: if it gets too crowded, virtual people start moving faster or clumsily. | **Logic:** Add "Obstacles" like walls and fences so people have to walk *around* them. |

---

### **Week 2: The "Smart" Counter (Analytics)**
*Goal: Teach the computer to spot when it's getting too crowded.*

| Day | Nishita's Tasks | Aditi's Tasks |
| :--- | :--- | :--- |
| **8-10** | **The Danger Score:** Create a math formula: "If more than 4 people are in one small box, mark it as RED (Danger)." | **Data Pipeline:** Write code that saves the location of every person every second so we can study it later. |
| **11-12** | **Thresholds:** Decide when to send a warning. (Example: 2 people = Safe, 5 people = Warning, 10 people = Emergency). | **Counters:** Create a "Counter" that shows how many people are entering vs. exiting every minute. |
| **13-14** | **Testing:** Run the simulation and see if your "Danger Score" actually turns red when people get stuck. | **Speed Study:** Write code to measure how the average speed drops as more people enter the room. |

---

### **Week 3: The AI Brain (LangGraph)**
*Goal: Use an AI assistant to give advice on how to save people.*

| Day | Nishita's Tasks | Aditi's Tasks |
| :--- | :--- | :--- |
| **15-16** | **The Playbook:** Write down "What should the AI do?" (Example: "If Gate A is stuck, tell people to use Gate B"). | **AI Setup:** Connect your code to an "AI Brain" (like GPT) using a tool called OpenRouter. |
| **17-18** | **Teaching the AI:** Give the AI the "Danger Scores" and ask it: "What is happening right now?" | **AI Flow:** Use a tool called LangGraph to help the AI think in steps (e.g., Step 1: Detect, Step 2: Analyze, Step 3: Advice). |
| **19-21** | **Explanations:** Tweak the AI so it speaks like a professional safety officer: "Urgent! Gate 4 is crowded. Open Gate 5 now." | **Intervention:** Write code that allows the AI to actually open virtual gates in your simulation. |

---

### **Week 4: The Dashboard & Final Show**
*Goal: Build the screen that shows the map and the AI's advice.*

| Day | Nishita's Tasks | Aditi's Tasks |
| :--- | :--- | :--- |
| **22-24** | **Design:** Build the website screen where the map will show up. Make the "Danger Score" big and red. | **The Bridge:** Write the code that sends data from the simulation to the website in real-time. |
| **25-27** | **Integration:** Connect the AI's "Advice" to a chat box on the website. | **Polishing:** Fix any bugs where the simulation crashes or the screen becomes slow. |
| **28-29** | **The "Final Test":** Simulate a disaster (like a fire) and see if the AI successfully guides people to safety. | **Documentation:** Write a simple "How to Run This" guide. Record a 2-minute video of the app working. |
| **30** | **Submission:** Finalize the project and prepare to share it on LinkedIn/GitHub! | **Review:** Double-check all code and celebrate! |

---

## 💡 Pro-Tips for Freshers
1. **Don't Panic:** If code breaks, it's normal. That's how you learn!
2. **Search YouTube:** Topics like "Mesa Python Tutorial" or "FastAPI for Beginners" will be your best friends.
3. **Daily Sync:** Talk to your friend for 15 minutes every morning to see what you both plan to do.
4. **Build Small:** First make one person walk. Then make 10. Then make it smart. Don't try to do everything at once!

Good luck, Team! You've got this. 🚀
