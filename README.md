ADR Action
---

Action to generate [Architecture Decision Records](https://adr.github.io/) Table of Contents and ADR Graph dependency into a README.md in the ADR dir.

## Usage
---

```yaml
- uses: jules2689/adr-action@main
  with:
    adr-dir: '' # Optional. Directory in which ADRs are located. Defaults to contents of .adr-dir
    adr-tool-repo: 'https://github.com/npryce/adr-tools.git' # Optional. ADR Tool Repo location 
    adr-tool-version: '3.0.0' # Optional. Version of the Tools to use.
    github-token: '' # Optional. Token with which to commit
```

### Example

```
name: ADR

on:
  push:
    branches: [main, master]

jobs:
  generate_adr_toc:
    runs-on: ubuntu-latest
    name: Lint ADRs and generate Table of Contents
    steps:
    - uses: actions/checkout@v2
    - uses: jules2689/adr-actions@0.0.3
```
