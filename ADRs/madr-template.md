---
status: proposed
date: 2023-09-14
deciders: Idealos
---
# Choose `madr` Template as Standard ADR Template

## Context and Problem Statement

PA Data Platform humans should have it easy to create ADRs and should not spend time choosing an ADR format. The goal is to standardize on a suitable template and share it.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Template is short / not to long. The effort for creating an ADR should be less than 5 minutes (?!).
* The template gives helpful guidance
* Tooling available

## Considered Options

* [madr template](https://github.com/adr/madr/blob/main/template/adr-template.md), see [website](https://github.com/adr/madr)
* [Nygard template](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)

## Decision Outcome

Chosen option: "madr template", because the template is lean and mature. The [list of decisions](https://github.com/adr/madr/tree/main/docs/decisions) are great examples of ADRs.

<!-- This is an optional element. Feel free to remove. -->
### Positive Consequences

* There are resources and tools for this template, which should facilitate adoption.

<!-- This is an optional element. Feel free to remove. -->
### Negative Consequences

* Template changes over time. Previously created ADRs are still valid but might have a different structure.


<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### Madr Template

<!-- This is an optional element. Feel free to remove. -->
See [template](https://github.com/adr/madr/blob/main/template/adr-template.md) and [github repo](https://github.com/adr/madr).

* Good, because template is lean.
* Good, because the template is well thougt out, see [list of decisions](https://github.com/adr/madr/tree/main/docs/decisions).
* Good, because there is [tooling](https://adr.github.io/madr/tooling.html) for the template.
* Neutral, because the list of decsions above are great examples of ADRs.

### Nygard Template

See [template](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)

* Good, because it gives freedom.
* Bad, because it gives too little guidance.
* Bad, because we would need to create our own markdown file.

<!-- This is an optional element. Feel free to remove. -->
## More Information

* [Love Unrequited: The Story of Architecture, Agile, and How Architecture Decision Records Brought Them Together](https://ieeexplore.ieee.org/document/9801811)
* [Gut Dokumentiert](https://www.heise.de/hintergrund/Gut-dokumentiert-Architecture-Decision-Records-4664988.html) [German, boring anyway :)]
