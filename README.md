<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="Pratham Ahuja: Backend Engineer, Java and Spring Boot" />
</p>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=19&duration=3200&pause=900&color=00D4FF&center=true&vCenter=true&width=760&lines=I+build+backends+that+fail+safely.;Queues+%C2%B7+retries+%C2%B7+locking+%C2%B7+auth;LLMs+inside+pipelines%2C+humans+in+the+loop.;Open+to+SDE+Intern+%2F+New-Grad+roles+(2027)" alt="Typing intro" />
</p>

<p align="center">
  <a href="https://linkedin.com/in/pratham--ahuja"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="https://leetcode.com/u/pratham_2005"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black" alt="LeetCode" /></a>
  <a href="mailto:ahujapa05@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://drive.google.com/file/d/1F6XRxr1pjyzFDXr8BLmCaJgKugaeysUh/view?usp=sharing"><img src="https://img.shields.io/badge/Resume-00D4FF?style=for-the-badge&logo=googledrive&logoColor=black" alt="Resume" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/LeetCode-500%2B_problems-FFA116?style=flat-square&logo=leetcode&logoColor=white" alt="500+ problems" />
  <img src="https://img.shields.io/badge/GSSoC-Contributor-ff6b35?style=flat-square&logo=github&logoColor=white" alt="GSSoC contributor" />
  <img src="https://img.shields.io/badge/The_Big_Hack_2025-Top_30-8a2be2?style=flat-square" alt="Big Hack 2025 Top 30" />
  <img src="https://img.shields.io/badge/NIE_Mysuru-ISE_'27-00ff88?style=flat-square" alt="NIE Mysuru ISE 2027" />
</p>

---

### `$ whoami`

```java
var pratham = Engineer.builder()
    .education("B.E. Information Science & Engineering @ NIE Mysuru, 2023–2027")
    .core("Java", "Spring Boot", "PostgreSQL", "Redis")
    .alsoUses("Python", "FastAPI", "pgvector", "Docker", "React")
    .enjoys("queues, retries, locking, auth, and what happens when a dependency goes down")
    .lately("putting LLMs inside backend pipelines, with a person approving the output")
    .lookingFor("SDE Intern / New-Grad (June 2027)")
    .locations("Bangalore", "Hyderabad", "Pune", "Mumbai", "Delhi", "Remote")
    .build();
```

```diff
+ Now      : hardening IncidentSense (timeouts, idempotent worker, service-to-service auth)
+ Learning : system design at scale, Python/AI engineering
- Not doing: putting numbers on my resume that I can't defend in an interview
```

---

### 🛠️ Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=java,spring,python,fastapi,cpp,js,react,postgres,redis,docker,githubactions,nginx,linux,azure,git&perline=8" alt="Tech stack icons" />
</p>

| | |
| :--- | :--- |
| **Backend** | Spring Boot · Spring Security (JWT, RBAC) · Spring Data JPA · FastAPI · REST |
| **Data** | PostgreSQL · pgvector · Redis (queues, atomic list ops) |
| **AI** | Sentence-Transformers embeddings · vector search · LLM APIs (Groq) · RAG |
| **Infra** | Docker Compose · GitHub Actions CI/CD · nginx · Linux · Azure VM |
| **Testing** | JUnit · Mockito · JaCoCo |

---

### 🚀 Featured work

<table>
<tr>
<td colspan="2">

