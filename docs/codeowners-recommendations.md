# CODEOWNERS recommendations

This repository provides the organization default ownership file. Individual
repositories should add local CODEOWNERS entries when maintenance is shared
across more contributors.

GitHub reads the first CODEOWNERS file it finds in `.github/`, the repository
root, or `docs/`. Keep one local file per repository and place narrower rules
after broader rules so the most specific owner wins.

## Starting point

Begin with the organization default and replace owners with visible teams or
users that have write access to the repository:

```text
* @pccxai/maintainers

docs/ @pccxai/docs-maintainers
hw/rtl/ @pccxai/rtl-maintainers
editors/ @pccxai/editor-maintainers
```

Keep `*` assigned to repository maintainers until every active area has a
named owner. Avoid assigning paths to teams before they are visible in the
organization and granted repository write access.

## kv260 path conventions

The `pccx-FPGA-NPU-LLM-kv260` repository uses stable top-level areas that are
good candidates for local ownership once contributor groups exist:

- `docs/` for public documentation, release notes, evidence inventories, and
  hardware handoff notes.
- `hw/rtl/` for synthesizable SystemVerilog, including controller, memory,
  matrix, vector, preprocessing, constants, and library code.
- `hw/tb/`, `hw/sim/`, `formal/`, and `hw/constraints/` for verification,
  simulation, formal models, and constraint files.
- `hw/vivado/` for project and build scripts tied to the FPGA flow.
- `sw/driver/` for the host driver API and HAL.
- `configs/`, `scripts/`, and `tools/` for manifests, run scripts, and
  helper utilities.
- `evidence/` for recorded run artifacts and inventories.

Those conventions support ownership rules such as:

```text
docs/ @pccxai/docs-maintainers
hw/rtl/ @pccxai/rtl-maintainers
hw/tb/ @pccxai/verification-maintainers
hw/sim/ @pccxai/verification-maintainers
formal/ @pccxai/formal-maintainers
hw/constraints/ @pccxai/fpga-maintainers
hw/vivado/ @pccxai/fpga-maintainers
sw/driver/ @pccxai/driver-maintainers
configs/ @pccxai/release-maintainers
scripts/ @pccxai/release-maintainers
tools/ @pccxai/release-maintainers
evidence/ @pccxai/evidence-maintainers
```

## Other repositories

For documentation-heavy repositories, keep `docs/` separate from source paths
so documentation changes can receive a focused review. For editor tooling,
route `editors/` to the maintainers responsible for editor integration files.
For mixed hardware and software repositories, split `hw/rtl/`, verification,
build-flow, and driver paths before adding finer module-level rules.
