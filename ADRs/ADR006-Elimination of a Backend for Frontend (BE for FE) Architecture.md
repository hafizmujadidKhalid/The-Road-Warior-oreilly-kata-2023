---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Elimination of a Backend for Frontend (BE for FE) Architecture

## Context and Problem Statement

The technical issue at hand is the architectural approach for developing and
maintaining Backend for Frontend (BE for FE) services. Specifically, we need to
decide whether to eliminate the use of BE for FE architecture in our system.

## Decision Outcome

After careful evaluation and discussion, it has been decided to eliminate the
use of BE for FE architecture in our system. The rationale for this decision
includes the following considerations:

1. Simplification: Eliminating BE for FE simplifies the architecture, reducing
   the number of intermediary services and improving overall system simplicity.

1. Efficiency: With BE for FE services, there is often overhead in maintaining
   additional codebases and APIs. Removing these intermediaries can streamline
development and reduce maintenance effort.

1. Latency Reduction: BE for FE services can introduce additional network
   latency and complexity, which can be eliminated by making direct calls to
the core backend services from the frontend.

1. Standardization: A unified architecture allows for standardized API design
   and data retrieval strategies across all frontend applications, making it
easier to maintain consistency.

1. Resource Optimization: By eliminating BE for FE services, we can allocate
   development resources more efficiently, focusing on core backend services
and frontend improvements.

### Consequences

Implementing this decision to eliminate the BE for FE architecture has several
consequences:

1. Backend Adjustments: Core backend services may require adjustments to
   accommodate the direct calls from frontend applications.

1. API Standardization: Standardizing APIs across frontend applications may
   require additional effort to ensure compatibility and consistency.

1. Testing and Validation: Thorough testing and validation are essential to
   ensure that the removal of BE for FE services does not introduce regressions
or performance issues.

