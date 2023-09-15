---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Reservation Updates Scheduler for Bookings without Event Subscription Support

## Context and Problem Statement

The technical issue at hand concerns the implementation of a Reservation
Updates Scheduler to manage and update bookings that do not support event
subscription. We need to determine the approach for scheduling and processing
updates for these reservations to ensure data accuracy and timeliness.

Our system processes a wide range of reservations, some of which are made
through booking channels that do not offer event subscription capabilities. As
a result, these reservations cannot be updated in real-time through
event-driven mechanisms. To address this limitation, we need to implement a
Reservation Updates Scheduler to periodically fetch and update reservation
information.

## Decision Outcome

After thorough analysis and consideration, it has been decided to implement a
Reservation Updates Scheduler to handle bookings without event subscription
support. This scheduler will be responsible for the following tasks:

1. Regular Polling: The scheduler will periodically poll the external booking
   sources that do not support event subscription to check for updates to
reservations. The polling frequency will be determined based on the criticality
of updates and the policies of the booking sources.

1. Data Synchronization: Upon detecting updates during polling, the scheduler
   will retrieve the latest reservation data and synchronize it with our
system's database. This process will include updating reservation details such
as dates, customer information, and booking status.

1. Error Handling: The scheduler will be equipped with robust error-handling
   mechanisms to address any issues that may arise during the polling and
synchronization processes. This includes handling network failures, temporary
unavailability of external sources, or data format inconsistencies.

### Consequences

Implementing a Reservation Updates Scheduler for bookings without event
subscription support has several implications:

1. Latency: Updates for reservations processed through this method will not be
   in real-time, leading to potential latency in reflecting the latest
information in our system.

1. Resource Consumption: Regular polling may consume network bandwidth and
   processing resources, particularly if a large number of reservations need to
be synchronized.

1. Data Consistency: Care must be taken to ensure data consistency and avoid
   conflicts when multiple updates occur for the same reservation during
polling.

1. Monitoring and Alerting: Robust monitoring and alerting mechanisms should be
   in place to track the status of the scheduler, detect failures, and trigger
corrective actions promptly.

