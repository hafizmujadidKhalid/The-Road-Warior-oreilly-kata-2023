---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Personal Identifiable Information data from emails

## Context and Problem Statement

The storage of Personal Identifiable Information (PII) data from emails poses
significant risks to data security and privacy. It is imperative to establish a
clear policy regarding the handling of PII data within email communications to
mitigate these risks effectively.
Storing PII data in databases creates a larger attack surface for
cybercriminals. A breach of the database can result in the exposure of a
significant amount of sensitive information.

## Considered Options

* Restrict access to PII data to authorized personnel only.
* Implement robust encryption techniques to safeguard PII data both during
  transmission and storage.
* Never store emails of PII data from email

## Decision Outcome

Chosen option: "Never store emails of PII data from email", because: if there
is no PII data nothing to risk.
