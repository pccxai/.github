# Triage Label Policy

This policy explains the labels contributors will see across PCCX AI repositories.
Repository-specific labels may add detail, but labels with the same name should
carry the same meaning.

The inventory below was checked against the kv260 repository on 2026-05-07.
Observed counts are current issue and pull request assignments at that time; zero
means the label exists in the repo but was not assigned to an open or closed item
in the checked set.

## How contributors use labels

- If you can apply labels, choose one priority, at least one area, and one or
  more type labels when opening an issue.
- If you cannot apply labels, include a short `Suggested labels:` line in the
  issue or pull request body.
- Use `agent-safe` only when the task is bounded and can be validated without
  architecture judgment.
- Use `human-review-required` when correctness, architecture, data formats,
  precision, hardware behavior, or release claims need a reviewer decision.
- Do not use labels as evidence for capability or readiness claims. Link the
  supporting record in the issue or pull request instead.

## Triage flow

```text
New issue or PR
      |
      v
Add priority + area + type
      |
      v
Is the scope clear and actionable?
      | yes                         | no
      v                             v
status:ready                 status:triage
      |                             |
      v                             v
Work starts?                 Needs outside input?
      | yes                         | yes
      v                             v
status:in-progress           status:blocked
      |                             |
      v                             v
Evidence or fix submitted --> Review labels:
                                human-review-required?
                                agent-safe?
      |
      v
Close when accepted, superseded, or no longer planned
```

## Who applies labels

Contributors with label permission may apply labels directly. Other contributors
should suggest labels in the issue or pull request body.

Maintainers and triage contributors adjust priority, status, and review labels
after reading the scope and evidence. Contributors should update their suggested
labels when the scope changes.

## Status changes

`status:triage` marks an item that has not yet been made actionable. Move to
`status:ready` once the requested outcome, owner expectations, and validation
path are clear.

`status:in-progress` starts when someone is actively working the item or a
linked pull request is open. Move to `status:blocked` when progress depends on
external access, design input, missing evidence, hardware availability, or a
decision outside the contributor's control.

Remove or ignore status labels after closure unless a repository keeps closed
items in a planning board that still needs status history.

## Priority labels

| Label | Meaning | Who applies | When it changes | Observed |
| --- | --- | --- | --- | ---: |
| `priority:P0` | Drop current work; needed before other planned work can continue. | Maintainers or triage contributors. | Downgrade after the blocker is removed or a safer workaround is accepted. | 7 |
| `priority:P1` | Next milestone blocker. | Maintainers or triage contributors. | Move to P0 if it blocks the active path; move to P2 when it no longer blocks the milestone. | 8 |
| `priority:P2` | Planned work that is useful but not blocking. | Contributors may suggest; triage confirms. | Move up when it becomes part of the active milestone; move down when deferred. | 10 |
| `priority:P3` | Backlog or nice-to-have item. | Contributors may suggest; triage confirms. | Move up when scope becomes planned or time-sensitive. | 1 |

## Area labels

| Label | Meaning | Who applies | When it changes | Observed |
| --- | --- | --- | --- | ---: |
| `area:admin` | External application, license, access, funding, or artifact policy. | Contributor suggests; triage confirms. | Change when the work moves from policy/admin into implementation. | 3 |
| `area:ci` | CI and workflow behavior. | Contributor suggests; triage confirms. | Change when the work is actually in scripts, docs, or release process. | 0 |
| `area:cvo` | CVO/SFU, CORDIC, softmax, RoPE, or nonlinear scalar operations. | Contributor suggests; triage confirms. | Add or remove when the affected datapath changes. | 1 |
| `area:dispatcher` | Instruction decode, uop dispatch, FIFO, or async completion. | Contributor suggests; triage confirms. | Add or remove when scope crosses dispatcher boundaries. | 4 |
| `area:docs` | Documentation surface. | Contributor suggests; triage confirms. | Change when the issue becomes code, release, or evidence work. | 0 |
| `area:drivers` | Bare-metal drivers. | Contributor suggests; triage confirms. | Add when the boundary includes driver code or driver-facing APIs. | 0 |
| `area:gemm` | GEMM systolic array, DSP W4A8 MAC, packing, or recovery. | Contributor suggests; triage confirms. | Add or remove when GEMM datapath scope changes. | 3 |
| `area:gemv` | GEMV reduction, lane mask, activation broadcast, or output path. | Contributor suggests; triage confirms. | Add or remove when GEMV datapath scope changes. | 2 |
| `area:golden-model` | Python golden model, bit-similarity, or trace comparison. | Contributor suggests; triage confirms. | Add when validation depends on model or trace comparison. | 1 |
| `area:kv260` | Kria KV260 board specifics. | Contributor suggests; triage confirms. | Add when board setup, hardware access, or KV260 integration is required. | 0 |
| `area:memory` | Memory hierarchy. | Contributor suggests; triage confirms. | Add when mappings, arbitration, hierarchy, or buffers are in scope. | 2 |
| `area:npu-top` | Top-level NPU wiring, status, memory routing, or end-to-end path. | Contributor suggests; triage confirms. | Add when an item crosses module boundaries through top-level wiring. | 4 |
| `area:preprocess` | BF16 preprocessing, activation quantization, or scale path. | Contributor suggests; triage confirms. | Add when preprocessing or quantization path behavior is in scope. | 3 |
| `area:release` | Release engineering. | Contributor suggests; triage confirms. | Add when packaging, notes, tags, or release evidence are in scope. | 0 |
| `area:rtl` | RTL source. | Contributor suggests; triage confirms. | Add when the change touches RTL but does not fit a narrower area. | 0 |
| `area:sail` | Sail ISA model. | Contributor suggests; triage confirms. | Add when ISA model behavior or parity is in scope. | 0 |
| `area:scheduler` | Global scheduler, hazard policy, async fence, or chaining. | Contributor suggests; triage confirms. | Add when scheduling or hazard rules are in scope. | 1 |
| `area:software` | Bare-metal software, HAL, instruction emitter, polling, or weights. | Contributor suggests; triage confirms. | Add when software or software-facing integration is in scope. | 3 |
| `area:spec` | Architecture, ISA, scale policy, or data format. | Contributor suggests; triage confirms. | Add when a decision or written contract must be clarified. | 3 |
| `area:synthesis` | Vivado synthesis, implementation, timing, utilization, DSP, BRAM, or URAM. | Contributor suggests; triage confirms. | Add when build reports or hardware resource evidence are needed. | 3 |
| `area:testbench` | SystemVerilog testbenches. | Contributor suggests; triage confirms. | Add when the primary work is a SystemVerilog bench. | 0 |
| `area:verification` | Simulation, testbench, golden model, or xsim verification. | Contributor suggests; triage confirms. | Add when the item primarily asks for evidence or regression coverage. | 3 |

