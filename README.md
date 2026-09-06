<p align="center">
  <img src="https://raw.githubusercontent.com/Coccinella-Labs/title/main/.github/assets/thumbnail.png" alt="title" width="100%">
</p>

# Title

[![Release](https://img.shields.io/github/v/release/libnudget/title?logo=github&label=latest)](https://github.com/libnudget/title/releases)

Fix PR title to conventional format.

## What it does

Auto-converts PR title formats and removes 'add' prefixes:
- `Add: new feature` → `[add] new feature`
- `[ADD] new feature` → `[add] new feature`
- `[ci] add macos job` → `[ci] macos job`

## Trigger

Automatically on PR: `opened`, `reopened`, `synchronize`, `edited`

## Usage

```yaml
name: Fix PR Title

on:
  pull_request:
    types: [opened, reopened, synchronize, edited]
    branches: [main]

jobs:
  fix-title:
    runs-on: ubuntu-latest
    steps:
      - uses: libnudget/title@v1
```

## Example

**Before:** `ADD: new feature`
**After:** `[add] new feature`

Or:
**Before:** `[feat] add new feature`
**After:** `[feat] new feature`

Or:
**Before:** `[ci] add macos job`
**After:** `[ci] macos job`

The `add` prefix is removed entirely from titles.

## License

MIT