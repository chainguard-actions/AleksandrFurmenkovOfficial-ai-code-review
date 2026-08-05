<!-- markdownlint-disable -->

# Hardening Report: AleksandrFurmenkovOfficial--ai-code-review/v1.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **AleksandrFurmenkovOfficial--ai-code-review/v1.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow references `AleksandrFurmenkovOfficial/ai-code-review@main`, which uses a mutable branch name (`@main`) instead of a pinned 40-character commit SHA. This means the action code can change at any time without notice, creating a supply-chain attack risk. It should be pinned to a full SHA, e.g., `AleksandrFurmenkovOfficial/ai-code-review@<40-char-sha> # main`.

Locations:

- `.github/workflows/aireview.yaml:14`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned `AleksandrFurmenkovOfficial/ai-code-review@main` to the full commit SHA `433c05e6936b9f3b6eac1b82c8706a189de4dfe0` in `.github/workflows/aireview.yaml` (line 14). The `# main` comment is preserved for readability. The workflow already had a minimal `permissions:` block (contents: read, pull-requests: write), so no other changes were required.

