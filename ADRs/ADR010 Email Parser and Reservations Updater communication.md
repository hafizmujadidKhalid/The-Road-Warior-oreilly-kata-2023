---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Email Parser and Reservations Updater Communication

## Context and Problem Statement

Our system receives reservation requests via email from customers. The Email
Parser component is responsible for extracting reservation details, such as
dates, customer information, and preferences, from incoming emails. Once these
details are extracted, they need to be communicated to the Reservations Updater
component, which updates the reservation database accordingly.

## Considered Options

* [Message broker](https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageBroker.html)
* [Message bus](https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageBus.html)

## Decision Outcome

After careful consideration, it has been decided to implement a message-bus
communication approach between the Email Parser and Reservations Updater
components. This decision is based on the following considerations:

1. Loose Coupling: A message-bus approach allows for loose coupling between the
   components. The Email Parser can generate reservation request messages in a
format that the Reservations Updater understands without needing to know the
internal details of the Reservations Updater.

1. Scalability: As our system grows and reservation volumes increase, a
   message-bus approach provides the flexibility to scale each component
independently to handle the load efficiently.

1. Asynchronous Processing: Messages can be processed asynchronously, allowing
   for efficient handling of multiple reservation requests in parallel. This
ensures that the system remains responsive and can handle peak loads
effectively.

1. Error Handling: Messages can include error-handling information and retries,
   ensuring robustness in the face of transient failures.

1. Logging and Monitoring: Messages can be logged and monitored, providing
   visibility into the reservation processing flow and facilitating debugging
and troubleshooting.

### Consequences

Implementing a message-based communication approach between the Email Parser
and Reservations Updater components has several consequences:

1. Development Effort: There will be some development effort required to
   implement the message generation and consumption logic in both components.

1. Message Format: A standardized message format needs to be defined and agreed
   upon by both components to ensure successful communication.

1. Testing: Comprehensive testing and integration testing will be necessary to
   ensure that messages are correctly generated, transmitted, and processed.

1. Infrastructure Considerations: Infrastructure support for message bus may be
   necessary, depending on the chosen messaging technology.
