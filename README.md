<div align="center">

# Mai Huy Hoang

### Software Engineer · Java Backend · Platform/DevOps · Observability/APM

**I build transactional systems where correctness, concurrency, and failure behavior matter.**

<p>
  <a href="https://github.com/MaiHuyHoang592004/corebank-api">
    <img src="https://img.shields.io/badge/CoreBank-181717?style=for-the-badge&logo=github&logoColor=white" alt="CoreBank" />
  </a>
  <a href="https://corebank-api-acv7.onrender.com">
    <img src="https://img.shields.io/badge/Live%20Demo-0F9D58?style=for-the-badge&logo=render&logoColor=white" alt="CoreBank live demo" />
  </a>
  <a href="https://github.com/MaiHuyHoang592004/Car-Rental">
    <img src="https://img.shields.io/badge/RentFlow-181717?style=for-the-badge&logo=github&logoColor=white" alt="RentFlow" />
  </a>
</p>

`Java` · `Spring Boot` · `PostgreSQL` · `Redis` · `Kafka` · `Docker` · `Kubernetes` · `OpenShift` · `OpenTelemetry` · `Dynatrace`

</div>

---

## About

I'm a backend-focused engineer who likes the parts of software that become interesting **after the happy path stops working**.

I care about financial correctness, transactional workflows, concurrency, idempotency, failure recovery, observability, and building product flows that remain understandable as the system grows.

My current direction sits at the intersection of **backend engineering, production reliability, and product systems**.

---

## Selected engineering work

<table>
<tr>
<td width="50%" valign="top">

### 🏦 CoreBank

**Financial correctness under retries, concurrency, and partial failure.**

A production-oriented core-banking backend built around PostgreSQL as the source of truth for money.

**Engineering focus**
- Double-entry ledger
- Hold / capture / void payment lifecycle
- Idempotent money commands
- Concurrency-safe transfers
- Transactional outbox
- Reconciliation & break detection
- Runtime operational controls
- OpenShift restricted-v2 deployment
- Dynatrace incident RCA

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

**A car-rental marketplace designed around booking correctness.**

A full-stack product where availability, booking, payment, and trip workflows are treated as stateful business processes rather than CRUD screens.

**Engineering focus**
- Double-booking prevention
- Pessimistic availability locking
- Idempotent booking creation
- Payment lifecycle safety
- Explicit state transitions
- JWT / RBAC boundaries
- Transactional outbox
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
| ⚔️ | **Concurrency is a product problem** | Booking the same car twice or spending the same balance twice is not just a database detail. |
| 🔎 | **Observe the failure, not only the uptime** | Metrics, traces, logs, and runbooks should explain *why* a system degraded. |
| 🧩 | **Architecture follows pressure** | I prefer the smallest architecture that preserves the required guarantees. |

---

## Verified platform work

```text
CoreBank — runtime-verified, with evidence in the repo
  ├─ OpenShift (Developer Sandbox) under restricted-v2 · Route · HPA · rollback
  ├─ Kubernetes on Kind · probes · PDB · rolling update · failed-rollout recovery
  ├─ OpenTelemetry → Dynatrace · JDBC spans · 45 s row-lock RCA
  └─ Istio 1.31 · canary · STRICT mTLS · rollback

Next: Dynatrace Operator (DynaKube) · OpenShift Service Mesh · NetworkPolicy
```

Every item above was executed against a live cluster and captured in the repository — not read about.

---

## Toolbox

<div align="center">

### Backend & product

<img src="https://skillicons.dev/icons?i=java,spring,ts,nextjs,react" alt="Backend and frontend stack" />

### Data & infrastructure

<img src="https://skillicons.dev/icons?i=postgres,mysql,redis,docker,kubernetes,linux,githubactions,git" alt="Data and infrastructure stack" />

<br />

<img src="https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white" alt="OpenTelemetry" />
<img src="https://img.shields.io/badge/OpenShift-EE0000?style=flat-square&logo=redhatopenshift&logoColor=white" alt="OpenShift" />
<img src="https://img.shields.io/badge/Dynatrace-1496FF?style=flat-square&logo=dynatrace&logoColor=white" alt="Dynatrace" />
<img src="https://img.shields.io/badge/Istio-466BB0?style=flat-square&logo=istio&logoColor=white" alt="Istio" />
<img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" alt="Kafka" />
<img src="https://img.shields.io/badge/Testcontainers-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Testcontainers" />

</div>

---

## What I'm optimizing for

Not the largest number of frameworks.

I'm trying to become the engineer who can follow one production problem all the way through:

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

<div align="center">

### Build the system. Break the assumptions. Understand the failure.

<sub>Hanoi, Vietnam · Open to observability/APM, platform &amp; DevOps, and Java backend engineering roles.</sub>

</div>
