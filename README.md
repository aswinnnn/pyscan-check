## What is pyscan?

Pyscan is a CLI tool that finds dependencies in your Python project and reports any security vulnerability found.

- It uses [osv.dev](https://osv.dev/) as its advisory (its open source and free).
- Pyscan can find dependencies from requirements, pyproject, setup.py and even straight from the source code. supports poetry, filt, hatch, pdm, etc
- Supports formatted text output and json.

## Add it to your repo

Here's a setup file to scan for vulnerabilities on push, modify it to your needs.

Create `.github/workflows/pyscan.yml`

Paste this in there:
```yaml
name: Pyscan dependency scan

on: push
jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - name: Pyscan 
        uses: aswinnnnn/pyscan@1.0.0
```

## Options

wip
