# Security Policy

## Reporting a vulnerability

Please do not file a public issue for security findings.

Email k1h6w4@gmail.com with:

- A description of the issue and the affected repository.
- Steps to reproduce, or a minimal proof of concept.
- The version, commit SHA, or build identifier where the issue was observed.
- Any known mitigations or workarounds.

## Process

- Initial acknowledgement: within 7 days.
- Triage and impact assessment: within 30 days.
- Coordinated disclosure window: up to 90 days from acknowledgement, extended only when a fix demonstrably needs more time.

A fix and advisory are published together once a release with the patch is available.

## Scope

This policy covers code in repositories under the `pccxai` organisation.
Hardware test fixtures, draft documentation, and archived directories are out of scope unless the issue affects users running a published artefact.

## Out of scope

- Findings that require physical access to a maintainer's machine.
- Issues in third-party dependencies -- report upstream first; tracked here once the upstream advisory is public.
- Theoretical attacks without a working proof of concept.
