# Dependabot Template Usage Policy

This policy applies to PCCX AI repositories that copy or adapt the shared
`dependabot.yml` template. It is based on the Dependabot template cited from
PR #q31, `workflow-templates/dependabot.yml`.

## Purpose

Dependabot keeps routine dependency maintenance visible and reviewable. The
shared template is a starting point for repositories that use Cargo, Python, or
Node.js package manifests at the repository root.

Use the template to:

- Open dependency update pull requests on a predictable weekly cadence.
- Keep dependency maintenance separate from feature, release, and refactor
  work.
- Limit automated pull request volume so maintainers can review updates with
  the same care as human-authored changes.

Do not use the template to:

- Replace maintainer review of dependency impact, licensing, or security risk.
- Make production-readiness, timing-closure, throughput, stable API/ABI, or
  hardware-readiness claims.
- Enable ecosystems that the repository does not actually use.

## Template Scope

The shared template defines weekly updates for:

- `cargo` at `/`
- `pip` at `/`
- `npm` at `/`

Each ecosystem has `open-pull-requests-limit: 5`. Repositories should keep that
limit unless they document a reason to use a lower value. Raising the limit is a
maintainer-owned decision because it changes review load across the repository.

## Adoption Rules

When adopting the template:

1. Copy it to `.github/dependabot.yml` in the target repository.
2. Keep only ecosystems that match package manifests owned by that repository.
3. Keep `directory: "/"` only when the relevant manifest is at the repository
   root. Add separate entries for real subdirectories instead of relying on a
   root entry to cover them.
4. Keep the weekly schedule unless the repository has a documented release or
   security need for a different cadence.
5. Treat the first Dependabot pull requests as a smoke check for configuration
   accuracy, reviewer routing, and CI coverage.

Repositories may add other supported ecosystems when they have matching
manifests and maintainers who can review the resulting updates. Do not add
placeholder ecosystems for future tooling.

## Review Expectations

Dependabot pull requests require normal review. Reviewers should check:

- The updated dependency is used by the repository and the update is in scope.
- License, notice, and attribution changes remain compatible with the
  repository's open-source policy.
- CI covers the affected package boundary, or the pull request explains the
  manual smoke check that was run.
- Generated lockfile changes are expected for the selected package ecosystem.
- Any security advisory, breaking change, or migration note is reflected in the
  pull request discussion before merge.

Merge dependency updates only when the repository's required checks are green
and the reviewer can explain the affected boundary. Batch unrelated dependency
updates only when the repository deliberately groups them and the combined risk
remains reviewable.

## Maintenance

Maintainers should review `.github/dependabot.yml` whenever a repository adds,
removes, or moves package manifests. Remove stale ecosystem entries promptly so
automation does not imply support for tooling that is no longer maintained.

Changes to the shared template or this policy should happen in focused pull
requests that cite the operational reason for the change and any repositories
affected by the new default.
