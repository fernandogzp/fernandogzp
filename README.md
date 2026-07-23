<div align="center">

<img src="assets/hero.gif" alt="Fernando Gutiérrez Pardo — AI Systems Engineer · agent infrastructure, retrieval, LLM ops" width="100%">

<sub><b>AI Systems Engineer</b> · Agentic AI &amp; LLM infrastructure · RAG &amp; retrieval · model routing · evals &nbsp;—&nbsp; Chemical Engineer, Universidad de Concepción</sub>

</div>

<br>

## Everything drifts. I build agent systems that hold setpoint.

I studied chemical engineering before I ever shipped production software. Nobody says *"it worked in the demo"* about a reactor — it's at temperature or it isn't, and something is always drifting. I run agent infrastructure on that reflex: instrument everything, alarm only what matters, and treat "up" as a measurement, not a mood. The interesting problems start *after* the prototype works.

Today that means operating a production multi-agent platform **solo** — memory and retrieval, LLM orchestration, model routing across frontier APIs and local GPU inference, context engineering, MCP integrations — inside a security perimeter I also built and run. The industry word is agentic AI; the daily work is evals, observability, and security engineering. When it breaks, there's no escalation path. There's me.

### <img src="https://img.shields.io/badge/-C0392B?style=flat-square" height="13"> &nbsp;Field notes from production

- **Memory is a fusion problem, not a search problem.** One vector store will hand you the wrong thing with total confidence; five disagreeing sources, ranked, rarely do.
- **The hard part of autonomy is the escape hatch, not the happy path.** An agent that can't hand a decision back to a human will either stall or guess — and both cost more than asking.
- **The easiest metric to read is usually the one that's lying.** I once watched a dashboard report *"0 blocked"* while the edge quietly ate 400 requests. Model the truth from raw events, not the convenient rollup.
- **An alert you can ignore is already broken.** Most of reliability is *deleting* pages, not adding them.
- **Recovery is a skill** (ask me about the 432k-vector recovery). Not needing it twice is the job.

<details>
<summary>&nbsp;<i>the one war story I'll tell unprompted</i></summary>
<br>

A cleanup job deleted the store backing a live vector index — 432,000 embeddings, no recent-enough backup. But the serving process still had the file open, so the kernel hadn't freed the bytes — they were still reachable through `/proc/<pid>/fd`. I froze writes, streamed the deleted file back out through the process's own file descriptor, checked integrity, and re-pointed the service. Zero vectors lost; nothing downstream noticed. Then I built the offsite backups and the guardrail so it can't matter again. That second part is the actual job.

</details>

### <img src="https://img.shields.io/badge/-C0392B?style=flat-square" height="13"> &nbsp;Open problems on the bench

Vector search that stays fast after the corpus outgrows RAM &nbsp;·&nbsp; cheap local models and frontier inference in one loop without the seams showing &nbsp;·&nbsp; memory for long-running agents that doesn't quietly rot &nbsp;·&nbsp; the unglamorous LLMOps layer that turns an agent *demo* into an agent *system*.

### <img src="https://img.shields.io/badge/-C0392B?style=flat-square" height="13"> &nbsp;One vector, no pivots

