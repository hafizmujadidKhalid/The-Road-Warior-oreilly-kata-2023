---
status: proposed
date: 2023-09-14
deciders: Idealos
---
# Trips Social Media Publisher as a Frontend Component

## Context and Problem Statement

We would like to allow the user to share their upcoming trips on social media.

## Considered Options

* Implementation is backend component
* Implementation is frontend component

## Decision Outcome

**Chosen option:** `Frontend component`, because:
* Avoid having to authorise our system to post on behalf of the user
* This is not a core functionality, so it is better to "buy"
* Less BE components to maintain, monitor and pay for
* Simple and well deisgned frontend libraries exist that integrate with a vast array of social media networks and are constantly updated whenever an API changes