<!-- WHEN TO USE THIS TEMPLATE
     Use an ADR when an architectural decision has already converged and you
     are recording the outcome for future readers. The discussion happened
     elsewhere (in an RFC, in a meeting, in a thread); this document captures
     *what* was decided and *why* so someone reading it in two years can
     understand the reasoning without reconstructing the original context.

     If the decision has NOT yet converged — multiple alternatives are still
     on the table and you want team input before committing — use the RFC
     template instead.

     Core principle: ADRs are append-only. Once an ADR is accepted, do not
     edit it. If the decision changes, write a new ADR that supersedes the
     old one, link them, and mark the old one as Superseded.

     Strip this comment block before publishing. -->

# ADR-NNNN: [Title]

<!-- guidance: Number ADRs sequentially in the repo (ADR-0001, ADR-0002, ...).
     Title should be a short imperative phrase describing what was decided,
     ideally under 50 characters — like a git commit message subject line.
     Bad: "Database choice." Good: "Use Postgres as the primary datastore
     for the user service." Present tense, declarative. -->

| Field | Value |
|---|---|
| Status | Proposed / Accepted / Deprecated / Superseded by ADR-NNNN |
| Date | YYYY-MM-DD |
| Deciders | [names or team] |

## Context

<!-- guidance: What is the situation that requires a decision? Include only
     the context a reader needs to understand *why* this decision came up. Do
     not recap history that does not bear on the decision. Two to four short
     paragraphs is typical.

     Frame the forces at play: technical constraints, organizational
     constraints, performance requirements, prior commitments. Save the
     specific factors that drove the choice for the next section. -->

## Decision drivers

<!-- guidance: A short list of the factors that drove this decision. These
     are the criteria you weighed when choosing between alternatives.
     Examples:
       - Must support 50k writes per second
       - Team already operates Postgres in production
       - Vendor lock-in concerns rule out managed-only solutions
       - Compatibility with existing ORM
     Two to six drivers is typical. If you cannot list any, the decision may
     be too small to need an ADR.

     Listing drivers explicitly makes the "why" auditable. A future reader
     can re-evaluate whether the same drivers still apply. -->

-
-
-

## Decision

<!-- guidance: What was decided? Write in plain declarative voice: "We will
     use Postgres for the user service." Not "We are considering" or "It is
     recommended that we might." Be specific enough that someone reading
     this in two years can confirm what was actually decided. One concise
     paragraph is usually enough. -->

## Consequences

<!-- guidance: What are the results of this decision? Cover positive and
     negative consequences honestly. A decision with no negative consequences
     is suspicious — either it was trivial, or the writer is not being
     honest. -->

### Positive

<!-- guidance: What gets better as a result of this decision. -->

### Negative

<!-- guidance: What gets harder, costs more, or creates risk as a result. -->

### Neutral

<!-- guidance: Optional. Side effects that are neither good nor bad but worth
     noting. Delete this subsection if nothing applies. -->

## Alternatives considered

<!-- guidance: Brief — one or two sentences per alternative explaining what
     it was and why it was not chosen. Unlike an RFC, this is not the place
     for deep alternative analysis. The decision is already made; this
     section exists to head off the question "why didn't you just do X?" -->

- **[Alternative 1]**: [one or two sentences on why not chosen]
- **[Alternative 2]**: [one or two sentences on why not chosen]

## Confirmation

<!-- guidance: Optional. How will we verify that this decision was actually
     implemented as decided? For some ADRs this is obvious (look at the
     database — it's Postgres) and the section adds no value. For others it
     is worth stating explicitly:
       - "All new services emit OpenTelemetry traces; verified via the
          observability dashboard at [link]."
       - "Migration plan tracked in [JIRA-XXXX]; complete when all
          services list as migrated in the registry."
     Delete this section if the implementation will be self-evident. -->

## References

<!-- guidance: Links to related ADRs, the RFC this decision came from (if
     any), supporting documentation, or external prior art. -->
