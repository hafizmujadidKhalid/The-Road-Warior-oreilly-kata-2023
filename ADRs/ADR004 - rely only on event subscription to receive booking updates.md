---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Rely only on event subscription to receive booking updates 

## Context and Problem Statement

While there are many channels through which our system can get notified
of an update of a booking, different channels have different levels of complexity
associated with implementing them.

The subject of this ADR it to decide on the approach of how to receive
updates on existing bookings.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Complexity of the domain logic
* Distribution of different approaches to different stages of the product,
    e.g. Phase 1 product differing from Phase 3.
* The availability of APIs where the updates can be fetched from,
    the complexity of implementing them and the amount of APIs to implement
    (and maintain).

## Considered Options

1. Fetch updates from update e-mails sent to users.
2. Fetch updates from GDS' APIs (with event subscription).
3. Fetch updates from travel agencies' APIs.
4. All of the above.

## Decision Outcome

Option #2 was selected for the Phase 1 of the product. Phase 3
aims at solution #4, that is using all available channels.

<!-- This is an optional element. Feel free to remove. -->
### Positive Consequences

* Relatively simple logic in Phase 1 since only a few APIs need to be implemented.

<!-- This is an optional element. Feel free to remove. -->
### Negative Consequences

* Not all bookings can be fetched from the GDS. We assume that 5-10% of bookings
    are only available through the APIs of agencies and as such, those bookings
    won't be available in the Phase 1 product.

<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### Fetch updates from update e-mails sent to users

* Good, because the updates are presumably sent also for bookings not available
    through GDSs.
* Bad, because parsing e-mails is complex and error-prone.
* Bad, because it cannot be used as a standalone solution, but still requires
  in addition to talk to some API to fetch all necessary data.

### Fetch updates from GDS' APIs (with event subscription)

* Good, because it requires the least amount of domain logic.
* Good, because there are only a few GDS to talk to (as compared to the number
  of various agencies).
* Good, because the GDSs' APIs allow for event subscription - therefore the
  APIs don't need to be polled, but rather only requested when an update happens.
* Bad, because some bookings can't be accessed through GDS' API.

### Fetch updates from travel agencies' APIs

* Good, because all bookings can be accessed through agency's API.
* Bad, because it requires implementing huge amount of different APIs
    and there's no standardization amongst them.
