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
- Releases follow the maintainer-owned [release process](RELEASE_PROCESS.md).

## Code style

- Match the file's existing style; do not reformat unrelated code.
- Add tests or reproducible examples where the project supports them.
- Keep documentation in sync with behaviour changes.

## Engineering discipline

Architecture, release decisions, and hardware-sensitive verification are maintainer-owned.

Non-trivial changes should define the public interface or boundary before implementation. Use focused pull requests, tests, and evidence-backed release language.

Do not make production-ready, stable API/ABI, KV260 inference, timing-closure, or throughput claims without linked evidence.

## Reporting security issues

Do not file a public issue for security findings. See [SECURITY.md](SECURITY.md).

## Operator, rights and first checks

PCCX is initiated and operated by Altifigence. Repository maintainers review
technical work; Altifigence is responsible for current operations, budgets and
contracts. See [Transparency](https://pccx.ai/en/legal/transparency/).

Use the [start guide](https://github.com/pccxai/pccx/blob/main/START_HERE.md)
and the repository's own checks. Buying or using Altifigence tools is optional.
The proposed developer support program is not yet open for applications.

Contribute only material you have the right to submit. Preserve author, source
and license notices. Copyright is not automatically assigned to Altifigence.
Existing file/repository licenses control; the Apache-2.0 code license does not
cover every document or mark. For new prose or artwork without an existing
contribution license, resolve publication permissions in the PR before merge.
No draft CLA, DCO or future policy becomes binding merely by being linked here.
