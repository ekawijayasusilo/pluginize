<!-- WHEN TO USE THIS TEMPLATE
     Use a design doc to plan substantial engineering work before building it:
     a new system, a significant feature, a hard or novel problem, or anything
     that needs coordination across teams. It answers "HOW will we build
     this?" — the direction is broadly agreed and you are specifying the
     implementation.

     Skip it for trivial or well-understood work where the design space is
     small. If you are still deciding *whether* or *which direction* to go —
     multiple alternatives genuinely live, the call not yet made — write an
     RFC instead. If you just need to record one decision that has already
     converged, write an ADR.

     Why bother: the main value is getting feedback early, before you commit,
     while changes are still cheap — and the writing itself forces you to
     think the design through clearly. A good design doc also makes the
     cross-cutting concerns (security, privacy, observability) impossible to
     forget.

     Lifecycle: a design doc is most valuable *during* the design phase. It is
     NOT a living document — once the system is built, the source of truth
     moves to the code, and this doc becomes a historical artifact. Write it
     while the design is still in flux, not afterward.

     Length: as long as it needs to be and no longer. A one-pager is a
     perfectly good design doc for a small effort; a large system might warrant
     10-20 pages. If it runs past ~20 pages, the problem is probably too big —
     split it. Delete every section below that does not apply (the optional
     ones are marked) rather than padding it out.

     Strip this comment block before publishing. -->

# Design Doc: [System or feature name]

<!-- guidance: Name the thing concretely. Bad: "Design Doc: Backend
     improvements." Good: "Design Doc: Real-time presence service." -->

| Field | Value |
|---|---|
| Author(s) | [names] |
| Reviewers | [names or teams] |
| Status | Draft / In review / Approved / Implemented / Obsolete |
| Created | YYYY-MM-DD |
| Last updated | YYYY-MM-DD |

## Context and scope

<!-- guidance: The objective background a reader needs to understand the rest
     of the doc: the landscape this system fits into and, roughly, what is
     being built. Stick to facts — not goals, and not the solution. Keep it
     short; the job is to get the reader up to speed quickly, not to recount
     every detail. -->

## Goals and non-goals

<!-- guidance: Two short bulleted lists. Goals are the outcomes the design must
     achieve, ideally concrete enough to check.

     Non-goals are the sharp tool here. They are NOT negative goals — they are
     things that could reasonably be assumed in scope but that you are
     deliberately choosing to exclude. For example, "ACID compliance" or
     "supporting on-prem deployment" might be explicit non-goals. Naming them
     bounds the review and heads off scope creep. -->

### Goals

-
-

### Non-goals

-
-

## The design

<!-- guidance: The heart of the doc, and usually the longest section. Start
     with a high-level overview so a reader gets the shape of the solution,
     then drill into detail. Throughout, explain the trade-offs you made and
     *why* — the reasoning is what reviewers engage with.

     Use the subsections below as they apply and delete the rest. Add others
     (a sequence diagram, a state machine) where they clarify. -->

### System-context diagram

<!-- guidance: Show the system as one box within the larger technical
     landscape — its users, its collaborators, and the systems it depends on
     and is depended on by. Lets readers place the new design against what
     they already know. -->

### APIs

<!-- guidance: The key interfaces or contracts the system exposes. Show
     representative signatures and the parts that matter for review — do NOT
     paste the full IDL, schema, or generated definitions. Convey the surface,
     not every detail. -->

### Data storage

<!-- guidance: How and in what form data is stored — the storage engine, the
     shape of the data, and its lifecycle (retention, migration) where
     relevant. As with APIs, convey the model without dumping every column. -->

### Code and pseudo-code

<!-- guidance: Use sparingly. Include a snippet only to illustrate something
     genuinely novel or hard to convey otherwise — a tricky algorithm or the
     feel of a new API. A design doc operates above the level of implementation
     detail; it is not the place for production code. Delete this subsection if
     you do not need it. -->

## Degree of rigor

<!-- guidance: Optional. How thoroughly has this design been validated, and how
     thoroughly does it need to be? Signals your confidence to reviewers. A
     spectrum: a back-of-the-envelope estimate, a throwaway prototype, a
     proof-of-concept under load, a benchmark, or a formal correctness
     argument. State what you have done and what you still intend to do. Fold
     this into "The design" or delete it if it adds nothing. -->

## Cross-cutting concerns

<!-- guidance: The concerns that cut across the whole design and are the
     easiest to forget — which is exactly why this section exists. Keep each
     short: a sentence or two on how the design handles it, or an explicit
     "N/A, because…". Do not skip Security, Privacy, and Observability even
     when the answer is brief. -->

### Security

<!-- guidance: New attack surface, authn/authz, untrusted input, secrets,
     trust boundaries. -->

### Privacy and compliance

<!-- guidance: PII or sensitive data handled, retention and deletion, and any
     regulatory implications (GDPR, HIPAA, SOC2, …). -->

### Observability

<!-- guidance: How you will know the system is healthy and debug it when it is
     not — logs, metrics, traces, and the alerts that page someone. -->

### Scalability and performance

<!-- guidance: Optional. Expected load, latency targets, capacity, and where
     the design bottlenecks first. Delete if not relevant. -->

### Reliability and failure modes

<!-- guidance: Optional. What happens when a dependency is down or slow —
     degradation, retries, fallbacks, disaster recovery. Delete if not
     relevant. -->

### Cost

<!-- guidance: Optional. Infrastructure or operational cost, if it is a
     material factor in the design. Delete if not relevant. -->

## Alternatives considered

<!-- guidance: Other designs that would reasonably have achieved comparable
     outcomes, and why you chose this one over them — the trade-offs. This is a
     hallmark of a serious design doc: it shows you explored the space. "Do
     nothing" and "use existing system X" are valid alternatives. Unlike an
     RFC, these are alternatives to a chosen design, not options in an open
     decision. -->

## Dependencies and cross-team impact

<!-- guidance: Optional. Internal and external systems this design relies on,
     and teams whose work it blocks or is blocked by. If your design depends on
     someone else's work, name them and it here. Delete if there are none. -->

## Rollout and migration

<!-- guidance: Optional. How this ships safely: feature flags, phased rollout,
     data migration or backfill, and the rollback plan if it goes wrong. Delete
     if the rollout is trivial. -->

## Open questions

<!-- guidance: Optional. Design questions you have not resolved and want
     reviewers' input on. Note: these should be details within an agreed
     direction. If the direction itself is in question, you want an RFC, not a
     design doc. -->

## References

<!-- guidance: Links to the originating RFC (if any), related design docs and
     ADRs, prior art, and supporting documentation. -->
