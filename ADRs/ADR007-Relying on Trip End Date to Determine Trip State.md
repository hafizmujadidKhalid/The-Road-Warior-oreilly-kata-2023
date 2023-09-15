---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Relying on Trip End Date to Determine Trip State

## Context and Problem Statement

The technical issue under consideration is the determination of the state of
trips within our system. Specifically, we need to decide whether to rely solely
on the trip's end date as the basis for determining its state, with the
objective of simplifying state management and reducing the complexity
associated with scheduling updates.

Our system manages a variety of trips, each with its own lifecycle and state.
The accurate determination of a trip's state is crucial for various aspects,
including reporting, user notifications, and business logic. Historically, we
have relied on various criteria and complex state management mechanisms to
determine trip states.

## Decision Outcome

After careful analysis and discussion, it has been decided to rely primarily on
the trip's end date as the primary factor for determining its state. This
approach eliminates the need for complex state management and reduces the
effort associated with scheduling updates. The decision encompasses the
following considerations:

1. Simplicity: Relying on the trip's end date simplifies the state
   determination process, making it more intuitive and easier to manage.

1. Transparency: Using the end date as the basis for state determination
   provides transparency to users and developers, as it aligns with their
natural understanding of a trip's lifecycle.

1. Automation: State transitions can be automated based on the trip's end date,
   reducing the need for manual intervention and complex logic.

1. Reduced Complexity: Eliminating the need for multiple criteria and intricate
   state management logic reduces code complexity, making the system more
maintainable and less error-prone.

1. Improved Performance: Simplified state determination typically results in
   faster processing and reduced computational overhead.

### Consequences

Implementing this approach has several consequences:

1. Dependency on End Date Accuracy: The accuracy of trip end dates becomes
   critical, as it directly affects state determination. Measures should be in
place to ensure that end dates are correctly recorded.

1. Limited State Flexibility: While this approach simplifies state management,
   it may not accommodate complex state transitions or business rules that
require consideration of other factors. In such cases, additional logic may be
needed.

1. Transition Predictability: Users and developers should be aware that state
   transitions are primarily determined by the end date, which may lead to
predictability concerns if other factors are not considered.

1. Data Integrity: Data integrity checks should be in place to validate that
   the end date is correctly recorded and that it aligns with the trip's actual
conclusion.

