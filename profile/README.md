# PCCX AI

Open hardware/software research for NPU architecture, FPGA acceleration, and AI-assisted verification.

## Projects

### [pccx](https://github.com/pccxai/pccx)

Specification, documentation, and release coordination across the ecosystem.

### [pccx-FPGA-NPU-LLM-kv260](https://github.com/pccxai/pccx-FPGA-NPU-LLM-kv260)

RTL, Sail reference, and KV260 bring-up artifacts. Hardware evidence lives here.

### [pccx-lab](https://github.com/pccxai/pccx-lab)

CLI-first verification lab. Hosts the plugin system and the controlled MCP backend.
AI workers can interact with pccx-lab through that MCP interface. GUI is a secondary surface.

### [pccx-systemverilog-ide](https://github.com/pccxai/pccx-systemverilog-ide)

SystemVerilog IDE spin-out from pccx-lab. Targets diagnostics, xsim log integration,
and an AI-assisted SystemVerilog development workflow.

### [pccx-llm-launcher](https://github.com/pccxai/pccx-llm-launcher)

User-facing local LLM launcher. Connects to KV260 and integrates pccx-lab diagnostics.

## Roadmap and tracking

Execution is tracked on the [PCCX Roadmap project](https://github.com/orgs/pccxai/projects/1).
The short release-track summary lives at [pccx/docs/roadmap](https://pccxai.github.io/pccx/roadmap.html).

## Contributing

Focused issues, documentation improvements, reproducible benchmarks, and small experiments are welcome.
See each repository's `CONTRIBUTING.md` for project-specific guidance.
Open a discussion before starting non-trivial work.

## Contact

For security disclosures, see [SECURITY.md](https://github.com/pccxai/.github/blob/main/SECURITY.md).
For other questions, file an issue in the relevant repository.
