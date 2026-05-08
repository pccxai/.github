# PCCX

PCCX is an open hardware/software ecosystem for AI accelerator research, FPGA bring-up, verification tooling, and developer workflows.

Website: https://pccx.ai  
Contact: contact@pccx.ai  
Security: security@pccx.ai

PCCX™ is a pending trademark.

Open hardware / software research for NPU architecture, FPGA
acceleration, and verification tooling. The project ships a
versioned IP-core package, a board integration, a verification lab,
an editor layer, and a local launcher under one umbrella.

## Project map

### [pccx](https://github.com/pccxai/pccx)

Canonical specification, public documentation site, project index,
and release coordination across the ecosystem.

### [pccx-v002](https://github.com/pccxai/pccx-v002)

Versioned v002 IP-core package — board- and model-agnostic reusable
RTL for LLM and shared subsystems. Consumed by board integration
repositories at a pinned SHA.

### [pccx-v003](https://github.com/pccxai/pccx-v003)

Canonical v003 IP-core planning package — same shape as `pccx-v002`
(LLM, Vision, Voice, common). Planning / evidence-gated; no v003 RTL
or contract is released yet. New reusable v003 LLM material belongs
under `pccx-v003/LLM/`.

### [pccx-FPGA-NPU-LLM-kv260](https://github.com/pccxai/pccx-FPGA-NPU-LLM-kv260)

KV260 + LLM application integration. Consumes `pccx-v002` through
the `third_party/pccx-v002` submodule, plus board constraints,
Vivado project files, and bare-metal driver code.

### [pccx-lab](https://github.com/pccxai/pccx-lab)

CLI-first verification lab and trace profiler. Provides the shared
analyze / status boundary that editor and launcher integrations
consume. Plugin system and external tool interface are planned. GUI
is a secondary surface.

### [systemverilog-ide](https://github.com/pccxai/systemverilog-ide)

SystemVerilog IDE layer spun out from pccx-lab. Targets diagnostics,
xsim log integration, and reviewed SystemVerilog development
workflows.

### [pccx-llm-launcher](https://github.com/pccxai/pccx-llm-launcher)

User-facing local LLM launcher targeting KV260-class edge devices.
Currently a planning scaffold; real launch flow depends on FPGA
bring-up evidence from `pccx-FPGA-NPU-LLM-kv260`.

### [pccx-vision-v001](https://github.com/pccxai/pccx-vision-v001)

Standalone vision track on the KV260 + v002 substrate. Default
direction: fold into `pccx-v002/Vision/` after a compatibility
review.

### [pccxai](https://github.com/pccxai/pccxai)

Organization placeholder and site assets.

## Historical / retired

`pccx-LLM-v003` was an early temporary feeder for v003 LLM planning.
It is superseded by `pccx-v003` and is no longer an active public
track.

## Trademark

`PCCX™` is a mark used by the PCCX project. Korean trademark
applications are pending in Classes 09 and 42 (application numbers
`40-2026-0091497` and `40-2026-0091498`). Registration has not been
granted; do not use `PCCX®` unless and until registration is
granted and the central trademark policy is updated. See the central
policy at
[`pccx/TRADEMARKS.md`](https://github.com/pccxai/pccx/blob/main/TRADEMARKS.md).

## Roadmap and tracking

Execution is tracked on the
[PCCX Roadmap project](https://github.com/orgs/pccxai/projects/1).
The short release-track summary lives at
[pccx/docs/roadmap](https://pccx.pages.dev/en/docs/roadmap.html).

## Contributing

Focused issues, documentation improvements, reproducible benchmarks,
and small experiments are welcome. See each repository's
`CONTRIBUTING.md` for project-specific guidance. Open a discussion
before starting non-trivial work. Contributions do not create rights
to equity, royalties, revenue share, profit share, employment,
sponsorship payments, or investor returns.

## Contact

For security disclosures, see
[SECURITY.md](https://github.com/pccxai/.github/blob/main/SECURITY.md).
For other questions, file an issue in the relevant repository.
