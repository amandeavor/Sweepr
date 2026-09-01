# Contributing to sweepr

Thanks for helping improve `sweepr`. We welcome bug fixes, documentation improvements, new file category definitions, and CLI usability enhancements.

## Code of Conduct

All contributors and maintainers are expected to follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## Development Setup

Clone the repository and create a virtual environment:

```bash
git clone https://github.com/amandeavor/sweepr.git
cd sweepr
python -m venv .venv
source .venv/bin/activate
python -m pip install -e ".[dev]"
```

On Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -e ".[dev]"
```

## Quality Commands

Before opening a pull request, run the test suite and linters:

```bash
ruff check .
ruff format --check .
pytest
```

## Pull Request Guidelines

- Keep changes focused and include a clear description of the problem solved.
- Add or update pytest unit tests for any behavior changes.
- Ensure all file operations preserve `--dry-run` safety and do not introduce file collision risks.
- Update documentation and [CHANGELOG.md](CHANGELOG.md) when adding new CLI flags or commands.

## Maintainer Path

Regular contributors who demonstrate reliable code quality, thoughtful code reviews, and strong adherence to file safety invariants may be invited to become maintainers. See [GOVERNANCE.md](GOVERNANCE.md) for details.
