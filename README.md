# Title

Fix PR title to conventional format.

## What it does

Auto-converts PR title formats:
- `Add: new feature` → `[add] new feature`
- `[ADD] new feature` → `[add] new feature`

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

The `add` prefix is removed when there are duplicates.

## License

MIT