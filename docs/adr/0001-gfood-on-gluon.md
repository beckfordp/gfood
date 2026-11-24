# 0001. gfood on gluon: reuse, new services and the walking skeleton

## Status
Proposed (2026-11-23).

## Context
gfood is a food-delivery application: a three-sided marketplace of customers,
restaurants and couriers ([primer](../primer.md)). It is the first application built on
gluon as its own repo, in Rust, and the first test of gluon's reuse as a platform.
The domain, personas and story map are agreed ([story map](../story-map.md)); the
questions in [open-questions.md](../open-questions.md) are not.

## Decision
1. **gfood is its own application on gluon.** Its own repo at gluon's `apps/gfood`; its own
   instances of the platform services it uses; its own namespace (`gfood`); its stories,
   ADRs and conductor here.
2. **Platform services used as they are where they fit:** user, payment, notification,
   order, catalog, cart ([`app.yaml`](../../app.yaml)). A change gfood needs in one is a
   platform backlog item in that service's repo, never a fork.
3. **Two services of gfood's own, written concretely for gfood:**
   - `restaurant-service-rs`: restaurants, hours, zones, accept or reject, prep time,
     ready.
   - `dispatch-service-rs`: couriers, offers, assignment, pick-up, delivery, tracking.
   Their repos are created when R0's first story needing them starts.
4. **inventory and fulfilment aren't used.** Sold out is a flag on a menu item, and
   dispatch takes fulfilment's place. Revisit inventory if counted stock appears.
5. **Build the walking skeleton (R0) first:** one seeded restaurant world and one seeded
   courier, an order going from basket to door across every side
   ([user-stories.md](../user-stories.md)). R1–R3 follow the story map's slices.

## Consequences
- gfood's first stories test gluon's reuse claim: R0 should need no fork of a platform
  service. Where it needs a change (likely candidates: restaurant grouping in catalog,
  the one-restaurant basket rule, roles in user), it is raised in that service's repo.
- The open questions (roles, payment timing, ownership of order states, geography, live
  updates, one zone) are each settled by an ADR here, or in gluon where a platform
  service changes, before the story that needs it.
- gluon's deploy tooling doesn't yet read `app.yaml`; until it does, gfood can't be
  deployed on its own.

## Alternatives considered
- **Prototype the frontend first.** Rejected as a first step: it leads with screens,
  and food delivery's hard parts (acceptance, timing, dispatch, refunds) are off-screen.
  A prototype follows the story map, to check it.
- **One service for restaurants and dispatch.** Fewer repos, but the two change for
  different people (Rosa, Kofi) and at different releases (R1, R2).
- **Use inventory for sold out.** A count is more than the domain needs; a flag on the
  menu item is what restaurants toggle.
