# ADR001: ASSI capability inside Foundry

Date: 2026-10-16
Status: Accepted owner direction; implementation and deployment unqualified.

## Decision

Zati is the organizational front door, including skills and agent departments.
Foundry is independently usable engineering software. ASSI owns infrastructure lifecycle and scoped custody
inside the Foundry product. A repository, process, database schema or restricted
principal can remain separate for delivery and security; this does not create
another product the owner must administer. Public interfaces preserve scoped
projects and externally enforced authorization rather than pooling credentials.

ASSI receives desired lifecycle intent from the owner/Zati, reconciles resource ownership and desired versus observed footprint, and delegates authorized mutations to protected execution adapters. Bora supplies observations and checks outcomes; it does not own infrastructure desired state or arbitrary cleanup.

Routine production changes and recovery may run under explicit bounded policy.
Destructive, privilege-expanding, spend-expanding or otherwise exceptional work
requires the applicable current human grant. Existing qualified execution paths
remain until replacement boundaries are independently qualified; no silent
credential cutover or duplicate mutation scheduler is introduced.

## Priority and authority

Production observability comes first across all production projects. AWS and
Kubernetes are selected with a $100/month observability infrastructure ceiling,
separate from Foundry's $150/month hosting/worker ceiling. Go is required for
our core; proven OSS dependencies may use other languages. Stack components,
capacity and complete signal coverage still require qualification. No EKS
migration, deployment or new spending is authorized by this documentation.
Telemetry deployment must not wait for complete ASSI, APRL or Gist replacement.

[Foundry ADR0010](https://github.com/sirerun/foundry/blob/main/docs/adr/0010-zati-foundry-portfolio-boundaries.md)
and [ADR0011](https://github.com/sirerun/foundry/blob/main/docs/adr/0011-observability-first-delivery.md)
record the cross-project direction. [The canonical portfolio plan](https://github.com/sirerun/foundry/blob/main/docs/portfolio-plan.md)
owns the coordinated delivery graph; local [plan.md](../plan.md) is a pointer.
These links are coordinated document destinations, not proof of landing.

## Consequences

The prior [authored RFC](../archive/20261016/rfc-001.md.source) remains exact
history. The active RFC supersedes standalone-product assumptions and blanket
production approval rules while retaining isolation, evidence and recovery
requirements. Source, tests, provider behavior, installation and live coverage
must be reported separately. Implementation and operational authority require
their own qualified scope and receipts.
