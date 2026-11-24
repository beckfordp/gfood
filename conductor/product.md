# Product Guide — gfood

## Context
gfood is an application on the Gluon platform; the platform's own docs live in gluon's
`docs/`. gfood's decisions are in [`../docs/adr/`](../docs/adr/).

## What this app does
Food delivery: a three-sided marketplace where customers order from local restaurants
and couriers deliver. gfood coordinates the three under a clock: the restaurant accepts
and sets a prep time, a courier is sent to arrive as the food is ready, and the customer
follows an ETA. See [`../docs/primer.md`](../docs/primer.md).

## Users
Five personas ([`../docs/personas.md`](../docs/personas.md)): Asha and Dan (customers),
Rosa (restaurant), Kofi (courier), Mei (support).

## Scope
The [story map](../docs/story-map.md) is the plan: R0 walking skeleton, R1 a real
kitchen, R2 real dispatch, R3 trust and care. Stories in
[`../docs/user-stories.md`](../docs/user-stories.md); each becomes a track here or in a
service repo.

## Services
Decided as the stories start, under gfood's
[reuse rule](../README.md#reuse-is-harvested).

## Goals
- Show gluon as a substrate: gfood built from its services, tools, libraries and ways
  of working.
- A demo that runs end to end in the sandbox and on the laptop, like gshop.
