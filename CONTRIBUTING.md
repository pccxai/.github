# Contributing

These guidelines apply to all PCCX AI repositories unless a repository ships its own override.

## Where to start

- Browse issues labelled `good first issue` in the relevant repository.
- Open a discussion before starting non-trivial work, so scope and design are agreed up front.
- Search existing issues and pull requests before filing a duplicate.

## Branches and commits

- Branch from `main`. Use `feat/`, `fix/`, `docs/`, `chore/`, or `refactor/` prefixes.
- Conventional commit subjects: `<type>(<scope>): <imperative summary>`.
- Subject under 72 characters. Body explains why; the diff shows what.
- One logical change per commit. Avoid mixing renames with edits.

## Pull requests

- Target `main`. Keep the diff focused.
- Describe motivation, approach, and any verification steps in the PR body.
- Link the related issue or discussion.
- Ensure CI is green before requesting review.

## Code style

- Match the file's existing style; do not reformat unrelated code.
- Add tests or reproducible examples where the project supports them.
- Keep documentation in sync with behaviour changes.

## AI-assisted engineering

PCCX AI uses AI workers to accelerate development. The following principles
keep that work safe and sustainable.

**Human strategy, AI execution.** AI workers implement local changes within
agreed boundaries. The human maintainer owns system architecture, release
decisions, and critical verification. AI workers do not expand architecture
speculatively.

**Interface first.** Agree on the public interface or boundary before
implementation begins. Use a planning step for anything non-trivial — state
assumptions explicitly rather than assuming a written spec is complete.

**Tests and tight feedback loops.** Run the cheapest available check before
declaring work done: `cargo check`, `pytest -q`, `git diff --check`. Large
patches without test coverage are not accepted.

**Deep modules over shallow ones.** Public interfaces should be small and
stable-looking. Internal complexity belongs behind clear module boundaries.

**Gray-box delegation.** Humans review public interfaces, IPC contracts, and
hardware-sensitive boundaries. AI workers can implement internals behind those
boundaries. Critical modules require stricter human sign-off.

**Evidence-first releases.** No production-ready claim without evidence. No
stable API/ABI claim without an explicit decision. No KV260 inference or
timing-closure claim without verified hardware evidence.

**PCCX-specific boundaries.** `pccx-lab` is CLI/core first; GUI second. All
IDE, editor, MCP, and AI worker workflows sit on the controlled CLI/core
boundary. The FPGA bring-up path is human-owned and human-verified.

For the full reference, see
[AI-assisted engineering discipline](https://github.com/pccxai/pccxai/blob/main/docs/AI_ASSISTED_ENGINEERING.md).

## Reporting security issues

Do not file a public issue for security findings. See [SECURITY.md](SECURITY.md).
