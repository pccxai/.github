# Release Process

These steps apply to PCCX AI repositories unless a repository documents a stricter release procedure.

This process records how maintainers create a release. It does not describe the current state of any repository.

## Preconditions

- The release scope is maintainer-approved in an issue, discussion, or pull request.
- The release commit is identified on the default branch after review and merge.
- All required CI checks for the release commit are green in GitHub.
- Verification evidence exists for every release claim, including links to CI runs, test commands, artifacts, screenshots, or logs.
- Any known exclusions, limitations, or deferred items are written in the release notes.

## Evidence

Before tagging, collect an evidence bundle that can be linked from the GitHub release:

- Release commit SHA.
- Merged pull requests included in the release.
- Required CI check names, conclusions, and GitHub Actions run URLs.
- Manual verification commands and their outputs, when manual checks are part of the release.
- Artifact names, checksums, package links, or build output locations.
- Known limitations and unsupported scenarios.

Do not include production, timing-closure, device-inference, stable API, stable ABI, or performance statements unless the evidence bundle directly supports them.

## CI Gate

1. Open the commit page for the release commit on GitHub.
2. Confirm every required branch-protection check has a passing conclusion.
3. Open each required CI run and confirm it corresponds to the same commit SHA.
4. Record the CI run URLs in the evidence bundle.
5. Stop the release process if a required check is missing, pending, skipped unexpectedly, cancelled, failed, or tied to a different commit.

## Tag

Use an annotated tag from the release commit after the CI gate and evidence collection are complete:

```sh
git fetch origin
git checkout main
git pull --ff-only origin main
git rev-parse HEAD
git tag -a vX.Y.Z -m "vX.Y.Z"
git push origin vX.Y.Z
```

Rules:

- The tag name must match the repository's versioning scheme. Use `vMAJOR.MINOR.PATCH` when the repository has no stricter convention.
- The tag must point to the exact release commit whose CI evidence was collected.
- Do not retag an existing release tag. If a tag was pushed incorrectly, document the incident and follow maintainer direction before taking further action.

## GitHub Release

Create the GitHub release from the pushed tag:

1. Open GitHub Releases for the repository.
2. Choose **Draft a new release**.
3. Select the tag pushed in the tag step.
4. Set the release title to the tag name unless the repository documents a different convention.
5. Write release notes with:
   - Summary of included changes.
   - Links to merged pull requests or changelog entries.
   - CI evidence links for the tagged commit.
   - Manual verification evidence, if applicable.
   - Artifact checksums or package links, if applicable.
   - Known limitations, exclusions, and follow-up work.
6. Attach release artifacts only when they were produced by the verified commit or by documented release automation for that tag.
7. Publish the GitHub release after another maintainer reviews the notes and evidence links.

## After Publishing

- Confirm the release page points to the intended tag and commit.
- Confirm attached artifacts download and match recorded checksums when artifacts are used.
- Announce only the facts supported by the release notes and evidence bundle.
- Open follow-up issues for deferred items or problems found after publication.
