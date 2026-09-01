# Roadmap

This document outlines the planned technical direction and near-term priorities for `sweepr`.

## Near-Term (v0.2.x)

- [ ] **Configurable Custom Rules**: Support user-defined category mapping via a `.sweepr.toml` or `pyproject.toml` configuration file.
- [ ] **Interactive TTY Mode**: Optional interactive prompt to review operations category-by-category before applying.
- [ ] **Regex Exclude & Include**: Extend glob filtering to support full regular expressions for fine-grained file selection.
- [ ] **Date-based Partition Formatting**: Allow configurable date formats (e.g. `YYYY-MM` vs `YYYY/MM`).

## Long-Term (v1.0.x)

- [ ] **Duplicate File Detection**: Hash-based detection of exact duplicate files with prompt to deduplicate or hardlink.
- [ ] **Cross-Platform Extended Attributes**: Retain file creation times and extended attributes across POSIX and Windows filesystems where possible.
- [ ] **Plugin / Hook System**: Allow custom python hooks before and after moves (e.g. metadata extraction, image resizing).
