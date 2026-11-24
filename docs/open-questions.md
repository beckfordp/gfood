# Open questions

Undecided; each is settled by an ADR in [`adr/`](./adr/) before the story that needs it.

1. **One identity with roles, or separate accounts?** Restaurant staff and couriers need
   sign-in in Releases 1 and 2.
2. **Authorise then capture, or charge at checkout?** Real platforms differ.
   Authorise-then-capture makes rejections cheap (release the hold).
3. **Order states: whose are they?** Who owns "accepted, ready, picked up": the order,
   or the restaurant and courier sides?
4. **Geography in the sandbox.** No map tiles or geocoding are reachable. A seeded grid
   of postcodes with coordinates and straight-line distance keeps dispatch and ETAs real
   enough.
5. **Live updates.** Tracking wants push (SSE or WebSocket). gshop polls today.
6. **One city, one zone for the skeleton?** Suggested: yes. Zones per restaurant arrive
   in Release 1.