## Type labels

| Label | Meaning | Who applies | When it changes | Observed |
| --- | --- | --- | --- | ---: |
| `type:bug` | Reproducible defect. | Contributor suggests; triage confirms. | Change if the report becomes a feature, question, or design decision. | 0 |
| `type:design` | Requires design decision or spec clarification before implementation. | Maintainers or triage contributors. | Remove when the decision is recorded and implementation can proceed. | 2 |
| `type:docs` | Documentation-only change. | Contributor suggests; triage confirms. | Remove if code, tests, or release mechanics enter scope. | 6 |
| `type:feature` | New capability. | Contributor suggests; triage confirms. | Change if the work is actually a fix, test, or maintenance task. | 0 |
| `type:infra` | Build, CI, scripts, synthesis runner, reports, or tooling. | Contributor suggests; triage confirms. | Add or remove when tooling stops being the primary work. | 2 |
| `type:integration` | Connects multiple modules or end-to-end system behavior. | Contributor suggests; triage confirms. | Add when a change crosses module boundaries; remove when it narrows to one module. | 5 |
| `type:maintenance` | Refactor or housekeeping. | Contributor suggests; triage confirms. | Change if behavior, API, or verification expectations change. | 0 |
| `type:question` | Open question or discussion. | Contributor suggests; triage confirms. | Remove when the question becomes an actionable task. | 0 |
| `type:rtl` | Requires RTL implementation or SystemVerilog module changes. | Contributor suggests; triage confirms. | Add when RTL is expected; remove when the work is docs, tests, or tooling only. | 5 |
| `type:test` | Test or testbench work. | Contributor suggests; triage confirms. | Use for general tests when `type:testbench` is too narrow. | 0 |
| `type:testbench` | Requires simulation testbench, xsim runner, or golden comparison. | Contributor suggests; triage confirms. | Add when the requested output is executable verification evidence. | 8 |

## Status labels

| Label | Meaning | Who applies | When it changes | Observed |
| --- | --- | --- | --- | ---: |
| `status:blocked` | Waiting on external input. | Maintainers, triage contributors, or assignees. | Move out when the missing access, decision, hardware, or evidence is available. | 0 |
| `status:in-progress` | Actively being worked. | Maintainers, triage contributors, or assignees. | Move to ready if work stops; move to blocked if progress waits on outside input. | 1 |
| `status:ready` | Triaged and actionable. | Maintainers or triage contributors. | Move to in-progress when active work starts; move to blocked if a dependency appears. | 2 |
| `status:triage` | Awaiting triage. | Maintainers, triage contributors, or issue authors with permission. | Move to ready, blocked, or close after scope is understood. | 0 |

## Review and automation labels

| Label | Meaning | Who applies | When it changes | Observed |
| --- | --- | --- | --- | ---: |
| `agent-safe` | Safe for bounded automation-assisted work: wiring, tests, scripts, docs, or scaffolding with clear validation. | Maintainers or triage contributors; contributors may suggest. | Remove if the task needs architecture judgment, hardware-sensitive correctness decisions, or unclear validation. | 10 |
| `human-review-required` | Core math, datapath, scale, precision, hardware behavior, or claim-sensitive scope needs human review. | Maintainers or triage contributors; contributors may suggest. | Remove only after the reviewer-sensitive decision is recorded or the scope no longer touches that risk. | 12 |
