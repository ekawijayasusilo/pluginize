<!-- WHEN TO USE THIS TEMPLATE
     Use an RFC when proposing a substantive change that needs team input
     before commitment. Multiple alternatives are on the table; the decision
     is not yet made. The document exists to drive discussion: author writes
     it, team reads and comments, decision emerges.

     If the decision has already converged and you are recording the outcome
     for future readers, use the ADR template instead. A common pattern: write
     an RFC, debate it, then write an ADR that records the chosen outcome.

     This template has many sections. Delete the ones that do not apply
     (especially Operations, Timeline, Future work) rather than leaving them
     empty. A focused RFC is more useful than a complete-looking one.

     Strip this comment block before publishing. -->

# RFC: [Title]

<!-- guidance: Title should name the thing being proposed in concrete terms,
     not "Proposal for considering X." Bad: "Proposal for caching layer
     evaluation." Good: "Add a Redis caching layer for product-detail reads." -->

| Field | Value |
|---|---|
| Author | [Name] |
| Status | Draft / Open for review / Accepted / Rejected / Superseded |
| Created | YYYY-MM-DD |
| Last updated | YYYY-MM-DD |
| Discussion | [link to PR, doc comments, or thread] |

## Summary

<!-- guidance: One paragraph. State what is being proposed and why. A reader
     who only reads this paragraph should understand the proposal and its
     motivation. Aim for 3-5 sentences. No throat-clearing, no buildup. -->

## Goals and non-goals

<!-- guidance: Two short lists. Goals are what this proposal will accomplish.
     Non-goals are what it will explicitly NOT accomplish — adjacent problems
     people might assume are in scope but aren't.

     Non-goals are the more important of the two: they bound the discussion
     and prevent scope creep during review. If you struggle to list non-goals,
     the proposal is probably too broad. -->

### Goals

-
-

### Non-goals

-
-

## Background and motivation

<!-- guidance: What is the current state of the world? Why is this change
     being proposed? What is the cost of NOT doing it?

     Concrete: numbers, examples, real incidents, specific pain points. Not
     abstract: "improve developer experience" is not a motivation; "reduce
     average build time from 8 minutes to under 2" is.

     Define any key terms or internal names the rest of the document will
     use. -->

## Detailed design

<!-- guidance: The substance of the RFC. What will be built, changed, or
     decided. This is typically the longest section. Include:
       - The shape of the solution (architecture sketch, schema, API surface)
       - The user-facing behavior change, if any
       - The internal mechanics that matter for review
       - Data model changes
       - Migration path if this changes existing behavior
       - Rollout plan if non-trivial
     Use subheadings freely. Diagrams welcome where they help. -->

## Alternatives considered

<!-- guidance: For each serious alternative: what it would be, and why this
     proposal is preferred over it. Two or three alternatives is normal; more
     suggests indecision, fewer suggests insufficient exploration. "Do nothing"
     is always a valid alternative — describe what happens if we accept the
     status quo.

     Also include prior art here: existing solutions inside or outside the
     company that solve the same or adjacent problems. -->

### Alternative 1: [Name]

<!-- guidance: One paragraph each. -->

### Alternative 2: [Name]

### Alternative 3: Do nothing

## Dependencies

<!-- guidance: What existing internal and external systems does this depend
     on? How will it use them? Include:
       - Internal services or libraries this needs
       - External APIs or vendors
       - Teams whose work this depends on
       - Required infrastructure changes
     If this proposal blocks on someone else's work, name them and the work
     here. -->

## Operations

<!-- guidance: Who will run this? What new regular human processes or extra
     work does this create for any team?

     Cover:
       - Ownership: which team owns the system after launch
       - On-call: how alerts route, what runbooks need to exist
       - Deployment: how this gets shipped and rolled back
       - Maintenance: recurring tasks (cert rotation, capacity reviews, etc.)
     If this is just a code change with no operational surface, write "N/A"
     and move on. -->

## Security, privacy, and compliance

<!-- guidance: What security, privacy, or compliance aspects should be
     considered? Examples:
       - New attack surface (public endpoints, user-controlled inputs)
       - PII or sensitive data handling
       - Auth/authz model changes
       - Data retention and deletion
       - Regulatory implications (GDPR, HIPAA, SOC2, etc.)
     If you are not certain, do not assume there are no concerns — flag the
     section for security/privacy review explicitly. "No concerns identified,
     pending security review" is a valid placeholder. -->

## Drawbacks and tradeoffs

<!-- guidance: What does this proposal cost — costs you are knowingly
     accepting? Distinct from Risks below (which covers what could go wrong).
     Examples:
       - Operational burden (more services to run, more on-call surface)
       - Migration complexity for downstream teams
       - Lock-in to a vendor or pattern
       - Performance regressions in specific scenarios
       - Team learning curve
     If there are genuinely no drawbacks, the proposal is probably too small
     for an RFC. -->

## Risks and mitigations

<!-- guidance: What could go wrong, and what is your plan if it does?
     Distinct from Drawbacks above (which covers certain costs).

     For each risk: state the risk, the rough likelihood/impact, and the
     mitigation. Risks without mitigation plans read as worries, not
     analysis.

     Common categories to scan:
       - Technical complexity that may blow estimates
       - Compatibility with existing systems
       - Latency or throughput surprises
       - Maturity of new dependencies (libraries, services)
       - Team expertise gaps
       - Adoption risk if other teams must change behavior -->

## Success metrics

<!-- guidance: How will we know this worked? Concrete, measurable criteria
     that someone can evaluate after the change ships. Examples:
       - "p99 checkout latency drops below 200ms within 30 days of launch"
       - "Cache hit rate on product-detail reads exceeds 80%"
       - "Build pipeline completes in under 4 minutes for 95% of runs"
     Vague positive outcomes ("better performance," "happier developers") do
     not count. If you cannot state a metric, state the qualitative
     condition that would convince you the change worked. -->

## Timeline and milestones

<!-- guidance: Optional. Rough timeline for delivery, with milestones if the
     work spans multiple phases. Delete this section if the work is small
     enough that timing does not need its own section, or if the team handles
     scheduling elsewhere (project tracker, sprint plan).

     Example:
       - Week 1-2: schema migration + dual-writes
       - Week 3: backfill
       - Week 4: cut reads over, monitor
       - Week 5: clean up dual-write path -->

## Open questions

<!-- guidance: Things you do not know the answer to and want input on.
     Explicitly numbered or bulleted. Open questions are a feature of an RFC,
     not a weakness — they are why we write RFCs instead of just shipping. -->

1.
2.
3.

## Future work

<!-- guidance: Optional. What is out of scope for this RFC but related and
     likely to come up. Helps reviewers understand what is *not* being decided
     here. Delete this section if nothing applies. -->

## References

<!-- guidance: Links to related RFCs, prior art, external articles,
     documentation, or discussion threads. -->
