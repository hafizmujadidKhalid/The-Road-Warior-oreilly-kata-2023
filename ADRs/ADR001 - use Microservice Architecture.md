---
status: proposed
date: 2023-09-14
deciders: Idealos
---
# Use Microservices Architecture

## Context and Problem Statement

Raod Warrior is the next gen travel management dashboard. We need to build it following an architectural style that maximises our success chances by meeting all functional and quality requirements with acceptable tradeofs.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* System must scale to accomodate 15 million users and 2 million active monthly users.
* System must process updates within 5 minutes from notification
* Five minutes of unplanned downtime per month (99.99% availability)
* Rich user experience
* Web and mobile support
* Extensive analytics
* No missed updates
* Fast time to market and rapid iteration speed

## Considered Options

* Layered architecture
* N Tiers
* Modular Monolith
* Microkernel
* Microservices

## Decision Outcome

Chosen option: `Microservices` and `Event Carried State Transfer` where needed. Because:
* Different scalbility requirements for different parts of the system
* Different security and compliance requirements for different parts of the system
* Emphasize on short time to market and rapid iteration
* Strict uptime requirements
* Ability to prallelise work
* Ability to limit faults' blast radius