<div align="center">

# Mai Huy Hoang

### Software Engineer · Java Backend · Platform/DevOps · Observability/APM

**I ship backend systems, then operate them — deployments, migrations, incidents, and the traces that explain them.**

<p>
  <a href="https://github.com/MaiHuyHoang592004/corebank-api">
    <img src="https://img.shields.io/badge/CoreBank-Platform%20%26%20APM%20lab-181717?style=for-the-badge&logo=github&logoColor=white" alt="CoreBank repository" />
  </a>
  <a href="https://corebank-api-acv7.onrender.com">
    <img src="https://img.shields.io/badge/Live%20demo-online-0F9D58?style=for-the-badge&logo=render&logoColor=white" alt="CoreBank live demo" />
  </a>
  <a href="https://github.com/MaiHuyHoang592004/Car-Rental">
    <img src="https://img.shields.io/badge/RentFlow-Booking%20platform-181717?style=for-the-badge&logo=github&logoColor=white" alt="RentFlow repository" />
  </a>
</p>

<p>
  <img src="https://img.shields.io/badge/Hanoi,%20Vietnam-informational?style=flat-square&logo=googlemaps&logoColor=white" alt="Hanoi, Vietnam" />
  <img src="https://img.shields.io/badge/Open%20to-Platform%20%C2%B7%20APM%20%C2%B7%20Java%20Backend-success?style=flat-square" alt="Open to platform, APM and Java backend roles" />
  <img src="https://img.shields.io/badge/Domain-Banking%20%26%20Financial%20Services-blueviolet?style=flat-square" alt="Banking and financial services" />
</p>

`Java 17` · `Spring Boot` · `PostgreSQL` · `Kubernetes` · `OpenShift` · `Istio` · `OpenTelemetry` · `Dynatrace` · `Kafka` · `Cloudflare Workers/D1`

</div>

---

## In one paragraph

Software engineer with hands-on **production operations** experience on two internal systems: I took over an outsourced fulfillment platform and adapted it for multi-workshop operations, and I built a **financial reconciliation platform** together with the accounting team. I own releases, database migrations and runtime troubleshooting across managed hosting and **Cloudflare Workers + D1**. On top of that, I have **runtime-verified Kubernetes / OpenShift and Dynatrace / OpenTelemetry** work with evidence in the repository 

---

## Experience

### Software Engineer — OP Creative · Fulfillment & Print-on-Demand
`05/2026 – 09/2026` · Hanoi, Vietnam

- **Production operations / DevOps** — day-to-day deployments and runtime support for two internal systems: the fulfillment platform on managed hosting and the reconciliation platform on **Cloudflare Workers + D1**. Releases, database migrations, production troubleshooting.
- **Fulfillment Operations Platform** — took over a system built by an outsourced team: maintained the codebase, customized workflows and shipped features for production processes across multiple workshops; supported automated artwork-processing and print-dispatch runners.
- **Payment & Reconciliation Hub** — built together with accounting: consolidated transaction data from multiple financial and commerce sources and attributed incoming funds to the correct customer/seller accounts.
- **Reconciliation correctness** — verification and exception-handling workflows for **ambiguous, duplicate and pending-to-posted** payments; investigated excessive **Cloudflare D1 row reads** and other production issues affecting financial operations.

### Java Backend Intern — FPT Software Academy
`04/2025 – 08/2025`

- Mentor-reviewed Java / Spring Boot training: OOP, SQL, REST APIs, Git, unit testing, relational database design.
- Built backend features in team projects, designed REST endpoints and database schemas, took part in code reviews.

---

## Verified platform & APM work

