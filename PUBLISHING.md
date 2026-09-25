# Publishing Sweepr

The PyPI project name is **`sweepr-cli`**. The installed console command remains **`sweepr`**.

The unscoped name `sweepr` is already taken on PyPI by an unrelated project. Do not attempt to publish under that name.

## Verify a release

```sh
python -m pip install -e ".[dev]"
python -m pytest
python -m ruff check .
python -m ruff format --check .
python -m build
```

Inspect the built `dist/` artifacts before uploading. They must not contain credentials, local virtualenvs, or unrelated workspace files.

## TestPyPI first

With a TestPyPI account authenticated via Trusted Publisher or a short-lived API token (never committed):

```sh
python -m twine upload --repository testpypi dist/*
```

Then verify in a clean environment:

```sh
pipx install --index-url https://test.pypi.org/simple/ --pip-args="--extra-index-url https://pypi.org/simple/" sweepr-cli
sweepr --help
```

## PyPI

After TestPyPI looks correct, publish the same version to PyPI (Trusted Publisher preferred):

```sh
python -m twine upload dist/*
```

Configure [Trusted Publishing](https://docs.pypi.org/trusted-publishers/) on PyPI/TestPyPI for this GitHub repository when automating releases. Do not store PyPI API tokens, passwords, or `.pypirc` secrets in the repository.

Repository tags and GitHub Releases do not upload to PyPI by themselves until a publish workflow (or a manual maintainer upload) is run.

After a successful PyPI publish, confirm `pipx install sweepr-cli` works from a clean machine before treating registry install docs as live.
