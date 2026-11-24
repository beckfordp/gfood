# User Stories — R0, walking skeleton

From the [story map](./story-map.md), release R0: one seeded restaurant, one seeded
courier; an order goes from basket to door, touching every side. Personas:
[personas.md](./personas.md).

Status: draft, first pass. Which service does each task is decided as the stories start;
open questions that change them are in [open-questions.md](./open-questions.md). R1–R3 are written from the map once R0 is
under way.

## US-1 — Seed a restaurant world
As the platform, the skeleton starts with restaurants, their menus, one delivery zone
and one courier seeded, so every side can be exercised before onboarding exists.
- Seeded data, not features: no sign-up, always open.
- Zone and courier position on a seeded postcode grid (open question 4).

### Tasks
- [ ] US-1.1: seeded restaurants, always open, one zone of postcodes
- [ ] US-1.2: seeded menus: items with names and prices, grouped by restaurant
- [ ] US-1.3: one seeded courier, always online

## US-2 — Find a restaurant that delivers to me
As a customer (Asha), I enter my postcode and see the restaurants that deliver there,
so I only choose food that can reach me.
- Outside the zone: told so, no restaurants listed.

### Tasks
- [ ] US-2.1: restaurants delivering to a postcode

## US-3 — Read a menu
As a customer, I see a restaurant's items and prices, so I can choose.

### Tasks
- [ ] US-3.1: a restaurant's menu

## US-4 — Fill a basket
As a customer, I add items, change quantities and remove them, so I build my order.
- One restaurant per basket: adding from a second asks to start a new basket.

### Tasks
- [ ] US-4.1: one-restaurant rule on the basket

## US-5 — Check out
As a customer, I pay with a saved test card and see the total including the delivery
fee, so my order is placed.
- Flat delivery fee in R0; the fee breakdown is R1.
- Payment authorised at checkout (open question 2).

### Tasks
- [ ] US-5.1: checkout creates the order with a delivery fee
- [ ] US-5.2: payment authorised at checkout

## US-6 — Receive and accept an order
As a restaurant (Rosa), a new order appears on the tablet and I accept it, so the
kitchen starts cooking.
- Accept only in R0; reject, timeout and prep time are R1.

### Tasks
- [ ] US-6.1: new orders reach the restaurant
- [ ] US-6.2: accept an order; an accepted event

## US-7 — Mark an order ready
As a restaurant, I mark an order ready, so the courier knows to collect it.

### Tasks
- [ ] US-7.1: mark ready; a ready event

## US-8 — Deliver an order
As a courier (Kofi), I'm assigned an order when the restaurant accepts it, mark it
picked up and then delivered, so the customer gets their food.
- Automatic assignment to the one courier; offers are R2.

### Tasks
- [ ] US-8.1: assign the courier on accept
- [ ] US-8.2: mark picked up, mark delivered; events for each

## US-9 — Follow my order
As a customer, I see my order's status (placed, accepted, ready, on the way,
delivered) and get an email at each change, so I know when it will arrive.
- Where these states live is open question 3.

### Tasks
- [ ] US-9.1: an order's status through the restaurant and courier steps
- [ ] US-9.2: an email per status change

## US-10 — Look up an order
As support (Mei), I see an order and its timeline, so I can answer a customer.
- A support view of the order.

### Tasks
- [ ] US-10.1: order timeline for support