> Everything below was executed against a live cluster and captured in the [CoreBank repository](https://github.com/MaiHuyHoang592004/corebank-api) — not read about.

```text
Same banking workload, two platforms — Kind and Red Hat OpenShift Developer Sandbox
  ├─ OpenShift · restricted-v2, platform-assigned UID, no anyuid / SCC bypass
  ├─ Self-healing · DB readiness & liveness behavior · HPA · rolling update · rollback
  ├─ OpenTelemetry Collector → Dynatrace · HTTP/JDBC traces · Hikari & banking metrics
  └─ Istio 1.31 (upstream, on Kind) · canary routing · STRICT mTLS · rollback
```

| Evidence | What it demonstrates |
|---|---|
| **3,899 committed journals = 3,899 HTTP server spans = 3,899 posted-journal metric increments** (on OpenShift) | Telemetry reconciles exactly with the ledger — traces and metrics can be trusted as financial evidence |
| **45 s PostgreSQL row-lock incident, induced and root-caused** | Correlated Dynatrace traces, JDBC acquisition events, Hikari metrics and PostgreSQL wait evidence to separate **lock contention** from **pool wait** and **slow SQL** |
| **PostgreSQL connection exhaustion at HPA scale-out** | A runtime-only defect invisible in unit tests; fixed and locked down with a **CI connection-budget guard** |
| **Operations runbook · proposed SLOs · end-to-end platform/APM POC document** | Operable by someone other than the author |

**Next:** Dynatrace Operator (DynaKube) · OpenShift Service Mesh · NetworkPolicy

---

## Selected engineering work

<table>
<tr>
<td width="50%" valign="top">

### 🏦 CoreBank
**Banking reliability & platform engineering lab.**

A core-banking workload built to be *operated*: PostgreSQL is the source of truth for money, and every platform claim is verified at runtime.

**Banking domain**
- Double-entry ledger
- Hold / capture / void lifecycle
- Idempotent money commands
- Concurrency-safe transfers
- Transactional outbox
- Reconciliation & break detection

**Platform & observability**
- OpenShift under `restricted-v2`
- HPA · rolling update · rollback
- OpenTelemetry → Dynatrace
- Incident RCA with trace evidence

**Stack**

`Java 17` `Spring Boot` `PostgreSQL` `Kafka` `Kubernetes` `OpenShift` `Istio` `OpenTelemetry` `Dynatrace`

<p>
  <a href="https://github.com/MaiHuyHoang592004/corebank-api"><strong>Repository →</strong></a>
  &nbsp;·&nbsp;
  <a href="https://corebank-api-acv7.onrender.com"><strong>Live demo →</strong></a>
</p>

</td>
<td width="50%" valign="top">

### 🚗 RentFlow
**A car-rental booking platform designed around booking correctness.**

Availability, booking, payment and trip workflows treated as stateful business processes rather than CRUD screens.

**Engineering focus**
- Double-booking prevention
- Pessimistic availability locking
- Idempotent booking creation
- JWT / RBAC + refresh-token rotation
- Rate limiting
- Transactional outbox
- Actuator / Prometheus metrics
- PostgreSQL integration testing

**Stack**

`Java 17` `Spring Boot` `PostgreSQL` `Redis` `Next.js` `Testcontainers`

<p>
  <a href="https://github.com/MaiHuyHoang592004/Car-Rental"><strong>Repository →</strong></a>
</p>

</td>
</tr>
</table>

---

## How I think about systems

| | Principle | What it means in practice |
|---|---|---|
| 💰 | **Correctness before convenience** | Money and transactional state live in an authoritative store, not in caches or message queues. |
| 🔁 | **Retries are part of the API** | Idempotency and recovery behavior are designed before a failure reaches production. |
| 📈 | **A claim isn't real until it runs** | Self-healing, HPA and rollback are verified on a live cluster, with the evidence committed. |
| 🔎 | **Observe the failure, not only the uptime** | Metrics, traces, logs and runbooks should explain *why* a system degraded. |
| 🧩 | **Architecture follows pressure** | I prefer the smallest architecture that preserves the required guarantees. |

---

## Toolbox

<div align="center">

**Platform & Operations**

<img src="https://skillicons.dev/icons?i=kubernetes,docker,linux,githubactions,git,cloudflare" alt="Platform and operations stack" />
<br />
<img src="https://img.shields.io/badge/OpenShift-EE0000?style=flat-square&logo=redhatopenshift&logoColor=white" alt="OpenShift" />
<img src="https://img.shields.io/badge/Istio-466BB0?style=flat-square&logo=istio&logoColor=white" alt="Istio" />
<img src="https://img.shields.io/badge/Kustomize-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kustomize" />
<img src="https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aquasecurity&logoColor=white" alt="Trivy" />
<img src="https://img.shields.io/badge/Cloudflare%20Workers%20%2F%20D1-F38020?style=flat-square&logo=cloudflare&logoColor=white" alt="Cloudflare Workers and D1" />

**Observability / APM**

<img src="https://img.shields.io/badge/Dynatrace-1496FF?style=flat-square&logo=dynatrace&logoColor=white" alt="Dynatrace" />
<img src="https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white" alt="OpenTelemetry" />
<img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" alt="Prometheus" />
<img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" alt="Grafana" />
<img src="https://img.shields.io/badge/Tempo-F46800?style=flat-square&logo=grafana&logoColor=white" alt="Tempo" />
<img src="https://img.shields.io/badge/Micrometer-117AC9?style=flat-square" alt="Micrometer" />

**Backend & Data**

<img src="https://skillicons.dev/icons?i=java,spring,postgres,mysql,redis,ts,nextjs" alt="Backend and data stack" />
<br />
<img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" alt="Kafka" />
<img src="https://img.shields.io/badge/Flyway-CC0200?style=flat-square&logo=flyway&logoColor=white" alt="Flyway" />
<img src="https://img.shields.io/badge/Testcontainers-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Testcontainers" />

</div>

---

## What I'm optimizing for

Not the largest number of frameworks — the ability to follow **one production problem all the way through**:

```text
business symptom
      ↓
API / application behavior
      ↓
transaction & database
      ↓
container / platform
      ↓
metrics · traces · logs
      ↓
root cause
      ↓
safe recovery
```

---


<div align="center">

### Build the system. Break the assumptions. Understand the failure.

**Open to Platform/DevOps, Observability/APM and Java Backend roles — Hanoi or remote.**

<a href="mailto:huyhoang59204@gmail.com">
  <img src="https://img.shields.io/badge/Email-huyhoang59204%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
</a>

<sub>Hanoi, Vietnam · Banking & financial-services platform and APM work welcome.</sub>

</div>
