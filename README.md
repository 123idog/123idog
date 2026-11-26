## Hi, I'm Ido 👋

**AI & Automation Engineer: I design and ship end-to-end AI solutions for sales and operations teams.**

I take a business process (lead intake, sales calls, customer conversations, reporting) and turn it into a production system: workflows, integrations, AI where it earns its place, and measurement that proves it works and what it costs.

My edge: systems that run in **Hebrew and Arabic** markets, where most AI tooling assumes English.

---

### What I build

- **Workflow automation**: 100+ production n8n workflows across CRM, messaging, marketing and operations, with monitoring, safety nets, deploy and test discipline
- **CRM automation and integrations**: lead intake and attribution, status rules, real-time alerts, safe bulk operations on Salesforce
- **AI in the process**: AI agents on WhatsApp and Messenger, call analysis and scoring, classification and extraction that write back into the systems of record
- **Measurement**: evaluation, cost per result and before/after studies, so every system has a number behind it
- **AI-assisted engineering**: Claude Code as my day-to-day engineering partner, with a memory system, custom skills and production guardrails

### Selected work

**🤖 WhatsApp sales agent: 3 in 4 inquiries handled end-to-end**
A Hebrew-speaking agent that qualifies inbound leads on WhatsApp, remembers customers across sessions, writes to the CRM and hands off to sales when a human is needed.
- **~75% of inquiries** closed with no human agent involved
- The bot was offline for 11 days, which gave a natural A/B test: first reply within 5 minutes **92% vs 30%**, after-hours messages left unanswered **under 1% vs 27%**
- Leads reaching a sales opportunity within 14 days: **48% vs 33%**

**📞 AI call analysis in Hebrew and Arabic**
Every sales call is transcribed, scored against a rubric written with the sales managers, and summarised into CRM fields the reps actually use.
- **~2,000 calls a month** at about **$0.11 per call**
- **500+ hours of audio** a month reviewed that nobody had time to listen to
- Separate Arabic rubric, refined over three rounds of feedback with the Arabic sales team
- High-scoring leads trigger a **real-time pop-up** for team leaders inside Salesforce

**⚙️ Lead intake and attribution across every channel**
Web forms, landing pages, Meta and Google ads, and click-to-WhatsApp feed one normalised flow into Salesforce.
- **~80% of ~3,000 monthly leads** created automatically, with clean phone numbers and campaign attribution
- Found that hidden form fields stamped the same stale campaign on every submission. Fixed going forward and corrected **~600 historical records**
- Automation across the stack saves an estimated **~300 hours a month (≈1.7 FTE)**, based on measured agent handling time

### Featured code

**💬 [whatsapp-agent-service](https://github.com/123idog/whatsapp-agent-service)**: a reference implementation of a production WhatsApp AI agent in Python, built around what breaks in real traffic rather than the happy path.

- **Idempotent webhooks:** a redelivered message gets the stored reply, with no second LLM call and no duplicate lead
- **Per-conversation locking** in Postgres, so a burst of messages is answered in order
- **Durable customer memory** that survives restarts. CI restarts the container mid-conversation and checks
- **Hebrew/Arabic output guards:** wrong language, English leaks, placeholders, tool-name leaks. A failed reply gets one rewrite, then a safe fallback and a human handoff
- **Model retries** with backoff and `Retry-After`, a fallback model, and cost tracked per turn
- **Multi-turn scenario evals in CI**, and a manual job against a real model

`Python` · `FastAPI` · `PostgreSQL` · `Docker` · `GitHub Actions` · 61 tests on Python 3.11–3.13

### Open source

| Repo | What it does |
|---|---|
| 🛡️ [**hebrew-arabic-guards**](https://github.com/123idog/hebrew-arabic-guards) | Dependency-free guards that stop a chatbot from sending broken Hebrew or Arabic: English leaks, prompt leaks, mojibake, Arabic/Hebrew whole-word matching, name cleaning. Tested, CI on Node 18–22 |
| 🔍 [**n8n-workflow-linter**](https://github.com/123idog/n8n-workflow-linter) | Offline linter for n8n workflows: catches the bugs that don't throw errors (stray `=` expressions, capped Data Table reads, missing retries, broken node references, hard-coded secrets) before deploy |
| 📈 [**llm-eval-kit**](https://github.com/123idog/llm-eval-kit) | Regression testing for chatbots and LLM agents: multi-turn replay with the bot's own history, repeated runs, flaky-case detection, judge-noise measurement, case-by-case comparison, CI gate on regressions |
| 💰 [**llm-cost-report**](https://github.com/123idog/llm-cost-report) | What an LLM app really costs per conversation and per result, from Langfuse traces: uncached prompts, oversized models, failed calls, runaway conversations, and a CI gate on cost per result |

### Writing

| Repo | What's inside |
|---|---|
| 📘 [**n8n Production Playbook**](https://github.com/123idog/n8n-production-playbook) | Lessons from running 100+ live workflows: silent failures, memory blowups, race conditions, API behaviour the docs don't mention |
| 🤖 [**Claude Code for Automation Engineers**](https://github.com/123idog/claude-code-for-automation-engineers) | How I run a production stack with Claude Code: operating model, CLAUDE.md, memory, skills and guardrails |
| 💬 [**WhatsApp AI Agent Design**](https://github.com/123idog/whatsapp-ai-agent-design) | Designing and operating production WhatsApp sales agents: methodology first, output guards, human handoff, CRM state, safety nets |
| 📊 [**LLM Evaluation in Production**](https://github.com/123idog/llm-evaluation-in-production) | How to know whether an AI agent actually works: what to measure, measurement hygiene, replay, shadow mode, LLM-as-judge, observability, cost per result, choosing a model |
| 🌍 [**LLMs for Hebrew and Arabic in Production**](https://github.com/123idog/llm-for-hebrew-and-arabic) | What breaks when customer-facing AI speaks Hebrew or Arabic: encoding, language guards, dialect, names, classification, voice |
| 🧭 [**Bot Operations Portal**](https://github.com/123idog/bot-operations-portal) | Designing a portal where non-technical team leads run their AI agents: modules not bots, versioned config with approvals, a keyed runtime contract, permissions in the database |
| ☁️ [**AI and Automation on Salesforce**](https://github.com/123idog/sales-ai-salesforce) | Connecting AI agents to a live sales org: writes the org overwrites, attribution, push triggers, rep alerts, safe bulk updates |

### How I work

- **Proven, not claimed.** A change is done when a live end-to-end run proves it, not when a tool returns 200.
- **Every incident becomes a rule.** Lessons are written down once and applied automatically afterwards.
- **Real customers are never test subjects.** Fake identities, live systems, then clean up.

### Stack

`Python` · `FastAPI` · `PostgreSQL` · `n8n` · `Claude Code` · `MCP` · `Gemini` · `OpenAI` · `Salesforce` · `WhatsApp Business API` · `Langfuse` · `Node.js` · `REST APIs` · `Docker` · `GitHub Actions` · `WordPress`

### Languages

Hebrew · English · building AI for Arabic-speaking markets

---

📫 [LinkedIn](https://www.linkedin.com/in/ido-guy)
🌐 [AutoFlow](https://auto-flow.co.il): my automation consulting brand
