# services/

gfood's own services, each its own independent git repo, gitignored here
(gluon ADR 0031, decision 4). None yet: `restaurant-service-rs` and
`dispatch-service-rs` are planned (`../app.yaml`).

Platform services (user, payment, notification, order, catalog, cart) live in
gluon's `services/` and are never copied here.
