ADR Action
---

Action to generate [Architecture Decision Records](https://adr.github.io/) Table of Contents and ADR Graph dependency into a README.md in the ADR dir.

This action also does some basic linting to:
- Ensure no duplicate numbering of ADRs
- ADR numbers in the filename (`0005-file.md`) match the title (`# 5. Title`)
- Add ADRs have titles (`# Number. Title`) as the first line

## Usage
---

```yaml
- uses: jules2689/adr-action@main
  with:
    adr-dir: '' # Optional. Directory in which ADRs are located. Defaults to contents of .adr-dir
    adr-tool-repo: 'https://github.com/npryce/adr-tools.git' # Optional. ADR Tool Repo location 
    adr-tool-version: '3.0.0' # Optional. Version of the Tools to use.
    github-token: '' # Optional. Token with which to commit
    generate-toc: true # Optional: Specify if we should generate TOC. Defaults to true.
    generate-toc-branches: "['main', 'master']" # Optional: JSON Array of Branch names as a string. specify which branches we should generate TOC on. Defaults to main/master. 
```

### Example

```
name: ADR

on:
  push: {} # Run on everything, restrict TOC generation with 'generate-toc-branches'

jobs:
  generate_adr_toc:
    runs-on: ubuntu-latest
    name: Lint ADRs and generate Table of Contents
    steps:
    - uses: actions/checkout@v2
    - uses: jules2689/adr-actions@0.0.3
```
