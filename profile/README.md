# PCCX AI

Open hardware/software research for NPU architecture, FPGA acceleration, and AI-assisted verification.

## Projects

### [pccx](https://github.com/pccxai/pccx)

SystemVerilog-based NPU core architecture and the canonical documentation site.
Targets Xilinx Kria KV260 (Zynq UltraScale+ ZU5EV) for autoregressive LLM decoding at the edge.

### [pccx-FPGA-NPU-LLM-kv260](https://github.com/pccxai/pccx-FPGA-NPU-LLM-kv260)

KV260 board integration: NPU plus LLM/KV-cache implementation, RTL, and bring-up notes.

### [pccx-lab](https://github.com/pccxai/pccx-lab)

Rust and Tauri development and verification toolchain.
Design, performance analysis, bottleneck detection, visualization, automated reports, and pipeline orchestration in one workspace.

## Current Focus

- NPU RTL architecture and verification
- FPGA deployment on Xilinx KV260
- AI-assisted design, analysis, and documentation workflows
- Hardware/software co-design for edge inference

## Contributing

Focused issues, documentation improvements, reproducible benchmarks, and small experiments are welcome.
See each repository's `CONTRIBUTING.md` for project-specific guidance.

Open a discussion before starting non-trivial work.

## Contact

For security disclosures, see [SECURITY.md](https://github.com/pccxai/.github/blob/main/SECURITY.md).
For other questions, file an issue in the relevant repository.
