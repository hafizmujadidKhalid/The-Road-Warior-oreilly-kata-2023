---
status: accepted
date: 2023-09-15
deciders: Idealos
---
# Parse users' e-mail for booking reference only 

## Context and Problem Statement

Our system scans users' mailboxes for e-mails containing information about
bookings, as means to get notified of updates of bookings. 

Since arguably every travel agency users different format of e-mails, the format
changes in time and sometimes the e-mails can be malformed, parsing such e-mails is
connected with non-trivial amount of complexity.

This raised a question how to use the incoming e-mails and what information to look for.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Complexity of parsing e-mails of various formats and cost of maintenance of such logic
* The response time of the dashboard
* The user comfort

## Considered Options

1. E-mails are only considered as notifications of events (e.g. an update of a booking),
  and are only parsed to find a booking reference. The rest of the booking data is fetched
  from agency's API.
2. E-mails are considered as bearers of various information about bookings and attempt
  is made to parse maximum useful information from the e-mail and to deliver it
  to our system.

## Decision Outcome

Option #1 was selected, to minimise the amount of logic needed to parse e-mails.

<!-- This is an optional element. Feel free to remove. -->
### Positive Consequences

* Less logic about parsing e-mails; typically booking reference can be parsed
    from e-mail's subject and parsing of the HTML body can be completely avoided.

<!-- This is an optional element. Feel free to remove. -->
### Negative Consequences

* Delay between an event and update of dashboard is greater, since after e-mail
    is received, the data still need to be fetched from API.
* Every e-mail received requires an API call, therefore the amount of API calls
    might be bigger than with the solution #2.
