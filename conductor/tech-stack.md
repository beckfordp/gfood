# Tech Stack — gfood

- **Services:** Rust, from gluon's `tools/rust-service-template` and `lib/gluon-rs`, as
  the platform's Rust ports (axum, sqlx and Postgres, Kafka with the Debezium outbox).
  Each its own repo under `services/`, with its own conductor and tech stack.
- **Platform services:** gluon's Rust ports, deployed as gfood's own instances
  ([`../app.yaml`](../app.yaml)).
- **Frontends:** React, TypeScript and Vite, as gshop (gluon ADR 0006). Each its own repo
  under `frontends/`.
- **Runtime:** gluon's Kubernetes setup (Helm chart `infra/k8s/gluon`); gluon-kube in the
  sandbox, OrbStack on the laptop. Namespace `gfood`.
- **Acceptance:** Playwright BDD, as gluon's `tests/acceptance` (gluon ADR 0023).
- **This repo:** documentation and the application manifest; no code of its own yet.
