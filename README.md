<h1 align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=24&pause=1000&color=00D4FF&center=true&vCenter=true&width=640&lines=PRATHAM+AHUJA;Backend+Engineer+%C2%B7+Java+%26+Spring+Boot;Building+AI-assisted+backend+systems;Open+to+SDE+roles+%C2%B7+2027" alt="Typing SVG" />
</h1>

<p align="center">
  <a href="https://linkedin.com/in/pratham--ahuja">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://leetcode.com/u/pratham_2005">
    <img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black" />
  </a>
  <a href="mailto:ahujapa05@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://drive.google.com/file/d/1F6XRxr1pjyzFDXr8BLmCaJgKugaeysUh/view?usp=sharing">
    <img src="https://img.shields.io/badge/Resume-00D4FF?style=for-the-badge&logo=googledrive&logoColor=black" />
  </a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=pratham-ahuja05&label=Profile%20views&color=00ff88&style=flat-square" alt="Profile views" />
</p>

---

### 👋 About me

> **B.E. Information Science & Engineering** · The National Institute of Engineering, Mysuru · 2023–2027

I'm a backend engineer who works mostly in **Java and Spring Boot**, with **Python/FastAPI** for the AI parts. I like the unglamorous side of backend work: queues, retries, locking, auth, and what a system does when one of its dependencies goes down. Lately I've been putting LLMs *inside* backend pipelines, with a person approving what the model suggests.

- 🔭 **Building:** [IncidentSense](https://github.com/pratham-ahuja05/incident-triage-system), an AI-assisted incident triage system
- 🎯 **Looking for:** SDE internships and new-grad roles (June 2027), in Bangalore, Hyderabad, Mumbai, Pune, Delhi or remote
- 🧩 **Problem solving:** 500+ DSA problems, mostly in C++
- 📫 **Reach me:** ahujapa05@gmail.com

---

### 🛠️ Tech I work with

| Area | Tools |
| :--- | :--- |
| **Languages** | `Java` `Python` `C++` `JavaScript` `SQL` |
| **Backend** | `Spring Boot` `Spring Security (JWT, RBAC)` `Spring Data JPA` `FastAPI` `REST APIs` |
| **Data** | `PostgreSQL` `pgvector` `Redis (queues, atomic list ops)` |
| **AI** | `Sentence-Transformers embeddings` `Vector search` `LLM APIs (Groq)` `RAG` |
| **Infra & tooling** | `Docker` `Docker Compose` `GitHub Actions` `nginx` `Linux` `Azure VM` `Git` |
| **Testing** | `JUnit` `Mockito` `JaCoCo` |
| **Frontend** | `React` `Vite` |

<p align="center">
  <img src="https://skillicons.dev/icons?i=java,spring,python,fastapi,cpp,js,react,postgres,redis,docker,githubactions,nginx,linux,azure,git" />
</p>

---

### 🚀 Featured projects

#### 🚨 [IncidentSense](https://github.com/pratham-ahuja05/incident-triage-system) · AI-assisted incident triage
[Live](https://incidentsense.duckdns.org) · [Demo video](https://drive.google.com/file/d/1EMiDwaJuj5V-1NAqe7BLdrIytrRXUkSZ/view?usp=drive_link)

*Matches a new production alert to past resolved incidents and suggests the fix that worked last time, or escalates when the problem looks new. A person always approves the suggestion.*

* **Async pipeline:** a Spring Boot API accepts the alert, returns `202 Accepted`, and hands the work to a Redis-queue worker with exponential-backoff retries. Dashboards update live over Server-Sent Events.
* **Retrieval + verification:** a FastAPI service embeds the alert (`all-MiniLM-L6-v2`) and runs cosine search in pgvector. A distance threshold plus an LLM check (Groq) decides between suggesting the past fix and escalating to Slack.
* **Learns from people:** approved fixes and human-written resolutions go back into the knowledge base, so the next similar alert can match. LLM classification sets P1–P4 priority and SLA due dates.
* **Platform:** JWT auth with four roles, a Jira-style ticket workflow with a full audit log, and a Docker Compose stack deployed to an Azure VM through GitHub Actions.
* **Stack:** `Java` `Spring Boot` `FastAPI` `PostgreSQL + pgvector` `Redis` `Groq` `React` `Docker`

<sub>The knowledge base is currently seeded with synthetic incidents, so I don't claim any accuracy numbers yet.</sub>

#### 🔄 [Distributed Job Queue](https://github.com/pratham-ahuja05/distributed-job-queue) · Fault-tolerant background job processing
*Two services (API + worker) that run jobs reliably when workers crash or jobs fail.*

* **Priority queues:** high, medium and low priority queues in Redis.
* **Safe claiming:** `rightPopAndLeftPush` hand-off plus PostgreSQL row locking (`SELECT … FOR UPDATE`) so two workers can't claim the same job.
* **Failure handling:** exponential-backoff retries (2ⁿ), a dead-letter queue, and a recovery scheduler for jobs left behind by a crashed worker.
* **Engineering:** Docker Compose, GitHub Actions CI, Mockito tests with JaCoCo coverage.
* **Stack:** `Java` `Spring Boot` `Redis` `PostgreSQL` `Docker`

#### 🧠 [AI-Assisted Issue Management System](https://github.com/pratham-ahuja05/issue-management-system)
*An issue tracker with AI features on top.*

* **Core:** issue lifecycle, search and soft delete behind JWT auth with role-based access control (four roles).
* **AI:** semantic duplicate detection using embeddings stored in pgvector, with LLM features via Groq (Llama 3).
* **Stack:** `Java` `Spring Boot` `PostgreSQL` `pgvector` `React` `Groq`

<details>
<summary><b>More projects</b></summary>

* **[EquiExchange](https://github.com/pratham-ahuja05/equi-exchange):** agent-based trade negotiation (FastAPI, Next.js) with agreed trades settled through Solidity smart contracts (Hardhat, Ethers.js).
* **MeshPay:** college project at NIE. A Spring Boot simulation of offline, UPI-style payments forwarded over a Bluetooth mesh (store-and-forward). It is a simulation for now, with no real Bluetooth or UPI integration yet.

</details>

---

### 🏆 Open source, achievements & leadership

* **Open source:** contributor in GirlScript Summer of Code (GSSoC)
* **Hackathon:** Top 30 at The Big Hack 2025
* **Industrial Relations Lead** @ IUCEE NIE Student Chapter (2025–present)
* **Technical Mentor** @ Shiksha Mentorship Program, mentoring 50+ students in backend and DSA

<details>
<summary><b>Certifications (Coursera, via NIE)</b></summary>

* Object Oriented Programming in Java (UC San Diego)
* Java Programming: Solving Problems with Software (Duke)
* Introduction to DevOps · Introduction to Cloud Computing · Encryption and Cryptography Essentials (IBM)
* Linux for Developers (Linux Foundation)

</details>

---

### 📈 GitHub activity

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=pratham-ahuja05&theme=tokyo-night&hide_border=true&area=true" width="100%" alt="contribution graph" />
</p>

---

<h3 align="center">Thanks for stopping by. Happy to talk backend, queues, or AI pipelines.</h3>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=00D4FF&height=60&section=footer" width="100%" />
</p>
