# Open questions

Undecided; each is settled by an ADR in [`adr/`](./adr/) (or a gluon ADR where it changes
a platform service) before the story that needs it.

1. **Roles in user-service, or separate accounts?** Restaurant staff and couriers need
   sign-in in Releases 1 and 2. Roles keep one identity service; it may be the first
   platform API change gfood asks for.
2. **Authorise then capture, or charge at checkout?** Real platforms differ.
   Authorise-then-capture makes rejections cheap (release the hold); check what
   payment-service supports.
3. **Order states: whose are they?** If order-service's lifecycle can't express
   "accepted, ready, picked up" without gfood nouns, those states live in restaurant-
   and dispatch-service, and order only knows placed, paid, completed, cancelled.
4. **Geography in the sandbox.** No map tiles or geocoding are reachable. A seeded grid
   of postcodes with coordinates and straight-line distance keeps dispatch and ETAs real
   enough.
5. **Live updates.** Tracking wants push (SSE or WebSocket). gshop polls today; is a push
   channel a platform capability or a gfood one?
6. **One city, one zone for the skeleton?** Suggested: yes. Zones per restaurant arrive
   in Release 1.
