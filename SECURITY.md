# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 0.1.x   | :white_check_mark: |
| < 0.1.0 | :x:                |

## Reporting a Vulnerability

If you discover a potential security issue in `sweepr`, particularly regarding unsafe path traversal, accidental file destruction, permission escalation, or unintended file modification:

1. Please report it privately using GitHub's [Private Vulnerability Reporting](https://github.com/amandeavor/sweepr/security/advisories/new) or by contacting the maintainer.
2. Provide a reproduction case with minimal directory structures and command arguments.
3. Allow reasonable time for investigation and patch preparation before disclosing the issue publicly.

## Filesystem Safety Invariants

`sweepr` is built around conservative filesystem invariants:
- `--dry-run` is always the default execution mode.
- Existing destination files are never overwritten; automatic numerical renaming is applied to resolve collisions.
- Symbolic links are deliberately skipped to prevent escaping target directory boundaries.
- Internal metadata (`.sweepr/`) is excluded from organization sweeps.
- Undo operations verify that target destinations have not been replaced or altered before restoring original file paths.
