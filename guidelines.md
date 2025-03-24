Here’s a **customized version of the Semantic Seed Venture Studio Coding Standards** tailored specifically for the **VibePlay** project — a high-velocity, behavior-first, no-chat matchmaking app with a strong focus on real-time interactivity, personalization, and viral loops.

---

# 🧠 *VibePlay Product Engineering Standards V1.0*
## *Introduction*
These standards guide the engineering team in building and maintaining VibePlay — a gamified, real-time social matching platform for Gen-Z users. Our principles focus on **rapid iteration, secure real-time interaction, behavioral data fidelity, test-first development, and product-led engineering**.

---

## 📋 *Backlog Management*
We manage our backlog using **Linear**, designed around tight feedback loops and weekly sprints.

### *LLM Prompts for Backlog Management*
*Prompt 1:*  
"Given a set of user stories for a social gaming app, describe the optimal agile workflow from design to deployment, including how real-time dependencies are handled."

*Prompt 2:*  
"Explain the importance of starting with WIP commits and how it supports test-driven development in fast-paced consumer apps."

*Prompt 3:*  
"Classify backlog items for a mobile game app into bugs, features, or experiments. Suggest how each type should be scheduled and tested."

### *Standard Workflow*
1. **Pick from prioritized sprint items**
2. **Branch Naming Convention**:  
   - `feature/{id}-title`  
   - `bug/{id}-title`  
   - `experiment/{id}-title`  
3. **TDD/BDD Process**:
   - Write failing test → implement code → pass test → refactor  
   - WIP commits after each milestone (Red / Green / Refactor)
4. **PR Workflow**:
   - Mark as *Ready*, submit PR  
   - All tests must pass (unit, integration)  
   - Code review with 1 peer  
   - PR merged → auto-deploy to staging  
   - QA or PM marks as *Done*  

---

## 📖 *Story Types & Estimation*

We use **point-based estimation** tied to value and complexity.

### *LLM Prompts for Estimation*
*Prompt 4:*  
"Given a VibePlay user story involving matchmaking logic, estimate its complexity using the Fibonacci scale and explain the edge cases to test."

*Prompt 5:*  
"Classify the following items as Feature, Bug, Chore, or Experiment, and outline the proper branching and testing requirements for each."

### *Estimation Rules*
| Points | Example |
|--------|---------|
| 0️⃣ | Typo fix, copy update |
| 1️⃣ | UI-only, no state change |
| 2️⃣ | Simple logic, small DB updates |
| 3️⃣ | Matchmaking rule update, leaderboard logic |
| 5️⃣ | New game mode or co-play activity |
| 8️⃣ | Co-play sync system or verdict engine refactor |

---

## 🎨 *Code Style & Structure*

We follow a **clean, modular architecture** and opinionated style guides per language.

### *LLM Prompts for Code Consistency*
*Prompt 6:*  
"Rewrite the following React Native component using hooks, camelCase props, and clean conditional rendering."

*Prompt 7:*  
"Refactor this game logic controller to separate concerns into utilities and reducers."

### *Style Guide Summary*
- **Naming**: camelCase (functions, props), PascalCase (components), snake_case (DB)  
- **Indentation**: 2 spaces (JS), 4 spaces (Python)  
- **Line Length**: Max 100 chars  
- **Comments**: Only for *why*, not *what*  
- **Modules**: Keep controllers <150 lines, break logic into `utils`, `services`, `hooks`  

---

## 🧪 *Testing Strategy (TDD/BDD)*

Every feature should have **automated test coverage**.

### *LLM Prompts for Testing*
*Prompt 8:*  
"Write Jest tests for a function that calculates compatibility based on emoji reaction and decision overlap in a co-play session."

*Prompt 9:*  
"Create an integration test to simulate two users joining a co-play session and receiving a Go/No-Go verdict."

### *Test Layers*
- **Unit Tests**: Pure logic and utilities (Jest, Mocha)
- **Integration Tests**: DB + API flows, persona generation
- **End-to-End**: Expo + Detox / Cypress for mobile flows
- **Shared Activity Simulators**: Stub user sessions to simulate multi-user sync

---

## 🔄 *CI/CD Pipeline*

### *LLM Prompts for CI/CD*
*Prompt 10:*  
"Describe a CI/CD pipeline for a real-time mobile app with feature flags and dynamic config."

*Prompt 11:*  
"Identify where to block a PR if co-play sync tests fail in staging."

### *Pipeline Steps*
1. **Pre-Commit**: Lint + unit tests  
2. **CI (PR)**:  
   - Run tests: unit + integration  
   - Build APK / IPA  
   - Deploy preview to Expo / staging  
3. **CD**:  
   - Auto-deploy to staging post-merge  
   - Manual promote to production (tagged release)  
4. **Monitoring**: Sentry for errors, Mixpanel for events

---

## 🔧 *Version Control*

We maintain **tight commit hygiene** and traceability.

### *LLM Prompts for Git Hygiene*
*Prompt 12:*  
"Rewrite these Git commits into a clear, single-sentence PR summary."

*Prompt 13:*  
"Explain why end-of-day commits and WIP checkpoints reduce onboarding friction."

### *Git Rules*
- **Daily commits mandatory**
- **WIP commit** after red and green test phases
- **Commit Messages**:
  - `feat: added verdict engine`
  - `fix: patch sync bug in session controller`
  - `chore: lint config update`

---

## 📊 *Data Tracking & Analytics*

We track **real-time product signals** to inform iteration.

### *LLM Prompt for Analytics Design*
*Prompt 14:*  
"Given a co-play activity flow, define 5 essential Mixpanel events to track success and dropout points."

### *Key Events to Track*
- Activity start / complete  
- Match trigger  
- Verdict received  
- Match card shared  
- Re-engage (“play again”) action  
- School-level leaderboard unlocks  

---

## 📌 *Conclusion*

VibePlay is engineered for **fast feedback**, **experiential learning**, and **emotional resonance**. These coding standards ensure we scale this product with consistency, speed, and integrity — powered by structured prompts, test-first thinking, and continuous feedback.

---

Would you like this delivered as a **Notion doc**, a **GitHub README.md**, or **embedded into your codebase as a `CONTRIBUTING.md` file** next?
