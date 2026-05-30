<!-- WHEN TO USE THIS TEMPLATE
     Use a postmortem to document a production incident after it has been
     resolved: what happened, what it affected, why it happened, and what
     follow-up work will keep it from happening again.

     Write one when the incident was significant: a SEV1 or SEV2, any
     customer-visible outage, data loss, an SLA/SLO breach, or a failure that
     monitoring missed (you found out manually). Anyone should be able to
     request one. A postmortem is not punishment — it is how the whole
     organization learns from a failure.

     This is the only RETROSPECTIVE template in this skill — it describes
     something that already happened. RFCs, ADRs, and design docs are all
     prospective (about work you are about to do).

     Core principle: BLAMELESS. Assume everyone involved acted in good faith
     with the information they had at the time. Focus on the systems and
     processes that allowed the failure, not on the people involved:
       - Attribute actions to roles, not names ("the on-call engineer," not
         "Priya").
       - Avoid counterfactual and blaming language: "should have," "failed
         to," "was careless," "if only X had." These punish hindsight and
         teach people to hide information.
       - Prefer neutral, factual phrasing: "the deploy proceeded because there
         was no staging gate," not "X carelessly skipped staging."
       - Treat human error as a starting point for investigation, never the
         conclusion. If a person could trigger this, ask why the system let
         them.

     Strip this comment block before publishing. -->

# Postmortem: [Incident name] (incident #NNN)

<!-- guidance: Name the incident specifically and searchably — what broke,
     and ideally when. Bad: "The big outage." Good: "Checkout API 500s during
     EU peak (incident #465)." The incident number ties this back to your
     tracker; drop it if you do not number incidents. -->

| Field | Value |
|---|---|
| Date | YYYY-MM-DD |
| Authors | [names or usernames] |
| Status | Draft / In review / Complete, action items in progress / Complete |
| Severity | SEV1 / SEV2 / SEV3 / SEV4 |
| Affected systems | [services / components] |
| Impact window | [start → end, with timezone; total duration] |

<!-- guidance: Severity is a rough measure of business impact; it drives how
     urgently the incident was handled and whether a postmortem is mandatory.
     A common scale:
       - SEV1: critical — full outage or data loss, all-hands response
       - SEV2: major — significant degradation or partial outage, urgent
       - SEV3: minor — limited impact, workaround available, normal hours
       - SEV4: cosmetic — negligible impact
     Use your org's scale if it differs. -->

## Summary

<!-- guidance: One to two sentences in plain language an executive could read:
     what broke, who was affected, how long it lasted, and the headline cause.
     A reader who stops here should still understand the incident. No jargon,
     no buildup. -->

## Impact

<!-- guidance: Quantify the damage. Numbers, not adjectives. Examples:
       - "~12,000 users (8% of EU traffic) could not check out for 47 minutes."
       - "3.2M requests returned 500s; estimated $40k in lost orders."
       - "Breached the 99.9% monthly availability SLO for the checkout service."
     Distinguish full outage from degraded service if both occurred. If you
     cannot quantify impact, state what you do know and flag the gap. -->

## Root cause & contributing factors

<!-- guidance: Most incidents do not have a single root cause — they are the
     result of several contributing factors lining up. List them rather than
     forcing one. For each, prefer the systemic framing: ask "why did the
     system allow this?" not "who did this?"

     The "5 Whys" can be a useful lens for one chain of causation, but treat
     it as one tool, not the answer — do not stop at the first human-error
     step ("the engineer ran the wrong command"); keep going to the system
     that made that error possible and consequential (no confirmation prompt,
     no canary, no fast rollback). Keep the language neutral and blameless. -->

## Trigger

<!-- guidance: The specific event that set the incident in motion — a deploy,
     a config change, a traffic spike, a dependency failure, a cert expiry.
     Distinct from the root cause: the trigger lit the fuse; the contributing
     factors above are what made it explosive. A trigger is often benign on
     its own and only dangerous given the contributing factors. -->

## Detection

<!-- guidance: How was the incident discovered, and how long did that take?
     An automated alert, a customer report, or a manual observation? State the
     time from onset to detection. If detection was slow, manual, or came from
     a customer rather than your monitoring, that gap is usually itself an
     action item — note it. -->

## Resolution

<!-- guidance: What actually stopped the bleeding, and what restored full
     service. Distinguish the temporary mitigation (rolled back the deploy,
     shed load, failed over) from the permanent fix, if they differ. Be
     specific about what worked — and note mitigations that were tried and did
     not work, since that is useful for the next responder. -->

## Action items

<!-- guidance: Concrete follow-up work to prevent recurrence, detect faster,
     or reduce blast radius. Every item must be specific, owned, dated, and
     tracked in your real issue tracker — link the ticket. Action items that
     live only in this document rot. "Be more careful" is not an action item.

     Type is one of:
       - prevent: stop this cause from recurring
       - detect: notice it faster next time (monitoring, alerting)
       - mitigate: reduce the impact when it does recur
       - process: runbooks, training, on-call, comms -->

| Action item | Type | Owner | Due | Ticket |
|---|---|---|---|---|
|  |  |  |  |  |
|  |  |  |  |  |

## Lessons learned

<!-- guidance: The honest reflection. Keep it blameless and specific. The
     three buckets below are a deliberate prompt — fill all three. -->

### What went well

<!-- guidance: What helped — good tooling, a fast rollback, a clear runbook, a
     quick diagnosis (credited to a role or action, not framed as heroics to
     depend on next time). -->

### What went wrong

<!-- guidance: What made the incident worse or slower to resolve — gaps in
     monitoring, missing safeguards, confusing dashboards, unclear
     ownership. -->

### Where we got lucky

<!-- guidance: The things that broke in your favor but might not next time.
     This surfaces latent risk: "the bug shipped Friday but only triggered
     under EU peak load, so US traffic was unaffected." Each of these is a
     candidate action item. -->

## Timeline

<!-- guidance: A chronological, timestamped account from the triggering change
     to the all-clear. Use ISO 8601 timestamps in a single, explicitly stated
     timezone (UTC is a safe default); optionally add relative offsets
     (T+0, T+14m) to make durations obvious.

     Capture the key inflection points: triggering change → first alert or
     detection → escalation/paging → mitigation attempts (and whether each
     worked) → root cause identified → fix applied → recovery → all-clear.
     Keep entries terse and factual; link to evidence (dashboards, log lines,
     chat) rather than pasting it inline. (Some teams put the timeline higher,
     right after Impact — that is fine.) -->

- **YYYY-MM-DDThh:mm UTC** —
- **YYYY-MM-DDThh:mm UTC** —
- **YYYY-MM-DDThh:mm UTC** —

## Supporting information

<!-- guidance: Optional. Dashboards, graphs, log excerpts, a link to the
     incident channel or call bridge, and related incidents or postmortems.
     Delete this section if there is nothing to add. -->
