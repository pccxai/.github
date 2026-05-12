# Branch Protection Recommendations

These recommendations apply to the default branch of PCCX AI repositories unless
a repository documents a stricter local policy.

## Required settings

- Protect the default branch, normally `main`.
- Require pull requests before merging.
- Require at least one approving review from a maintainer.
- Dismiss stale approvals when new commits are pushed.
- Require conversation resolution before merge.
- Require status checks to pass before merge.
- Require branches to be up to date before merge when the repository has
  integration-sensitive CI.
- Require linear history.
- Do not allow force pushes.
- Do not allow branch deletion.

## Required CI checks

Each repository should require the checks that prove its supported boundary.
Recommended required checks are:

- Formatting or lint checks for source and documentation.
- Unit tests for libraries, CLIs, and reusable modules.
- Build checks for packages, documentation sites, generated artifacts, or RTL
  deliverables.
- Repository-specific smoke checks that cover the public interface advertised by
  the repository.

Do not require optional, hardware-only, or maintainer-only jobs unless the
repository has a stable way to run them for every pull request. Track those
checks as reviewer evidence instead.

## Review expectations

Required reviews should confirm:

- The change has a clear scope and target branch.
- CI coverage is appropriate for the files touched.
- Public interface, release, hardware, timing, and performance claims are backed
  by linked evidence.
- Security-sensitive changes were handled through the security policy when
  needed.

Repository administrators may temporarily bypass branch protection only for
incident response or repository maintenance. Record the reason in the pull
request, issue, or maintainer notes.
