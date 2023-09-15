---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Event Subscription for Reservation Updates

## Context and Problem Statement

Our system handles reservation updates for a variety of bookings, including
those made directly by customers and those facilitated through travel agencies.
Reservation updates are critical for ensuring the accuracy and up-to-date
status of bookings, and the method of receiving these updates needs to be both
efficient and resilient.

## Considered Options

* [Subscriptions in Apollo Server](https://www.apollographql.com/docs/react/data/subscriptions/)
* [Sabre: Event Notification Services](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)

## Decision Outcome

After thorough evaluation and consideration, it has been decided to implement a
hybrid approach for receiving reservation updates:

1. Event Subscription (Preferred Method): The primary method for receiving
   reservation updates will be through event subscription. This approach offers
the following advantages:

* Real-time Updates: Event subscription allows us to receive updates in
  real-time, ensuring that our system reflects the most current reservation
tatus.

* Efficiency: It is a more efficient and responsive way to handle updates
  compared to polling or periodic checks.

* Scalability: Event-driven architectures can be scaled to accommodate high
  volumes of updates.

1. GDS Subscription (Fallback Method): In cases where reservations are made
   through agencies that do not support event subscription, we will resort to
using GDS subscriptions to obtain booking updates. This approach is considered
a fallback method and is justified by the following reasons:

* Agency Limitations: Some travel agencies may not provide event subscription
  capabilities or may have limitations that prevent real-time updates through
this method.

* Data Integrity: To ensure data integrity and accuracy, it is essential to
  have a reliable source of reservation updates, even when direct event
subscription is not available.

### Consequences

Implementing this hybrid approach has several implications:

1. Integration Complexity: Our system will need to support both event
   subscription mechanisms and GDS subscriptions, leading to additional
integration effort.

1. Monitoring and Error Handling: We must implement robust monitoring and
   error-handling mechanisms to track the status of both event subscriptions
and
GDS subscriptions and handle failures gracefully.

1. Data Consistency: Care must be taken to synchronize data obtained through
   event subscription and GDS subscription to maintain data consistency.

