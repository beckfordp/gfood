# Story map

Jeff Patton's form. The backbone runs left to right in the order the work happens
across all three sides; each release below it is a thin, usable path end to end, not a
component. Personas: [personas.md](./personas.md). *(seeded)* marks a stand-in that is
seeded data, not a built story.

## Backbone

| # | Activity | Who | Steps |
| --- | --- | --- | --- |
| A1 | Get set up | Restaurant | Join gfood · Build the menu · Set hours and area |
| A2 | Find food | Customer | Set address · Browse restaurants · Read a menu |
| A3 | Choose and pay | Customer | Fill a basket · Check out |
| A4 | Prepare | Restaurant | Receive the order · Accept or reject · Cook and hand over |
| A5 | Deliver | Courier | Go online · Take a job · Pick up, drop off · Get paid |
| A6 | Wait for it | Customer | Follow progress · Hear what changed |
| A7 | Afterwards | Customer | Rate · Report a problem · Order again |
| A8 | Make it right | Support | Look up an order · Refund or cancel |

## R0 — Walking skeleton

One seeded restaurant, one seeded courier: an order goes from basket to door, touching
every side.

| Step | Stories |
| --- | --- |
| Join gfood | *(seeded)* Restaurants seeded |
| Build the menu | *(seeded)* Menu seeded: names, prices |
| Set hours and area | *(seeded)* Always open; one zone of seeded postcodes |
| Set address | Enter a postcode; told if it's outside the zone |
| Browse restaurants | See restaurants that deliver to me |
| Read a menu | See items and prices |
| Fill a basket | Add, change quantity, remove · One restaurant per basket |
| Check out | Pay with a saved test card · See total with delivery fee |
| Receive the order | New order appears on the tablet |
| Accept or reject | Accept the order |
| Cook and hand over | Mark the order ready |
| Go online | *(seeded)* One courier, always online |
| Take a job | Assigned automatically when the restaurant accepts |
| Pick up, drop off | Mark picked up · Mark delivered |
| Follow progress | See status: placed, accepted, ready, on the way, delivered |
| Hear what changed | Email at each status change |
| Look up an order | See an order and its timeline (gshop admin) |

## R1 — A real kitchen

Restaurants control their side: options, sold out, hours, prep time, and saying no.

| Step | Stories |
| --- | --- |
| Join gfood | Staff sign in to the tablet |
| Build the menu | Options and extras on items · Allergens per item · Mark an item sold out |
| Set hours and area | Opening hours · Pause new orders when busy · Delivery zone per restaurant |
| Browse restaurants | Closed and paused restaurants shown as such |
| Read a menu | Sold-out items shown, not orderable · Allergens on every item |
| Fill a basket | Choose options; price updates |
| Check out | Fee breakdown: delivery, service, small order |
| Receive the order | Tablet sounds until acknowledged |
| Accept or reject | Reject with a reason; customer refunded · No answer in time: cancelled and refunded |
| Cook and hand over | Set prep time on accepting |
| Follow progress | ETA from prep time |
| Hear what changed | Told at once on rejection or cancellation |

## R2 — Real dispatch

Couriers choose work; jobs are offered, timed to the food, and tracked to the door.

| Step | Stories |
| --- | --- |
| Go online | Courier signs in, goes online and offline · Location shared while online |
| Take a job | Offer to the nearest courier, with the fee · Decline or let expire; offered to the next · Sent so arrival matches ready time · Nobody accepts: restaurant and customer told |
| Pick up, drop off | Directions to restaurant, then customer · Proof of delivery: photo or code · Customer not answering: timer, then left |
| Get paid | Fee per job, earnings today · Waiting time paid |
| Follow progress | Courier on a map; ETA updates |
| Refund or cancel | Reassign a courier |

## R3 — Trust and care

When something goes wrong, it is put right quickly and fairly.

| Step | Stories |
| --- | --- |
| Set hours and area | Payout statement with commission |
| Check out | Tip the courier |
| Get paid | Weekly earnings statement |
| Follow progress | Cancel free before the restaurant accepts |
| Rate | Rate the food and the delivery |
| Report a problem | Report a missing or wrong item |
| Order again | Reorder a past order |
| Refund or cancel | Refund an item · Cancel and refund an order · Flag repeat claims |

## Later, not sliced yet

Vouchers and promotions · Scheduled orders · Collection instead of delivery · Group
orders · Stacked deliveries · Busy-time pricing · Subscription (free delivery) · Search
and filter by cuisine or diet · Favourites, saved addresses · Chains with many sites
