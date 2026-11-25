<a id="top"></a>
<div align="center">

<!-- Animated typing header -->
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=22&duration=1500&pause=400&color=00FF88&center=true&vCenter=true&multiline=true&repeat=true&width=630&height=95&lines=Software+Engineer+%7C+Go+%C2%B7+Java;Digital+Asset+Manager+%C2%B7+Xsolla;API+%C2%B7+CDN+%C2%B7+Webhooks+%C2%B7+MCP+%C2%B7+CLI;Distributed+Locks+%2B+ACID+%3D+Zero+double-bookings;+" alt="Typing SVG" />

<br/>

<h1 align="center"><a href="#top"><img src="https://raw.githubusercontent.com/JayceWright/JayceWright/main/title.svg" alt="Jayce Wright" height="48" align="absmiddle" /> <img src="./comet_2604-fe0f.png" width="42" height="42" alt="comet" align="absmiddle" /></a></h1>

> *"When you understand how a system works — you start seeing structure in everything."*

<br/>

[![Telegram](https://raw.githubusercontent.com/JayceWright/JayceWright/main/telegram.svg)](https://t.me/JayceWright)
[![Portfolio](https://raw.githubusercontent.com/JayceWright/JayceWright/main/portfolio.svg)](https://jaycewright.github.io)
[![Email](https://raw.githubusercontent.com/JayceWright/JayceWright/main/email.svg)](mailto:prog061204@gmail.com)


</div>

---

## `$ whoami`

```yaml
name:       Jayce Wright
role:       Software Engineer
experience: Xsolla — Go (Sep–Nov 2026) · T-Bank — Java (Apr–Jun 2026)
stack:      Go · PostgreSQL · Google Cloud · Kubernetes · Java 21 · Spring Boot
focus:      APIs for humans and AI agents, MCP, fault-tolerant backends
languages:  Russian (native) · English (C1)
location:   Perm, Russia · open to Moscow, Yekaterinburg, remote
status:     Open to full-time roles
```

Building backends that keep working under load and are easy to integrate with.  
At Xsolla: built in Go a service that stores and delivers game assets, for people and AI agents alike.

---

## `$ cat work/xsolla.md`

### 🗂️ Digital Asset Manager `Xsolla · Go · Sep–Nov 2026`

A service that stores, processes and delivers game assets (images, 3D models, files) for Xsolla.

- **Uploads & processing** — resumable uploads to Google Cloud Storage, image and 3D model processing (libvips, glTF, Draco, KTX2), file versions and folders
- **CDN delivery** — Cloudflare Workers with signed, expiring and one-time download links
- **`damctl` CLI** — OAuth sign-in and the full asset workflow from the terminal
- **Remote MCP server** — AI agents (Claude, ChatGPT, Cursor) search, upload and manage assets through the [Model Context Protocol](https://modelcontextprotocol.io), with confirmations before destructive actions
- **OAuth 2.1 authorization server** for MCP clients — PKCE, dynamic client registration, refresh-token rotation, Okta sign-in
- **Account webhooks** — Standard Webhooks signatures, transactional outbox, retries, SSRF protection
- **LLM evals** — a test bench that measures how reliably different models pick the right tool, with cost tracking
- **Spec-first REST API** — OpenAPI as the source of truth, code generation, CI gates for contract drift, mutation testing on changed lines

### `$ open dam-architecture.svg`
<div align="center">
  <img src="./dam-arch.svg" alt="Digital Asset Manager — architecture" width="100%" />
</div>

**Stack:** `Go` `PostgreSQL` `OpenAPI` `MCP` `OAuth 2.1` `Google Cloud Storage` `Pub/Sub` `Cloudflare Workers` `TypeScript` `OpenTelemetry` `Kubernetes` `Helm` `GitLab CI` `SonarQube` `k6`

---

## `$ cat achievements.log`

🏆 **Kod Sporta — Winner** `T-Bank 2026`  
&nbsp;&nbsp;&nbsp;&nbsp;Team Competitive Programming Contest. Team of 3. Work under pressure, won under pressure.

🏦 **Backend Lead** `T-Bank × HSE Practicum 2026`  
&nbsp;&nbsp;&nbsp;&nbsp;Led a 5-person team for 10 weeks, built the CI/CD pipeline from scratch. Public defence before T-Bank and HSE jury.

---

## `$ cat projects.md`

<table>
<tr>
<td width="65%">

### 🎫 [T-Reserve Engine](https://github.com/TicketRace/T-RESERVE-ENGINE)
`T-Bank × HSE · Production · Backend Lead`

Seat booking for the moment sales open — concerts, cinemas, sports: few seats, thousands of fans hitting the same ones at once.
- **Redis SETNX** absorbs the rush — ~2 ms reject, 999 of 1000 requests for a taken seat never reach the database
- **PostgreSQL `SELECT FOR UPDATE NOWAIT`** guarantees the sale — one winner, zero double-bookings, even with Redis down
- **SafetyNet** frees expired holds every 30 s (partial index) · **graceful degradation** to PostgreSQL only
- **WebSocket STOMP** live seat map · **RabbitMQ** pipeline: PDF → MinIO → email
- **2 instances behind Nginx**, stateless JWT · CI: JUnit → Testcontainers → Playwright E2E → deploy

</td>
<td width="35%" align="center">

`k6 · 1000 VU on one seat`

| | PG only | Redis + PG |
|---|---|---|
| ⚡ Avg | 450–670ms | **250ms** |
| 📊 p95 | 780–1210ms | **465ms** |
| 🗄️ DB transactions | 300–500 | **1** |
| ❌ 5xx | cascading | **0** |

</td>
</tr>
</table>

**Stack:** `Java 21` `Spring Boot 3.3` `PostgreSQL 16` `Redis 7` `RabbitMQ` `MinIO` `Angular 17` `Docker` `Nginx` `Prometheus` `Grafana` `k6` `Testcontainers` `Playwright` `GitHub Actions`

### `$ open architecture.svg`
<div align="center">
  <img src="./arch.svg" alt="T-Reserve Engine — System Architecture" width="100%" />
</div>

---

## `$ cat stack.json`

```json
{
  "languages":   ["Go", "Java 21", "TypeScript", "JavaScript", "Python", "C#", "SQL", "Bash"],
  "frameworks":  ["oapi-codegen", "MCP Go SDK", "Spring Boot 3", "Spring Security", "Spring Data JPA",
                  "FastAPI", "Angular 17"],
  "databases":   ["PostgreSQL", "Redis", "Flyway", "Hibernate", "SQLAlchemy"],
  "messaging":   ["RabbitMQ", "Google Pub/Sub", "WebSocket STOMP", "Webhooks"],
  "cloud":       ["Google Cloud Storage", "Cloudflare Workers", "MinIO S3", "Kubernetes", "Helm"],
  "infra":       ["Docker", "GitLab CI", "GitHub Actions", "Maven", "Nginx", "Railway", "Linux"],
  "security":    ["OAuth 2.1 / PKCE", "Okta", "JWT", "BCrypt", "RBAC"],
  "monitoring":  ["OpenTelemetry", "Datadog", "Prometheus", "Grafana"],
  "testing":     ["Mutation testing", "LLM evals", "k6", "JMeter", "JUnit 5", "Mockito",
                  "Testcontainers", "Playwright", "SonarQube"],
  "ai":          ["MCP", "Claude Code", "Codex", "Cursor"],
  "patterns":    ["Spec-first API", "Transactional Outbox", "Distributed Locking", "Idempotency keys",
                  "State Machine", "Cache-Aside", "Circuit Breaker", "Graceful Degradation",
                  "Ports & Adapters"]
}
```

---

## `$ git log --stat`

<div align="center">

<a href="#stats"><img src="https://streak-stats.demolab.com/?user=JayceWright&v=2026112501&theme=dark&background=0d1117&border=00ff88&stroke=00ff88&ring=00ff88&fire=00ff88&currStreakNum=00ff88&sideNums=58a6ff&sideLabels=8b949e&dates=8b949e&hide_border=true" alt="GitHub Streak" width="95%" /></a>

<br/><br/>

<a href="#stats"><img src="https://github-readme-activity-graph.vercel.app/graph?username=JayceWright&bg_color=0d1117&color=00ff88&line=58a6ff&point=00ff88&area=true&hide_border=true" alt="Activity Graph" width="95%" /></a>

</div>

---

<div align="center">

```
[SYSTEM ONLINE] :: Backend that survives production. Architecture that scales.
```

**[jaycewright.github.io](https://jaycewright.github.io)** · Built by Jayce Wright · 2026

</div>