#### 🚨 [IncidentSense](https://github.com/pratham-ahuja05/incident-triage-system) — AI-assisted incident triage
[**Live**](https://incidentsense.duckdns.org) · [**Demo video**](https://drive.google.com/file/d/1EMiDwaJuj5V-1NAqe7BLdrIytrRXUkSZ/view?usp=drive_link)

Matches a new production alert to past resolved incidents and suggests the fix that worked last time, or escalates when the problem looks new. **A person always approves.**

```mermaid
flowchart LR
    A([Alert]) -->|POST · 202 Accepted| B[Spring Boot API]
    B -->|LPUSH| Q[(Redis queue)]
    Q -->|BRPOP| W[Worker · retries 2/4/8s]
    W -->|/triage| AI[FastAPI AI service]
    AI -->|cosine search| V[(pgvector)]
    AI -->|verify match| L{{Groq LLM}}
    AI -->|fix or escalate| W
    W -->|SSE| D[React dashboard]
    D -->|approve · resolve| K[(Knowledge base)]
    K -.->|next similar alert| V
```

- **Async pipeline:** the API answers `202 Accepted` and a Redis-queue worker does the slow AI work, with exponential-backoff retries. Dashboards update live over SSE.
- **Retrieval + verification:** `all-MiniLM-L6-v2` embeddings and pgvector cosine search, then a distance threshold plus an LLM check decide between suggesting the past fix and escalating to Slack.
- **Learns from people:** approved fixes and human resolutions go back into the knowledge base. LLM classification sets P1–P4 priority and SLA due dates.
- **Platform:** JWT auth with four roles, Jira-style workflow with an audit log, Docker Compose on an Azure VM shipped by GitHub Actions.

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/pgvector-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

<sub>The knowledge base is seeded with synthetic incidents for now, so no accuracy numbers are claimed.</sub>

</td>
</tr>
<tr>
<td width="50%" valign="top">

#### 🔄 [Distributed Job Queue](https://github.com/pratham-ahuja05/distributed-job-queue)
Fault-tolerant background job processing with separate API and worker services.

- High / medium / low priority queues in Redis
- `rightPopAndLeftPush` hand-off + PostgreSQL `SELECT … FOR UPDATE` so two workers can't claim the same job
- Exponential backoff (2ⁿ), dead-letter queue, recovery scheduler for crashed workers
- Docker Compose · GitHub Actions CI · Mockito + JaCoCo

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

</td>
<td width="50%" valign="top">

#### 🧠 [AI-Assisted Issue Management](https://github.com/pratham-ahuja05/issue-management-system)
An issue tracker with AI features on top.

- Issue lifecycle, search and soft delete
- JWT auth with role-based access control (four roles)
- Semantic duplicate detection with embeddings in pgvector
- LLM features via Groq (Llama 3)

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![pgvector](https://img.shields.io/badge/pgvector-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)

</td>
</tr>
</table>

<details>
<summary><b>More projects</b></summary>
<br />

- **[EquiExchange](https://github.com/pratham-ahuja05/equi-exchange):** agent-based trade negotiation (FastAPI, Next.js) with agreed trades settled through Solidity smart contracts (Hardhat, Ethers.js).
- **MeshPay:** college project at NIE. A Spring Boot simulation of offline, UPI-style payments forwarded over a Bluetooth mesh (store-and-forward). Simulation only for now; no real Bluetooth or UPI integration yet.

</details>

---

### 🏆 Beyond code

| | |
| :--- | :--- |
| 🌱 **Open source** | Contributor, GirlScript Summer of Code (GSSoC) |
| ⚡ **Hackathon** | Top 30 at The Big Hack 2025 |
| 🤝 **Leadership** | Industrial Relations Lead, IUCEE NIE Student Chapter (2025–present) |
| 🎓 **Mentoring** | Technical Mentor, Shiksha Mentorship Program: 50+ students in backend and DSA |

<details>
<summary><b>📜 Certifications (Coursera, via NIE)</b></summary>
<br />

- Object Oriented Programming in Java (UC San Diego)
- Java Programming: Solving Problems with Software (Duke)
- Introduction to DevOps · Introduction to Cloud Computing · Encryption and Cryptography Essentials (IBM)
- Linux for Developers (Linux Foundation)

</details>

---

### 🐍 Contributions

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/pratham-ahuja05/pratham-ahuja05/output/github-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/pratham-ahuja05/pratham-ahuja05/output/github-snake.svg" />
    <img alt="Contribution snake animation" src="https://raw.githubusercontent.com/pratham-ahuja05/pratham-ahuja05/output/github-snake.svg" width="100%" />
  </picture>
</p>

<p align="center">
  <img src="./assets/footer.svg" width="100%" alt="Happy to talk backend, queues or AI pipelines" />
</p>
