# PCCX AI

Open hardware/software research for NPU architecture, FPGA acceleration, and verification tooling.

## Projects

### [pccx](https://github.com/pccxai/pccx)

Specification, documentation, and release coordination across the ecosystem.

### [pccx-FPGA-NPU-LLM-kv260](https://github.com/pccxai/pccx-FPGA-NPU-LLM-kv260)

RTL, Sail reference, and KV260 bring-up artifacts. Hardware evidence lives here.

### [pccx-lab](https://github.com/pccxai/pccx-lab)

CLI-first verification lab. Provides the shared analyze and status boundary that
editor and launcher integrations consume. Plugin system and external tool interface are planned.
GUI is a secondary surface.

### [systemverilog-ide](https://github.com/pccxai/systemverilog-ide)

SystemVerilog IDE spin-out from pccx-lab. Targets diagnostics, xsim log integration,
and reviewed SystemVerilog development workflows.

### [pccx-llm-launcher](https://github.com/pccxai/pccx-llm-launcher)

User-facing local LLM launcher, targeting KV260-class edge devices. Currently a
planning scaffold; real launch flow depends on FPGA bring-up evidence from
pccx-FPGA-NPU-LLM-kv260.

## Roadmap and tracking

Execution is tracked on the [PCCX Roadmap project](https://github.com/orgs/pccxai/projects/1).
The short release-track summary lives at [pccx/docs/roadmap](https://pccxai.github.io/pccx/en/docs/roadmap.html).

## Reusable CI Workflows

Workflow templates prepared in [pccxai/.github#10](https://github.com/pccxai/.github/pull/10):

- [claim-guard](../workflow-templates/claim-guard.yml): checks pull request diffs for restricted release and source wording.
- [xsim-regression](../workflow-templates/xsim-regression.yml): runs `hw/sim/run_verification.sh --full` when a repository provides it.
- [evidence-gate](../workflow-templates/evidence-gate.yml): requires an `Evidence state:` line in the pull request body.

## Today's activity

Merged lane activity is summarized by range, 50 PRs total:

- [pccx-lab#124](https://github.com/pccxai/pccx-lab/pull/124)-[#159](https://github.com/pccxai/pccx-lab/pull/159): extended JSON-boundary coverage across MCP client and plugin host fixtures.
- [systemverilog-ide#116](https://github.com/pccxai/systemverilog-ide/pull/116)-[#123](https://github.com/pccxai/systemverilog-ide/pull/123): added module health, summary, view, graph, and refactor CLI coverage.
- [pccx#41](https://github.com/pccxai/pccx/pull/41)-[#46](https://github.com/pccxai/pccx/pull/46): refreshed public docs for v003, vision-v001, typography, and home-page visibility.
- [pccxai/.github#9](https://github.com/pccxai/.github/pull/9) and [#10](https://github.com/pccxai/.github/pull/10): keep org profile, community templates, and reusable workflow templates under review.

## Contributing

Focused issues, documentation improvements, reproducible benchmarks, and small experiments are welcome.
See each repository's `CONTRIBUTING.md` for project-specific guidance.
Open a discussion before starting non-trivial work.

## Contact

For security disclosures, see [SECURITY.md](https://github.com/pccxai/.github/blob/main/SECURITY.md).
For other questions, file an issue in the relevant repository.
