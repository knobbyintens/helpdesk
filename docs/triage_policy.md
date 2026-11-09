# Customer Support Triage Policy (v3)

Every open issue in this repository is one open customer ticket. Ticket ids are
written in the issue title as `[CUST-xxxx]` and the structured fields (Priority,
Type, Opened, Customer, Plan) are in the issue body.

The weekly triage run evaluates the rules below **in order**. The first matching
rule wins.

1. `Type: duplicate` -> close the ticket; comment must start with `[DUPLICATE]` and name
   the original ticket id.
2. `Type: how-to` -> close the ticket; comment must start with `[HOW-TO]` and include
   the knowledge-base link https://kb.northstar-cloud.example.com/help/how-to
3. `Priority: P1` and the ticket has been open for **more than 3 days** -> leave it
   open; comment must start with `[ESCALATED]` and name the on-call engineer.
4. `Priority: P3` and the ticket has been open for **21 days or more** -> close it;
   comment must start with `[STALE]`.
5. Otherwise -> leave the ticket untouched (no comment, no state change).

After handling the individual tickets, open one new issue in this repository titled
`Weekly triage digest - <date>` that lists the escalated ticket ids and the
escalated / closed / monitored counts.
