# Security Disclosure Template

Use this template when a repository needs its own `SECURITY.md`, security
section in `README.md`, or disclosure process in project documentation.
Replace bracketed placeholders before publishing.

## Security Policy

### Reporting a vulnerability

Please do not file a public issue for security findings.

Email `[security-contact@example.com]` with:

- A description of the issue and the affected repository.
- Steps to reproduce, or a minimal proof of concept.
- The version, commit SHA, release, or build identifier where the issue was
  observed.
- The expected impact, including whether credentials, data, execution, or
  availability are affected.
- Any known mitigations or workarounds.

If the report includes sensitive logs, credentials, customer data, or exploit
code, state that in the first message so maintainers can arrange a safer
transfer method.

### Supported versions

This project accepts vulnerability reports for:

- The default branch.
- Currently supported releases listed in `[link to release policy]`.
- Published artefacts that users are expected to deploy or run.

Unsupported branches, forks, archived code, draft documentation, and local
development experiments are out of scope unless the issue affects a supported
release or published artefact.

### Response process

- Initial acknowledgement: within `[7 days]`.
- Triage and impact assessment: within `[30 days]`.
- Fix target: as soon as practical based on severity, exploitability, and
  release risk.
- Coordinated disclosure window: up to `[90 days]` from acknowledgement,
  extended only when a fix demonstrably needs more time.

Maintainers will confirm receipt, assess reproducibility and impact, identify
affected versions, and coordinate remediation with the reporter when practical.
A fix, release note, and advisory should be published together once a patched
release is available.

### Disclosure expectations

Reporters should allow maintainers a reasonable opportunity to investigate and
release a fix before public disclosure. Maintainers should keep reporters
informed when there are material status changes, such as confirmation,
mitigation availability, release timing, or advisory publication.

Public disclosure should include enough detail for users to understand impact
and mitigation steps without unnecessarily enabling active exploitation before
patched versions are available.

### Out of scope

- Findings that require physical access to a maintainer's machine.
- Issues in third-party dependencies; report upstream first unless this project
  adds project-specific exploitability or exposure.
- Theoretical attacks without a working proof of concept or plausible exploit
  path.
- Denial-of-service reports based only on high-volume traffic without a
  project-specific amplification or resource exhaustion issue.
- Social engineering, spam, phishing, or account takeover reports that do not
  involve this project's code or deployment.

### Safe harbor

Good-faith security research is welcome when it avoids privacy violations,
service disruption, data destruction, and access beyond what is necessary to
demonstrate the issue. Do not access, modify, delete, or exfiltrate data that
does not belong to you.

### Maintainer checklist

- Confirm the report and assign an owner.
- Reproduce the finding in a controlled environment.
- Determine affected versions, severity, and likely exploitability.
- Prepare a fix, regression test, and release plan.
- Decide whether a GitHub Security Advisory, CVE request, or downstream notice
  is needed.
- Credit the reporter if they request attribution and disclosure policy allows
  it.