Six years studying chemical engineering — *Ingeniero Civil Químico*, Universidad de Concepción — with a thesis inside a **CODELCO** copper smelter: the formation mechanism of As₂O₃ / Sb₂O₃ accretions in an electrostatic precipitator, thermodynamic modeling against real plant data, XRD / SEM-EDS characterization. **Springer** published it ([*12th International Copper Conference*, 2025](https://doi.org/10.1007/978-3-032-00102-3_224)). That's where the instincts were installed: mass-and-energy balances, transport, process control, failure modes.

Then software, then the platform — and because Reflejo is a registered **security firm**, security engineering isn't a layer that got added later; it's the practice, both sides of it. **Defense:** a self-hosted **Wazuh SIEM** I actually read, a **zero-trust** mesh between every service, ATT&CK-mapped **detection engineering**, OSINT when a question needs it. **Offense, in a private lab network I run:** red-team and **vulnerability-assessment** exercises, red-team tooling I built, SAST pipelines in CI, CTFs on Fluid Attacks to stay honest, **OSCP in progress**. The part I care about most sits where my two identities meet — **AI red teaming and LLM security**: adversarial testing of LLMs, prompt-injection and jailbreak/refusal evals, capability elicitation, and safety guardrails for the agents I ship. **Purple team** as an operating posture, not an annual audit.

The newest work is where the whole line was pointing: **reflejo-cfd** — GPU reacting-flow CFD with **physics-informed neural networks**. Reacting flows, thermodynamics, transport: the physics I trained on, finally in the same loop as the ML I run. Same engineering — the reactor keeps changing.

### <img src="https://img.shields.io/badge/-C0392B?style=flat-square" height="13"> &nbsp;Stack

<sub><b>LANGUAGES</b></sub><br>
<img src="https://cdn.simpleicons.org/python" height="34" alt="Python">
<img src="https://cdn.simpleicons.org/typescript" height="34" alt="TypeScript">
<img src="https://cdn.simpleicons.org/gnubash" height="34" alt="Bash">
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/latex/white"><img src="https://cdn.simpleicons.org/latex" height="34" alt="LaTeX"></picture>

<sub><b>AI / LLM</b></sub><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/ollama/white"><img src="https://cdn.simpleicons.org/ollama" height="34" alt="Ollama"></picture>
<img src="https://cdn.simpleicons.org/huggingface" height="34" alt="Hugging Face">
<img src="https://cdn.simpleicons.org/pytorch" height="34" alt="PyTorch">
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/anthropic/white"><img src="https://cdn.simpleicons.org/anthropic" height="34" alt="Anthropic"></picture>

<sub><b>BACKEND &amp; WEB</b></sub><br>
<img src="https://cdn.simpleicons.org/fastapi" height="34" alt="FastAPI">
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/django/white"><img src="https://cdn.simpleicons.org/django" height="34" alt="Django"></picture>
<img src="https://cdn.simpleicons.org/nodedotjs" height="34" alt="Node.js">
<img src="https://cdn.simpleicons.org/react" height="34" alt="React">
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/nextdotjs/white"><img src="https://cdn.simpleicons.org/nextdotjs" height="34" alt="Next.js"></picture>

<sub><b>DATA</b></sub><br>
<img src="https://cdn.simpleicons.org/postgresql" height="34" alt="PostgreSQL">
<img src="https://cdn.simpleicons.org/redis" height="34" alt="Redis">
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/sqlite/white"><img src="https://cdn.simpleicons.org/sqlite" height="34" alt="SQLite"></picture>

<sub><b>INFRA &amp; OPS</b></sub><br>
<img src="https://cdn.simpleicons.org/docker" height="34" alt="Docker">
<img src="https://cdn.simpleicons.org/linux" height="34" alt="Linux">
<img src="https://cdn.simpleicons.org/nginx" height="34" alt="Nginx">
<img src="https://cdn.simpleicons.org/githubactions" height="34" alt="GitHub Actions">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/oracle/oracle-original.svg" height="30" alt="Oracle Cloud">
<img src="https://cdn.simpleicons.org/netdata" height="34" alt="Netdata">
<img src="https://cdn.simpleicons.org/git" height="34" alt="Git">

<sub><b>NETWORK &amp; SECURITY</b></sub><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/tailscale/white"><img src="https://cdn.simpleicons.org/tailscale" height="34" alt="Tailscale"></picture>
<img src="https://cdn.simpleicons.org/cloudflare" height="34" alt="Cloudflare">
<img src="https://cdn.simpleicons.org/wireshark" height="34" alt="Wireshark">

<details>
<summary><sub><b>+ concepts &amp; methods</b> &nbsp;·&nbsp; the toolkit in words</sub></summary>
<br>
<sub>
<b>AI / LLM</b> &nbsp;— agentic AI · multi-agent systems · LLM orchestration · RAG &amp; hybrid retrieval · vector search · semantic search · reranking · embeddings · evals &amp; guardrails · model routing · LLM inference · GPU inference · context engineering · MCP · LLMOps · fine-tuning (QLoRA) · harness engineering · prompt engineering · llama.cpp<br>
<b>AI security</b> &nbsp;— AI red teaming · LLM security · prompt injection · adversarial ML · jailbreak &amp; refusal evals · capability elicitation · AI safety evals · model safety evaluation<br>
<b>Offensive</b> &nbsp;— red team · offensive security · offensive cybersecurity · ethical hacking · penetration testing · nmap · adversary emulation · vulnerability research · fuzzing · exploit development · private lab network · vulnerability assessment · SAST-in-CI · OSCP (in progress)<br>
<b>Defensive · blue / purple team</b> &nbsp;— Wazuh SIEM · blue team · purple team · threat intelligence · MITRE ATT&amp;CK · detection engineering · incident response · DevSecOps · IoC analysis · SOC operations · OSINT · zero-trust · cloud / app / network security<br>
<b>Chemical engineering &amp; physics</b> &nbsp;— thermodynamics · process control · transport phenomena · CFD · physics-informed neural networks (PINN)
</sub>
</details>

<br>

> **Most of what I build is private** — it ships to production, not to GitHub, so my green squares run ahead of my public repos. If any of this is your kind of problem, ask me for the walkthrough. It's better than the README.

<br>

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/fernandogzp/fernandogzp/output/github-snake-dark.svg">
  <img alt="Contribution graph (includes private commits), animated nightly" src="https://raw.githubusercontent.com/fernandogzp/fernandogzp/output/github-snake.svg" width="100%">
</picture>

<br>

<a href="https://linkedin.com/in/fernandogzp"><img src="https://img.shields.io/badge/LinkedIn-in%2Ffernandogzp-C0392B?style=flat-square&labelColor=0b0b0f" alt="LinkedIn"></a>
&nbsp;
<a href="https://reflejo.ai"><img src="https://img.shields.io/badge/Web-reflejo.ai-C0392B?style=flat-square&labelColor=0b0b0f" alt="reflejo.ai"></a>

<sub>Chemical engineer → AI systems · Concepción, Chile · building <a href="https://reflejo.ai">Reflejo AI</a></sub>

</div>

<br>

<details>
<summary><sub><code>// colophon</code></sub></summary>

<sub>Written by AI, supervised by ego. I wrote the AI — it's named **Reflejo**, and a reflection is only as good as what it's pointed at.</sub>

</details>
